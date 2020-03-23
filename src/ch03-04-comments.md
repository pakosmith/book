<!-- ## Comments -->
## Комментарии

<!-- All programmers strive to make their code easy to understand, but sometimes
extra explanation is warranted. In these cases, programmers leave notes, or
*comments*, in their source code that the compiler will ignore but people
reading the source code may find useful. -->
Все программисты стремятся сделать свой код легким для понимания, но иногда
требуется дополнительное объяснение. В этих случаях программисты оставляют
примечания или *комментарии* в своем исходном коде, которые компилятор будет
игнорировать, но для людей, читающих исходный код, они могут оказаться полезными.

<!-- Here’s a simple comment: -->
Вот простой комментарий:

```rust
// hello, world
```

<!-- In Rust, the idiomatic comment style starts a comment with two slashes, and the
comment continues until the end of the line. For comments that extend beyond a
single line, you’ll need to include `//` on each line, like this: -->
В Rust однострочный комментарий начинается с двух косых черт, и продолжается до
конца строки. Для комментариев, которые выходят за пределы одной строки, вам
необходимо включить `//` в каждую строку, например так:

```rust
// So we’re doing something complicated here, long enough that we need
// multiple lines of comments to do it! Whew! Hopefully, this comment will
// explain what’s going on.
```

<!-- Comments can also be placed at the end of lines containing code: -->
Комментарии также могут быть размещены в конце строк, содержащих код:

<!-- <span class="filename">Filename: src/main.rs</span> -->
<span class="filename">Имя файла: src/main.rs</span>

```rust
{{#rustdoc_include ../listings/ch03-common-programming-concepts/no-listing-24-comments-end-of-line/src/main.rs}}
```

<!-- But you’ll more often see them used in this format, with the comment on a
separate line above the code it’s annotating: -->
Но чаще вы будете видеть их в таком формате, с комментарием в отдельной строке
над кодом, который он комментирует:

<!-- <span class="filename">Filename: src/main.rs</span> -->
<span class="filename">Имя файла: src/main.rs</span>

```rust
{{#rustdoc_include ../listings/ch03-common-programming-concepts/no-listing-25-comments-above-line/src/main.rs}}
```

<!-- Rust also has another kind of comment, documentation comments, which we’ll
discuss in the “Publishing a Crate to Crates.io” section of Chapter 14. -->
В Rust также есть другой вид комментариев - комментарии к документации,
которые мы обсудим в разделе “Публикация крейта в Crates.io” Главы 14.
