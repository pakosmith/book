<!-- # Object Oriented Programming Features of Rust -->
# Особенности объектно-ориентированного программирования Rust

<!-- Object-oriented programming (OOP) is a way of modeling programs. Objects came
from Simula in the 1960s. Those objects influenced Alan Kay’s programming
architecture in which objects pass messages to each other. He coined the term
*object-oriented programming* in 1967 to describe this architecture. Many
competing definitions describe what OOP is; some definitions would classify
Rust as object oriented, but other definitions would not. In this chapter,
we’ll explore certain characteristics that are commonly considered object
oriented and how those characteristics translate to idiomatic Rust. We’ll then
show you how to implement an object-oriented design pattern in Rust and discuss
the trade-offs of doing so versus implementing a solution using some of Rust’s
strengths instead. -->
Объектно-ориентированное программирование (ООП) - это способ моделирования программ.
Объекты пришли из языка Simula в 1960-х годах. Эти объекты повлияли на архитектуру
программирования Алана Кея, в которой объекты передают сообщения друг другу. Он ввел
термин *объектно-ориентированное программирование* в 1967 году для описания этой
архитектуры. Многие конкурирующие определения описывают, что такое ООП; некоторые
определения будут классифицировать Rust как объектно-ориентированный язык, другие -
нет. В этой главе мы рассмотрим некоторые характеристики, которые обычно считаются
объектно-ориентированными, и как эти характеристики реализованы в Rust. Затем мы
покажем вам, как внедрить объектно-ориентированный шаблон проектирования в Rust,
и обсудим компромиссные решения в этом направлении по сравнению с реализацией
решения, использующего некоторые сильные стороны Rust.
