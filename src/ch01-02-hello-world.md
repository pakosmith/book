<!-- ## Hello, World! -->
## Привет, мир!

<!-- Now that you’ve installed Rust, let’s write your first Rust program. It’s
traditional when learning a new language to write a little program that prints
the text `Hello, world!` to the screen, so we’ll do the same here! -->
Теперь, когда вы установили Rust, давайте напишем вашу первую программу на нём.
При изучении нового языка традиционно пишется небольшая программа, которая 
выводит на экран текст `Hello, world!`, Поэтому мы сделаем то же самое здесь!

<!-- > Note: This book assumes basic familiarity with the command line. Rust makes
> no specific demands about your editing or tooling or where your code lives, so
> if you prefer to use an integrated development environment (IDE) instead of
> the command line, feel free to use your favorite IDE. Many IDEs now have some
> degree of Rust support; check the IDE’s documentation for details. Recently,
> the Rust team has been focusing on enabling great IDE support, and progress
> has been made rapidly on that front! -->
> Примечание: Эта книга предполагает базовое знакомство с командной строкой.
> Rust не предъявляет особых требований к вашим инструментам, или к тому,
> где живет ваш код, поэтому, если вы предпочитаете использовать
> интегрированную среду разработки (IDE) вместо командной строки, смело используйте
> вашу любимую IDE. Многие IDE имеют поддержку Rust; уточните это в
> документации к вашей IDE. В последнее время команда Rust сосредоточилась на том,
> чтобы обеспечить хорошую поддержку IDE, и в этой области был достигнут большой прогресс!

<!-- ### Creating a Project Directory -->
### Создание каталога проекта

<!-- You’ll start by making a directory to store your Rust code. It doesn’t matter
to Rust where your code lives, but for the exercises and projects in this book,
we suggest making a *projects* directory in your home directory and keeping all
your projects there. -->
Начнём с создания каталога для хранения вашего кода. Для Rust не имеет значения,
где располагается ваш код, но для упражнений и проектов из этой книги мы предлагаем
создать каталог *projects* в вашем домашнем каталоге и хранить все проекты там.

<!-- Open a terminal and enter the following commands to make a *projects* directory
and a directory for the “Hello, world!” project within the *projects* directory. -->
Откройте терминал и введите следующие команды, чтобы создать каталог *projects* 
и внутри него папку для проекта «Hello, world!».

<!-- For Linux, macOS, and PowerShell on Windows, enter this: -->
Для Linux, macOS и PowerShell на Windows введите следующее:

```text
$ mkdir ~/projects
$ cd ~/projects
$ mkdir hello_world
$ cd hello_world
```

Для командной строки Windows введите это:

```cmd
> mkdir "%USERPROFILE%\projects"
> cd /d "%USERPROFILE%\projects"
> mkdir hello_world
> cd hello_world
```

<!-- ### Writing and Running a Rust Program -->
### Написание и запуск программы на Rust

<!-- Next, make a new source file and call it *main.rs*. Rust files always end with
the *.rs* extension. If you’re using more than one word in your filename, use
an underscore to separate them. For example, use *hello_world.rs* rather than
*helloworld.rs*. -->
Затем создайте новый исходный файл и назовите его *main.rs*. Файлы Rust 
всегда заканчиваются расширением *.rs*. Если в названии файла более одного слова,
используйте подчеркивание, чтобы отделить их. Например, используйте *hello_world.rs*
вместо *helloworld.rs*.

<!-- Now open the *main.rs* file you just created and enter the code in Listing 1-1. -->
Теперь откройте файл *main.rs*, который вы только что создали, и введите код из Листинга 1-1.

<!-- <span class="filename">Filename: main.rs</span> -->
<span class="filename">Имя файла: main.rs</span>

```rust
fn main() {
    println!("Hello, world!");
}
```

<!-- <span class="caption">Listing 1-1: A program that prints `Hello, world!`</span> -->
<span class="caption">Листинг 1-1: программа, которая печатает `Hello, world!`</span>

<!-- Save the file and go back to your terminal window. On Linux or macOS, enter
the following commands to compile and run the file: -->
Сохраните файл и вернитесь в окно терминала. В Linux или macOS введите следующие
команды для компиляции и запуска программы:

```text
$ rustc main.rs
$ ./main
Hello, world!
```

<!-- On Windows, enter the command `.\main.exe` instead of `./main`: -->
В Windows введите команду `.\main.exe` вместо `./main`:

```powershell
> rustc main.rs
> .\main.exe
Hello, world!
```

<!-- Regardless of your operating system, the string `Hello, world!` should print to
the terminal. If you don’t see this output, refer back to the
[“Troubleshooting”][troubleshooting]<!-- ignore -> part of the Installation
section for ways to get help. -->
Вне зависимоти от вашей операционной системы, в окне терминала должна появиться
строка `Hello, world!`. Если этого не произошло, вернитесь к части 
[“Устранение неполадок”][troubleshooting] <!-- ignore --> раздела «Установка»
для получения помощи.

<!-- If `Hello, world!` did print, congratulations! You’ve officially written a Rust
program. That makes you a Rust programmer—welcome! -->
Если вы увидели строку `Hello, world!`, поздравляем! Вы официально написали программу
на Rust. Это делает вас программистом Rust - добро пожаловать!

<!-- ### Anatomy of a Rust Program -->
### Анализ программы

<!-- Let’s review in detail what just happened in your “Hello, world!” program.
Here’s the first piece of the puzzle: -->
Давайте подробно рассмотрим, что только что произошло в вашей программе “Hello, world!”.
Вот первый кусочек этого пазла:

```rust
fn main() {

}
```

<!-- These lines define a function in Rust. The `main` function is special: it is
always the first code that runs in every executable Rust program. The first
line declares a function named `main` that has no parameters and returns
nothing. If there were parameters, they would go inside the parentheses, `()`. -->
Эти строки объявляют функцию в Rust. Функция `main` является особенной:
в ней расположен код, который выполняется в первую очередь при запуске каждой исполняемой
программы на Rust. Первая строка объявляет функцию с именем `main`, которая не имеет
параметров и ничего не возвращает. Если бы там были параметры, они были бы заключены
в круглые скобки, `()`.

<!-- Also, note that the function body is wrapped in curly brackets, `{}`. Rust
requires these around all function bodies. It’s good style to place the opening
curly bracket on the same line as the function declaration, adding one space in
between. -->
Также обратите внимание на то, что тело функции заключено в фигурные скобки, `{}`.
Rust требует, чтобы тела всех функций были заключены в фигурные скобки.
Рекомендуется размещать открывающую фигурную скобку на той же строке, что и
объявление функции, разделяя их одним пробелом.

<!-- At the time of this writing, an automatic formatter tool called `rustfmt` is
under development. If you want to stick to a standard style across Rust
projects, `rustfmt` will format your code in a particular style. The Rust team
plans to eventually include this tool with the standard Rust distribution, like
`rustc`. So depending on when you read this book, it might already be installed
on your computer! Check the online documentation for more details. -->
На момент написания этой статьи автоматический инструмент форматирования `rustfmt`
находится в стадии разработки. Если вы хотите придерживаться стандартного стиля
в проектах Rust, `rustfmt` отформатирует ваш код в определенном стиле. Команда
Rust планирует со временем включить этот инструмент в стандартный дистрибутив Rust,
например `rustc`. Таким образом, в зависимости от того, когда вы читаете эту книгу,
`rustfmt` уже может быть установлен на вашем компьютере! Для получения более подробной
информации ознакомьтесь с онлайн-документацией.

<!-- Inside the `main` function is the following code: -->
В функции `main` находится следующий код: 

```rust
    println!("Hello, world!");
```

<!-- This line does all the work in this little program: it prints text to the
screen. There are four important details to notice here. First, Rust style is
to indent with four spaces, not a tab. -->
Эта строка выполняет всю работу в нашей маленькой программе: она выводит текст
на экран. Здесь нужно отметить четыре важные детали. Во-первых, стиль Rust
требует делать отступы, состоящие из четырех пробелов, а не табуляции.

<!-- Second, `println!` calls a Rust macro. If it called a function instead, it
would be entered as `println` (without the `!`). We’ll discuss Rust macros in
more detail in Chapter 19. For now, you just need to know that using a `!`
means that you’re calling a macro instead of a normal function. -->
Во-вторых, `println!` вызывает макрос Rust. Если бы мы хотели вызвать
функцию вместо этого, мы бы ввели `println` (без `!`). Мы обсудим макросы более
подробно в Главе 19. А пока вам просто нужно знать, что вызов с `!` означает,
что вы вызываете макрос вместо обычной функции.

<!-- Third, you see the `"Hello, world!"` string. We pass this string as an argument
to `println!`, and the string is printed to the screen. -->
В-третьих, вы видите строку `"Hello, world!"`. Мы передаем эту строку в качестве
аргумента `println!`, и строка выводится на экран.

<!-- Fourth, we end the line with a semicolon (`;`), which indicates that this
expression is over and the next one is ready to begin. Most lines of Rust code
end with a semicolon. -->
В-четвертых, мы заканчиваем строку точкой с запятой (`;`), которая указывает на то,
что данное выражение закончено и следующее готово к началу. Большинство строк кода
Rust заканчиваются точкой с запятой.

### Compiling and Running Are Separate Steps

You’ve just run a newly created program, so let’s examine each step in the
process.

Before running a Rust program, you must compile it using the Rust compiler by
entering the `rustc` command and passing it the name of your source file, like
this:

```text
$ rustc main.rs
```

If you have a C or C++ background, you’ll notice that this is similar to `gcc`
or `clang`. After compiling successfully, Rust outputs a binary executable.

On Linux, macOS, and PowerShell on Windows, you can see the executable by
entering the `ls` command in your shell. On Linux and macOS, you’ll see two
files. With PowerShell on Windows, you’ll see the same three files that you
would see using CMD.

```text
$ ls
main  main.rs
```

With CMD on Windows, you would enter the following:

```cmd
> dir /B %= the /B option says to only show the file names =%
main.exe
main.pdb
main.rs
```

This shows the source code file with the *.rs* extension, the executable file
(*main.exe* on Windows, but *main* on all other platforms), and, when using
Windows, a file containing debugging information with the *.pdb* extension.
From here, you run the *main* or *main.exe* file, like this:

```text
$ ./main # or .\main.exe on Windows
```

If *main.rs* was your “Hello, world!” program, this line would print `Hello,
world!` to your terminal.

If you’re more familiar with a dynamic language, such as Ruby, Python, or
JavaScript, you might not be used to compiling and running a program as
separate steps. Rust is an *ahead-of-time compiled* language, meaning you can
compile a program and give the executable to someone else, and they can run it
even without having Rust installed. If you give someone a *.rb*, *.py*, or
*.js* file, they need to have a Ruby, Python, or JavaScript implementation
installed (respectively). But in those languages, you only need one command to
compile and run your program. Everything is a trade-off in language design.

Just compiling with `rustc` is fine for simple programs, but as your project
grows, you’ll want to manage all the options and make it easy to share your
code. Next, we’ll introduce you to the Cargo tool, which will help you write
real-world Rust programs.

[troubleshooting]: ch01-01-installation.html#troubleshooting
