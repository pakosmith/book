<!-- # The Rust Programming Language -->
# Язык программирования Rust

[![Build Status](https://travis-ci.com/rust-lang/book.svg?branch=master)](https://travis-ci.com/rust-lang/book)

<!-- This repository contains the source of "The Rust Programming Language" book. -->
Этот репозиторий содержит исходный код книги «Язык программирования Rust».

<!--[The book is available in dead-tree form from No Starch Press][nostarch].-->
[Книга доступна в бумажном виде от No Starch Press][nostarch].

[nostarch]: https://nostarch.com/rust

<!-- You can also read the book for free online. Please see the book as shipped with
the latest [stable], [beta], or [nightly] Rust releases. Be aware that issues
in those versions may have been fixed in this repository already, as those
releases are updated less frequently. -->
Вы также можете прочитать книгу бесплатно онлайн. Please see the book as shipped with
the latest [stable], [beta], or [nightly] Rust releases. Be aware that issues
in those versions may have been fixed in this repository already, as those
releases are updated less frequently.

[stable]: https://doc.rust-lang.org/stable/book/
[beta]: https://doc.rust-lang.org/beta/book/
[nightly]: https://doc.rust-lang.org/nightly/book/

<!-- See the [releases] to download just the code of all the code listings that appear in the book. -->
Смотрите раздел [releases], чтобы загрузить только код всех листингов, которые появляются в книге.

[releases]: https://github.com/rust-lang/book/releases

<!-- ## Requirements -->
## Требования

<!-- Building the book requires [mdBook], ideally the same 0.3.x version that
rust-lang/rust uses in [this file][rust-mdbook]. To get it: -->
Для сборки книги требуется [mdBook], в идеале той версии, которую
rust-lang/rust использует в [этом файле][rust-mdbook]. Для установки:

[mdBook]: https://github.com/rust-lang-nursery/mdBook
[rust-mdbook]: https://github.com/rust-lang/rust/blob/master/src/tools/rustbook/Cargo.toml

```bash
$ cargo install mdbook --vers [version-num]
```
<!-- ## Building -->
## Сборка

Чтобы собрать книгу, введите:

```bash
$ mdbook build
```

<!-- The output will be in the `book` subdirectory. To check it out, open it in
your web browser. -->
Книга будет лежать в подкаталоге `book`. Чтобы проверить, откройте её в
вашем веб-браузере.

_Firefox:_
```bash
$ firefox book/index.html                       # Linux
$ open -a "Firefox" book/index.html             # OS X
$ Start-Process "firefox.exe" .\book\index.html # Windows (PowerShell)
$ start firefox.exe .\book\index.html           # Windows (Cmd)
```

_Chrome:_
```bash
$ google-chrome book/index.html                 # Linux
$ open -a "Google Chrome" book/index.html       # OS X
$ Start-Process "chrome.exe" .\book\index.html  # Windows (PowerShell)
$ start chrome.exe .\book\index.html            # Windows (Cmd)
```

<!-- To run the tests: -->
Для запуска тестов:

```bash
$ mdbook test
```

<!-- ## Contributing -->
## Внесение своего вклада

<!-- We'd love your help! Please see [CONTRIBUTING.md][contrib] to learn about the
kinds of contributions we're looking for. -->
Мы будем рады вашей помощи! Пожалуйст, просмотрите файл [CONTRIBUTING.md][contrib] чтобы узнать,
как вы можете нам помочь.

[contrib]: https://github.com/rust-lang/book/blob/master/CONTRIBUTING.md

<!-- ### Translations -->
### Переводы

<!-- We'd love help translating the book! See the [Translations] label to join in
efforts that are currently in progress. Open a new issue to start working on
a new language! We're waiting on [mdbook support] for multiple languages
before we merge any in, but feel free to start! --?
Мы будем рады вашей помощи в переводе данной книги. Просмотрите метки [Translations]
чтобы присоединиться к уже ведущейся работе по переводу книги. Откройте новое 
issue чтобы начать работу над новым языком. Мы ждем вашего сообщения в 
[mdbook support] до слияния вашего перевода, но не стесняйтесь начать! 

[Translations]: https://github.com/rust-lang/book/issues?q=is%3Aopen+is%3Aissue+label%3ATranslations
[mdbook support]: https://github.com/rust-lang-nursery/mdBook/issues/5

<!-- ## Spellchecking -->
## Проверка орфографии

<!-- To scan source files for spelling errors, you can use the `spellcheck.sh`
script. It needs a dictionary of valid words, which is provided in
`dictionary.txt`. If the script produces a false positive (say, you used word
`BTreeMap` which the script considers invalid), you need to add this word to
`dictionary.txt` (keep the sorted order for consistency). -->
Чтобы проверить исходные файлы на наличие орфографических ошибок вы 
можете использовать скрипт `spellcheck.sh`. Для этого нужен словарь допустимых 
слов, который предоставляется в `dictionary.txt`. Если скрипт выдает 
ложноположительный результат (скажем, вы использовали слово `BTreeMap`, 
которое скрипт считает недопустимым) , вам нужно добавить это слово в 
`dictionary.txt` (сохраняйте порядок сортировки для согласованности).


