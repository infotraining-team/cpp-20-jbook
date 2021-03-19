Content in Jupyter Book
=======================

There are many ways to write content in Jupyter Book. This short section
covers a few tips for how to do so.

```cpp
size_t result{};
for (const size_t i : std::views::iota(1u, n))
    result += i;
return result;
```

# std::views::iota - sekwencja bez końca

```cpp
size_t result{};
for (const size_t i : std::views::iota(1u) | std::views::take(n))
    result += i;
return result;
```

```{note}
Koncepty zostały zaproponowane jako rozszerzenie języka już w 2002 roku. Ale do standardu weszły dopiero w 2020.
```

```{warning}
Działające wcześniej w niektórych kompilatorach implementacje konceptów nie są zgodne składniowo z wersją, która znalazła się w standardzie.
```

```{admonition} Spróbuj skompilować
:class: tip
My content
```

````{panels}
Verision 1
^^^

```cpp
#include <concepts>

template <typename T>
concept integral = std::is_integral_v<T>;
```
---
Version 2
^^^

```cpp
#include <concepts_lite>

template <typename T>
concept Integral = std::is_integral_v<T>;
```
````


# Structured bindings

````{tabbed} C++17
```cpp
auto [name, value] = std::tuple("pi"s, 3.14);
```
````

````{tabbed} C++11/14
```cpp
std::string name;
double value;

std::tie(name, value) = std::make_tuple("pi"s, 3.14);
```
````


# Definicje

````{margin} Jak przetestować kod
```cpp
TEST_CASE("test)
{
    REQUIRE(foo() == 42);
}
```
````

Range
: Zakres posiadający metody ``begin()`` i ``end()``, które zwracają iteratory wskazujące na elementy zakresu

Iterator
: Obiekt, którego interfejs odpowiada wskaźnikowi. Służy do wskazywania na elementy zakresu.

```{epigraph}
Here is a cool quotation.

-- From me, Jo the Jovyan
```