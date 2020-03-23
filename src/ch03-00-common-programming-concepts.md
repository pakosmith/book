<!-- # Common Programming Concepts -->
# Общие концепции программирования

<!-- This chapter covers concepts that appear in almost every programming language
and how they work in Rust. Many programming languages have much in common at
their core. None of the concepts presented in this chapter are unique to Rust,
but we’ll discuss them in the context of Rust and explain the conventions
around using these concepts. -->
В этой главе рассматриваются понятия, которые встречаются практически в каждом
языке программирования, и то как они работают в Rust. Многие языки программирования
имеют много общего в своей основе. Ни одна из концепций, представленных в этой главе,
не является уникальной для Rust, но мы обсудим их в контексте Rust и объясним
соглашения об использовании этих концепций.

<!-- Specifically, you’ll learn about variables, basic types, functions, comments,
and control flow. These foundations will be in every Rust program, and learning
them early will give you a strong core to start from. -->
В частности, вы узнаете о переменных, основных типах, функциях, комментариях и
потоках управления. Эти основы будут присутствовать в каждой программе Rust,
и раннее их изучение даст вам прочную основу для старта.

<!-- > #### Keywords
>
> The Rust language has a set of *keywords* that are reserved for use by
> the language only, much as in other languages. Keep in mind that you cannot
> use these words as names of variables or functions. Most of the keywords have
> special meanings, and you’ll be using them to do various tasks in your Rust
> programs; a few have no current functionality associated with them but have
> been reserved for functionality that might be added to Rust in the future. You
> can find a list of the keywords in [Appendix A][appendix_a]. -->
> #### Ключевые слова
> Язык Rust имеет набор *ключевых слов*, которые зарезервированы для использования
> самим языком, также как и в других языках. Имейте в виду, что вы не можете
> использовать эти слова в качестве имен переменных или функций. Большинство
> ключевых слов имеют особое значение, и вы будете использовать их для выполнения
> различных задач в своих программах на Rust; некоторые из них не имеют текущих
> функциональных возможностей, связанных с ними, но были зарезервированы для
> функций, которые могут быть добавлены в Rust в будущем. Вы можете найти список
> ключевых слов в [Приложении A][appendix_a].

[appendix_a]: appendix-01-keywords.md
