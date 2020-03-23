<!-- # Functional Language Features: Iterators and Closures -->
# Функциональные возможности языка: итераторы и замыкания

<!-- Rust’s design has taken inspiration from many existing languages and
techniques, and one significant influence is *functional programming*.
Programming in a functional style often includes using functions as values by
passing them in arguments, returning them from other functions, assigning them
to variables for later execution, and so forth. -->
Дизайн Rust черпал вдохновение из многих существующих языков и методов, и
одним из значительных влияний является *функциональное программирование*.
Программирование в функциональном стиле часто включает использование функций
в качестве значений путем передачи их в аргументах, возврата их из других
функций, присвоения их переменным для последующего выполнения и т. д.

<!-- In this chapter, we won’t debate the issue of what functional programming is or
isn’t but will instead discuss some features of Rust that are similar to
features in many languages often referred to as functional. -->
В этой главе мы не будем обсуждать вопрос о том, что такое функциональное
программирование, а вместо этого обсудим некоторые особенности Rust, которые
похожи на функции во многих языках, часто называемых функциональными.

<!-- More specifically, we’ll cover: -->
Более конкретно, мы рассмотрим:

<!-- * *Closures*, a function-like construct you can store in a variable
* *Iterators*, a way of processing a series of elements
* How to use these two features to improve the I/O project in Chapter 12
* The performance of these two features (Spoiler alert: they’re faster than you
  might think!) -->
* *Замыкания*, функциональная конструкция, которую можно хранить в переменной
* *Итераторы*, способ обработки ряда элементов
* Как использовать эти две функции для улучшения проекта ввода/вывода в Главе 12
* Производительность этих двух функций (Спойлер: они быстрее, чем вы думаете!)

<!--Other Rust features, such as pattern matching and enums, which we’ve covered in
other chapters, are influenced by the functional style as well. Mastering
closures and iterators is an important part of writing idiomatic, fast Rust
code, so we’ll devote this entire chapter to them. -->
Другие особенности Rust, такие как сопоставление шаблонов и перечисления,
которые мы рассмотрели в других главах, также зависят от функционального стиля.
Освоение замыканий и итераторов является важной частью написания идиоматического,
быстрого Rust-кода, поэтому мы посвятим им всю эту главу.
