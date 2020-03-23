<!-- # Common Collections -->
# Общие коллекции

<!-- Rust’s standard library includes a number of very useful data structures called
*collections*. Most other data types represent one specific value, but
collections can contain multiple values. Unlike the built-in array and tuple
types, the data these collections point to is stored on the heap, which means
the amount of data does not need to be known at compile time and can grow or
shrink as the program runs. Each kind of collection has different capabilities
and costs, and choosing an appropriate one for your current situation is a
skill you’ll develop over time. In this chapter, we’ll discuss three
collections that are used very often in Rust programs: -->
Стандартная библиотека Rust включает в себя ряд очень полезных структур данных,
называемых *коллекциями*. Большинство других типов данных представляют одно
конкретное значение, но коллекции могут содержать несколько значений. В отличие
от встроенных массивов и типов кортежей, данные, на которые указывают эти коллекции,
хранятся в куче, что означает, что не нужно знать объем данных на этапе компиляции
и он может увеличиваться или уменьшаться по мере выполнения программы. Каждый тип
коллекций имеет разные возможности и производительность, и выбор подходящего для вашей
текущей ситуации - это навык, который вы приобретете со временем. В этой главе
мы обсудим три коллекции, которые очень часто используются в программах Rust:

<!-- * A *vector* allows you to store a variable number of values next to each other.
* A *string* is a collection of characters. We’ve mentioned the `String` type
  previously, but in this chapter we’ll talk about it in depth.
* A *hash map* allows you to associate a value with a particular key. It’s a
  particular implementation of the more general data structure called a *map*. -->
* *Vector* позволяет хранить переменное число значений друг за другом.
* *String* представляет собой набор символов. Мы уже упоминали тип `String` ранее,
но в этой главе мы поговорим об этом подробнее.
* *Hash map* позволяет вам связывать значение с определенным ключом. Это конкретная
реализация более общей структуры данных, называемой *map*.

<!-- To learn about the other kinds of collections provided by the standard library,
see [the documentation][collections]. -->
Чтобы узнать о других видах коллекций, предоставляемых стандартной библиотекой,
см. [lокументаци.][collections].

[collections]: ../std/collections/index.html

<!-- We’ll discuss how to create and update vectors, strings, and hash maps, as well
as what makes each special. -->
Мы обсудим, как создавать и обновлять векторы, строки и хэш-карты, а также что
делает каждое из них особенным.
