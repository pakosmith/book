<!-- ## Installation -->
## Установка

<!-- The first step is to install Rust. We’ll download Rust through `rustup`, a
command line tool for managing Rust versions and associated tools. You’ll need
an internet connection for the download. -->
Первым делом необходимо установить Rust. Мы будем загружать Rust через `rustup`,
инструмент командной строки для управления версиями Rust и соответствующими 
инструментами. Тебе понадобится подключение к интернету для загрузки.

<!-- > Note: If you prefer not to use `rustup` for some reason, please see [the Rust
> installation page](https://www.rust-lang.org/tools/install) for other options. -->
> Примечание: Если по какой-либо причине вы предпочитаете не использовать `rustup`, 
> см. [Страница установки Rust](https://www.rust-lang.org/tools/install) 
> для других опций.

<!-- The following steps install the latest stable version of the Rust compiler.
Rust’s stability guarantees ensure that all the examples in the book that
compile will continue to compile with newer Rust versions. The output might
differ slightly between versions, because Rust often improves error messages
and warnings. In other words, any newer, stable version of Rust you install
using these steps should work as expected with the content of this book. -->
Следующие шаги устанавливают последнюю стабильную версию компилятора Rust.
Стабильность Rust гарантирует, что все примеры в книге, которые компилируются, 
будут продолжать компилироваться и с более новыми версиями Rust. Вывод может 
немного отличаться, по причине того, что Rust часто улучшает сообщения об 
ошибках и предупреждения. Другими словами, любая более новая стабильная версия 
Rust, которую вы установите при помощи этих шагов, должна работать в соотвествии 
с описанным в данной книге поведением. 

<!-- > ### Command Line Notation
>
> In this chapter and throughout the book, we’ll show some commands used in the
> terminal. Lines that you should enter in a terminal all start with `$`. You
> don’t need to type in the `$` character; it indicates the start of each
> command. Lines that don’t start with `$` typically show the output of the
> previous command. Additionally, PowerShell-specific examples will use `>`
> rather than `$`. -->
> ### Обозначение командной строки
>
> В этой главе и на протяжении всей книги мы покажем некоторые команды, 
> используемые в терминале. Строки, которые вы должны ввести в терминале, 
> начинаются с `$`. Вам не нужно вводить символ `$` - он указывает на 
> начало каждой команды. Строки, которые не начинаются с `$`, обычно 
> показывают вывод предыдущей команды. Кроме того, в примерах для 
> PowerShell будет использоваться `>`, а не `$`.

<!-- ### Installing `rustup` on Linux or macOS -->
### Установка `rustup` на Linux или macOS

<!-- If you’re using Linux or macOS, open a terminal and enter the following command: -->
Если вы используете Linux или macOS, откройте терминал и введите следующую команду:

```text
$ curl https://sh.rustup.rs -sSf | sh
```

<!-- The command downloads a script and starts the installation of the `rustup`
tool, which installs the latest stable version of Rust. You might be prompted
for your password. If the install is successful, the following line will appear: -->
Команда загружает скрипт и запускает установку инструмента `rustup`, который 
устанавливает последнюю стабильную версию Rust. Вам может быть предложено 
ввести пароль. Если установка прошла успешно, появится следующая строка:

```text
Rust is installed now. Great!
```

<!-- If you prefer, feel free to download the script and inspect it before running
it. -->
Вы также можете просто скачать скрипт и изучить его перед запуском. 

<!-- The installation script automatically adds Rust to your system PATH after your
next login. If you want to start using Rust right away instead of restarting
your terminal, run the following command in your shell to add Rust to your
system PATH manually: -->
Скрипт автоматически добавит Rust в системную переменную PATH после 
следующего входа в систему. Если вы хотите сразу начать использовать Rust, 
не перезапуская терминал, выполните следующую команду в своей оболочке, 
чтобы вручную добавить Rust в системную переменную PATH:

```text
$ source $HOME/.cargo/env
```

<!-- Alternatively, you can add the following line to your *~/.bash_profile*: -->
Также вы можете добавить следующую строку в ваш *~/.bash_profile*:

```text
$ export PATH="$HOME/.cargo/bin:$PATH"
```

<!-- Additionally, you’ll need a linker of some kind. It’s likely one is already
installed, but when you try to compile a Rust program and get errors indicating
that a linker could not execute, that means a linker isn’t installed on your
system and you’ll need to install one manually. C compilers usually come with
the correct linker. Check your platform’s documentation for how to install a C
compiler. Also, some common Rust packages depend on C code and will need a C
compiler. Therefore, it might be worth installing one now. -->
Дополнительно вам понадобится какой-нибудь компоновщик. Возможно, он уже установлен, 
но если вы пытаетесь скомпилировать программу Rust и получаете ошибки, указывающие 
на невозможность выполнения компоновщика, это означает, что компоновщик не установлен 
в вашей системе, и вам нужно будет установить его вручную. Компиляторы C обычно 
поставляются с правильным компоновщиком. Обратитесь к документации вашей платформы, 
чтобы узнать, как установить компилятор Си. Кроме того, некоторые распространенные 
пакеты Rust зависят от C-кода и будут нуждаться в C-компиляторе. Поэтому, возможно, 
стоит установить его сейчас.

<!-- ### Installing `rustup` on Windows -->
### Установка `rustup` на Windows

<!-- On Windows, go to [https://www.rust-lang.org/tools/install][install] and follow
the instructions for installing Rust. At some point in the installation, you’ll
receive a message explaining that you’ll also need the C++ build tools for
Visual Studio 2013 or later. The easiest way to acquire the build tools is to
install [Build Tools for Visual Studio 2019][visualstudio]. The tools are in
the Other Tools and Frameworks section. -->
В Windows перейдите на [https://www.rust-lang.org/tools/install][install] и следуйте
инструкциям по установке Rust. На одном из этапов установки вы получите сообщение о
том, что вам также понадобятся инструменты сборки C++ для Visual Studio 2013 или
более поздней версии. Самый простой способ получить их - это установить
[Инструменты Build Tools для Visual Studio 2019][visualstudio].

[install]: https://www.rust-lang.org/tools/install
[visualstudio]: https://www.visualstudio.com/downloads/#build-tools-for-visual-studio-2019

<!-- The rest of this book uses commands that work in both *cmd.exe* and PowerShell.
If there are specific differences, we’ll explain which to use. -->
Далее в этой книге используются команды, которые работают как в *cmd.exe*, так и в
PowerShell. Если будут конкретные различия, мы объясним, что использовать.

<!-- ### Updating and Uninstalling -->
### Обновление и Удаление

<!-- After you’ve installed Rust via `rustup`, updating to the latest version is
easy. From your shell, run the following update script: -->
После того, как вы установили Rust через `rustup`, обновление до последней версии
становится простым. Запустите следующий скрипт обновления из вашей оболочки:

```text
$ rustup update
```

<!-- To uninstall Rust and `rustup`, run the following uninstall script from your
shell: -->
Чтобы удалить Rust и `rustup`, запустите следующий скрипт удаления из вашей оболочки:

```text
$ rustup self uninstall
```

<!-- ### Troubleshooting -->
### Устранение неполадок

<!-- To check whether you have Rust installed correctly, open a shell and enter this
line: -->
Чтобы проверить, правильно ли установлен Rust, откройте оболочку и введите следующую 
команду:

```text
$ rustc --version
```

<!-- You should see the version number, commit hash, and commit date for the latest
stable version that has been released in the following format: -->
Вы должны увидеть номер версии, хеш коммита и дату коммита для последней 
стабильной версии, представленные в следующем формате:

```text
rustc x.y.z (abcabcabc yyyy-mm-dd)
```

<!-- If you see this information, you have installed Rust successfully! If you don’t
see this information and you’re on Windows, check that Rust is in your `%PATH%`
system variable. If that’s all correct and Rust still isn’t working, there are
a number of places you can get help. The easiest is the #beginners channel on
[the official Rust Discord][discord]. There, you can chat with other Rustaceans
(a silly nickname we call ourselves) who can help you out. Other great
resources include [the Users forum][users] and [Stack Overflow][stackoverflow]. -->
Если вы видите эту информацию, вы успешно установили Rust! Если вы её не
видите и находитесь в Windows, убедитесь, что Rust находится в вашей
системной переменной `%PATH%`. Если все верно и Rust по-прежнему не работает,
есть ряд мест, где вы можете получить помощь. Самый простой способ - канал #beginners 
на [официальном Rust Discord][discord]. Там можно пообщаться с другими Растаманами
(глупое прозвище, которым мы называем себя), которые могут вам помочь.

[discord]: https://discord.gg/rust-lang
[users]: https://users.rust-lang.org/
[stackoverflow]: http://stackoverflow.com/questions/tagged/rust

<!-- ### Local Documentation -->
### Оффлайн документация

<!-- The installation of Rust also includes a copy of the documentation locally, so
you can read it offline. Run `rustup doc` to open the local documentation in
your browser. -->
Установка Rust также включает локальную копию документации, поэтому вы можете 
читать ее в оффлайн режиме. Запустите `rustup doc`, чтобы открыть локальную 
документацию в вашем браузере.

<!-- Any time a type or function is provided by the standard library and you’re not
sure what it does or how to use it, use the application programming interface
(API) documentation to find out! -->
Каждый раз, когда вы встречаете тип или функцию, предоставляемые стандартной библиотекой,
и не уверены, что она делает или как ее использовать, используйте документацию
интерфейса прикладного программирования (API), чтобы узнать это!
