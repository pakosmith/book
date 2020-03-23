<!-- ## Hello, Cargo! -->
## Привет, Cargo!

<!-- Cargo is Rust’s build system and package manager. Most Rustaceans use this tool
to manage their Rust projects because Cargo handles a lot of tasks for you,
such as building your code, downloading the libraries your code depends on, and
building those libraries. (We call libraries your code needs *dependencies*.) -->
Cargo - это система сборки и пакетный менеджер Rust. Большинство Растаманов
используют этот инструмент для управления своими проектами Rust, потому что
Cargo выполняет множество задач, таких как сборка кода, загрузка
библиотек, от которых зависит ваш код, и сборка этих библиотек.
(Мы называем библиотеки,необходимые вашему коду, *зависимостями*.)

<!-- The simplest Rust programs, like the one we’ve written so far, don’t have any
dependencies. So if we had built the “Hello, world!” project with Cargo, it
would only use the part of Cargo that handles building your code. As you write
more complex Rust programs, you’ll add dependencies, and if you start a project
using Cargo, adding dependencies will be much easier to do. -->
Простейшие программы на Rust, подобные той, что мы недавно написали,
не имеют никаких зависимостей. Так что, когда мы строили проект “Hello, world!”
при помощи Cargo, мы использовали только ту часть Cargo, которая обрабатывает
создание вашего кода. По мере написания более сложных программ на Rust вы
будете добавлять зависимости, и если вы начнете проект с использованием
Cargo, добавление зависимостей будет намного проще.

<!-- Because the vast majority of Rust projects use Cargo, the rest of this book
assumes that you’re using Cargo too. Cargo comes installed with Rust if you
used the official installers discussed in the
[“Installation”][installation]<!-- ignore -> section. If you installed Rust
through some other means, check whether Cargo is installed by entering the
following into your terminal: -->
Поскольку подавляющее большинство проектов Rust используют Cargo, далее в
этой книге предполагается, что вы тоже используете его. Cargo поставляется
с Rust, если вы использовали официальные установщики, описанные в разделе
[«Установка»][installation]<!-- ignore -->. Если вы установили Rust с помощью
каких-либо других средств, проверьте, установлен ли Cargo, введя в свой терминал
следующее:

```text
$ cargo --version
```

<!-- If you see a version number, you have it! If you see an error, such as `command
not found`, look at the documentation for your method of installation to
determine how to install Cargo separately. -->
Если вы видите номер версии, то он у вас есть! Если вы видите ошибку, например
`команда не найдена`, посмотрите документацию для вашего метода установки,
чтобы определить, как отдельно установить Cargo.

<!-- ### Creating a Project with Cargo --> 
### Создание проекта с Cargo

<!-- Let’s create a new project using Cargo and look at how it differs from our
original “Hello, world!” project. Navigate back to your *projects* directory (or
wherever you decided to store your code). Then, on any operating system, run
the following: -->
Давайте создадим новый проект с использованием Cargo и посмотрим,
чем он отличается от нашего оригинального проекта «Hello, world!». Вернитесь
в каталог *projects* (или туда, где вы решили хранить свой код). Затем в любой
операционной системе выполните следующее:

```text
$ cargo new hello_cargo
$ cd hello_cargo
```

<!-- The first command creates a new directory called *hello_cargo*. We’ve named
our project *hello_cargo*, and Cargo creates its files in a directory of the
same name. -->
Первая команда создает новый каталог с именем *hello_cargo*. Мы назвали наш
проект *hello_cargo*, и Cargo создает его файлы в каталоге с тем же именем.

<!-- Go into the *hello_cargo* directory and list the files. You’ll see that Cargo
has generated two files and one directory for us: a *Cargo.toml* file and a
*src* directory with a *main.rs* file inside. -->
Перейдите в каталог *hello_cargo* и просмотрите файлы. Вы увидите, что Cargo
сгенерировал для нас два файла и один каталог: файл *Cargo.toml* и каталог *src*
с файлом *main.rs* внутри. 

<!-- It has also initialized a new Git repository along with a *.gitignore* file.
Git files won’t be generated if you run `cargo new` within an existing Git
repository; you can override this behavior by using `cargo new --vcs=git`. -->
Он также инициализировал новый Git-репозиторий вместе с файлом *.gitignore*.
Git-файлы не будут сгенерированы, если вы запустите `cargo new` в существующем
Git-репозитории; вы можете переопределить это поведение, используя
`cargo new --vcs=git`.

<!-- > Note: Git is a common version control system. You can change `cargo new` to
> use a different version control system or no version control system by using
> the `--vcs` flag. Run `cargo new --help` to see the available options. -->
> Примечание: Git - распространенная система контроля версий. Вы можете задать
> через `cargo new` использование другой системы контроля версий или вовсе без
> системы контроля версий, используя флаг `--vcs`. Запустите `cargo new --help`,
> чтобы увидеть доступные опции.

<!-- Open *Cargo.toml* in your text editor of choice. It should look similar to the
code in Listing 1-2. -->
Откройте *Cargo.toml* в любом текстовом редакторе. Он должен выглядеть примерно так,
как показано в Листинге 1-2.

<!-- <span class="filename">Filename: Cargo.toml</span> -->
<span class="filename">Имя файла: Cargo.toml</span>

```toml
[package]
name = "hello_cargo"
version = "0.1.0"
authors = ["Your Name <you@example.com>"]
edition = "2018"

[dependencies]
```

<!-- <span class="caption">Listing 1-2: Contents of *Cargo.toml* generated by `cargo
new`</span> -->
<span class="caption">Листинг 1-2: Содержимое *Cargo.toml*, сгенерированное `cargo
new`</span>

<!-- This file is in the [*TOML*][toml]<!-- ignore -> (*Tom’s Obvious, Minimal
Language*) format, which is Cargo’s configuration format. -->
Этот файл находится в формате [*TOML*][toml]<!-- ignore --> (*Tom’s Obvious, Minimal
Language*), который является форматом конфигурации Cargo.

[toml]: https://github.com/toml-lang/toml

<!-- The first line, `[package]`, is a section heading that indicates that the
following statements are configuring a package. As we add more information to
this file, we’ll add other sections. -->
Первая строка, `[package]`, является заголовком раздела, который указывает,
что следующие инструкции конфигурируют пакет. По мере добавления дополнительной
информации в этот файл мы будем добавлять и другие разделы.

<!-- The next four lines set the configuration information Cargo needs to compile
your program: the name, the version, who wrote it, and the edition of Rust to
use. Cargo gets your name and email information from your environment, so if
that information is not correct, fix the information now and then save the
file. We’ll talk about the `edition` key in Appendix E. -->
В следующих четырех строках указывается информация о конфигурации, необходимая
Cargo для компиляции вашей программы: имя, версия, кто ее написал, и версия Rust
для использования. Cargo получает ваше имя и адрес электронной почты из вашей среды,
поэтому, если эта информация неверна, исправьте ее сейчас и сохраните файл.
О ключе `edition` мы поговорим в Приложении E.

<!-- The last line, `[dependencies]`, is the start of a section for you to list any
of your project’s dependencies. In Rust, packages of code are referred to as
*crates*. We won’t need any other crates for this project, but we will in the
first project in Chapter 2, so we’ll use this dependencies section then. -->
Последняя строка, `[dependencies]` - начало раздела, где вы можете перечислять
любые зависимости вашего проекта. В Rust пакеты кода называются крейтами(*crates*).
Нам не понадобятся никакие другие крейты для этого проекта, но мы будем использовать
их в первом проекте в Главе 2, поэтому мы будем использовать этот раздел зависимостей.

<!-- Now open *src/main.rs* and take a look: -->
Теперь откройем *src/main.rs* и взглянем:

<!-- <span class="filename">Filename: src/main.rs</span> -->
<span class="filename">Имя файла: src/main.rs</span>

```rust
fn main() {
    println!("Hello, world!");
}
```

<!-- Cargo has generated a “Hello, world!” program for you, just like the one we
wrote in Listing 1-1! So far, the differences between our previous project and
the project Cargo generates are that Cargo placed the code in the *src*
directory, and we have a *Cargo.toml* configuration file in the top directory. -->
Cargo создал программу “Hello, world!” за вас, похожую на ту, которую мы написали в
Листинге 1-1! Пока что различия между нашим предыдущим проектом и проектом,
который генерирует Cargo, заключаются в том, что Cargo поместил код в каталог
*src*, и у нас теперь есть файл конфигурации *Cargo.toml* в верхнем каталоге.

<!-- Cargo expects your source files to live inside the *src* directory. The
top-level project directory is just for README files, license information,
configuration files, and anything else not related to your code. Using Cargo
helps you organize your projects. There’s a place for everything, and
everything is in its place. -->
Cargo ожидает, что ваши исходные файлы будут находиться в каталоге *src*.
Каталог проекта верхнего уровня предназначен только для файлов README,
информации о лицензии, файлов конфигурации и всего, что не связано с вашим кодом.
Использование Cargo поможет вам организовать ваши проекты. Здесь есть место
для всего, и все на своем месте.

<!-- If you started a project that doesn’t use Cargo, as we did with the “Hello,
world!” project, you can convert it to a project that does use Cargo. Move the
project code into the *src* directory and create an appropriate *Cargo.toml*
file. -->
Если вы начали проект без использования Cargo, как мы сделали это с проектом “Hello,
world!”, вы можете преобразовать его в проект, который использует Cargo. Переместите
код проекта в каталог *src* и создайте соответствующий файл *Cargo.toml*.

<!-- ### Building and Running a Cargo Project -->
### Сборка и запуск проекта с Cargo

<!-- Now let’s look at what’s different when we build and run the “Hello, world!”
program with Cargo! From your *hello_cargo* directory, build your project by
entering the following command: -->
Теперь давайте посмотрим, что изменилось, когда мы скомпилировали и запустили
программу “Hello, world!” при помощи Cargo! Соберите свой проект из каталога
*hello_cargo*, введя следующую команду:

```text
$ cargo build
   Compiling hello_cargo v0.1.0 (file:///projects/hello_cargo)
    Finished dev [unoptimized + debuginfo] target(s) in 2.85 secs
```

<!-- This command creates an executable file in *target/debug/hello_cargo* (or
*target\debug\hello_cargo.exe* on Windows) rather than in your current
directory. You can run the executable with this command: -->
Эта команда создает исполняемый файл в *target/debug/hello_cargo* (или
*target\debug\hello_cargo.exe* в Windows), а не в вашем текущем каталоге.
Вы можете запустить исполняемый файл с помощью этой команды:

```text
$ ./target/debug/hello_cargo # or .\target\debug\hello_cargo.exe on Windows
Hello, world!
```

<!-- If all goes well, `Hello, world!` should print to the terminal. Running `cargo
build` for the first time also causes Cargo to create a new file at the top
level: *Cargo.lock*. This file keeps track of the exact versions of
dependencies in your project. This project doesn’t have dependencies, so the
file is a bit sparse. You won’t ever need to change this file manually; Cargo
manages its contents for you. -->
Если все пройдёт успешно, в окне терминала должно появиться `Hello, world!`.
Первый запуск `cargo build` также приводит к тому, что Cargo создает новый файл
на верхнем уровне: *Cargo.lock*. Этот файл отслеживает точные версии зависимостей
в вашем проекте. Наш проект не имеет зависимостей, поэтому этот файл пока пуст.
Вам никогда не нужно будет изменять этот файл вручную; Cargo управляет его
содержимым за вас.

<!-- We just built a project with `cargo build` and ran it with
`./target/debug/hello_cargo`, but we can also use `cargo run` to compile the
code and then run the resulting executable all in one command: -->
Мы только что создали проект с помощью `cargo build` и запустили его с помощью
`./target/debug/hello_cargo`», но мы также можем использовать `cargo run` для
компиляции кода последующего запуска исполняемого файла, объединив два шага
одной командой:

```text
$ cargo run
    Finished dev [unoptimized + debuginfo] target(s) in 0.0 secs
     Running `target/debug/hello_cargo`
Hello, world!
```

<!-- Notice that this time we didn’t see output indicating that Cargo was compiling
`hello_cargo`. Cargo figured out that the files hadn’t changed, so it just ran
the binary. If you had modified your source code, Cargo would have rebuilt the
project before running it, and you would have seen this output: -->
Обратите внимание, что на этот раз мы не увидели вывод, указывающий, что Cargo
компилирует `hello_cargo`. Cargo выяснил, что файлы не изменились, поэтому он
просто запустил двоичный файл. Если бы вы изменили свой исходный код, Cargo
перестроил бы проект перед его запуском, и вы бы увидели этот вывод:

```text
$ cargo run
   Compiling hello_cargo v0.1.0 (file:///projects/hello_cargo)
    Finished dev [unoptimized + debuginfo] target(s) in 0.33 secs
     Running `target/debug/hello_cargo`
Hello, world!
```

<!-- Cargo also provides a command called `cargo check`. This command quickly checks
your code to make sure it compiles but doesn’t produce an executable: -->
Cargo также предоставляет команду под названием `cargo check`. Эта команда
быстро проверяет ваш код, чтобы убедиться, что он компилируется, но не создаёт
исполняемый файл:

```text
$ cargo check
   Checking hello_cargo v0.1.0 (file:///projects/hello_cargo)
    Finished dev [unoptimized + debuginfo] target(s) in 0.32 secs
```

<!-- Why would you not want an executable? Often, `cargo check` is much faster than
`cargo build`, because it skips the step of producing an executable. If you’re
continually checking your work while writing the code, using `cargo check` will
speed up the process! As such, many Rustaceans run `cargo check` periodically
as they write their program to make sure it compiles. Then they run `cargo
build` when they’re ready to use the executable. -->
Почему нам не нужен исполняемый файл? Зачастую `cargo check` выполняется намного
быстрее, чем `cargo build`, поскольку пропускает этап создания исполняемого файла.
Если вы постоянно проверяете свою работу во время написания кода, использование
`cargo check` ускорит процесс! Поэтому многие Растаманы периодически запускают
`cargo check`, когда пишут свою программу, чтобы убедиться, что она компилируется.
Затем они запускают `cargo build`, когда они готовы использовать исполняемый файл.

<!-- Let’s recap what we’ve learned so far about Cargo: -->
Давайте повторим то, что мы узнали о Cargo:

<!-- * We can build a project using `cargo build` or `cargo check`.
* We can build and run a project in one step using `cargo run`.
* Instead of saving the result of the build in the same directory as our code,
  Cargo stores it in the *target/debug* directory. -->
* Мы можем собрать проект, используя `cargo build` или `cargo check`.
* Мы можем собрать и запустить проект за один шаг, используя `cargo run`.
* Вместо сохранения результата сборки в том же каталоге, что и наш код,
Cargo сохраняет его в каталоге *target/debug*.

<!-- An additional advantage of using Cargo is that the commands are the same no
matter which operating system you’re working on. So, at this point, we’ll no
longer provide specific instructions for Linux and macOS versus Windows. -->
Дополнительным преимуществом использования Cargo является то, что команды
одинаковы независимо от того, на какой операционной системе вы работаете.
Итак, с этого момента мы больше не будем предоставлять конкретные инструкции
для Linux и macOS по сравнению с Windows.

<!-- ### Building for Release -->
### Сборка для релиза

<!-- When your project is finally ready for release, you can use `cargo build
--release` to compile it with optimizations. This command will create an
executable in *target/release* instead of *target/debug*. The optimizations
make your Rust code run faster, but turning them on lengthens the time it takes
for your program to compile. This is why there are two different profiles: one
for development, when you want to rebuild quickly and often, and another for
building the final program you’ll give to a user that won’t be rebuilt
repeatedly and that will run as fast as possible. If you’re benchmarking your
code’s running time, be sure to run `cargo build --release` and benchmark with
the executable in *target/release*. -->
Когда ваш проект наконец готов к выпуску, вы можете запустить
`cargo build --release`, чтобы скомпилировать его с оптимизацией. Эта команда
создаст исполняемый файл в *target/release* заместо *target/debug*. Оптимизации
ускоряют выполнение кода Rust, но их включение увеличивает время, необходимое
для компиляции программы. Вот для чего нужны два  профиля: один для разработки,
когда вы хотите быстро и часто пересобирать код, а другой для построения
окончательной программы, которую вы предоставите пользователю и которая не будет
перестраиваться повторно и будет работать так быстро, насколько это возможно.

<!-- ### Cargo as Convention -->
### Cargo как конвенция

<!-- With simple projects, Cargo doesn’t provide a lot of value over just using
`rustc`, but it will prove its worth as your programs become more intricate.
With complex projects composed of multiple crates, it’s much easier to let
Cargo coordinate the build. -->
В простых проектах Cargo не обеспечивает большее преимущество, чем просто использование
`rustc`, но он докажет свою ценность, когда ваши программы станут более сложными.
Сложные проекты, состоящие из нескольких крейтов, позволяют Cargo координировать сборку.

Even though the `hello_cargo` project is simple, it now uses much of the real
tooling you’ll use in the rest of your Rust career. In fact, to work on any
existing projects, you can use the following commands to check out the code
using Git, change to that project’s directory, and build:
Хотя проект `hello_cargo` и прост, теперь он использует большую часть реальных
инструментов, которые вы будете использовать в своей дальнейшей карьере в Rust. 

```text
$ git clone someurl.com/someproject
$ cd someproject
$ cargo build
```

<!-- For more information about Cargo, check out [its documentation]. -->
Для получения дополнительной информации о Cargo, ознакомьтесь с [его документацией].

[его документацией]: https://doc.rust-lang.org/cargo/

<!-- ## Summary -->
## Резюме 

<!-- You’re already off to a great start on your Rust journey! In this chapter,
you’ve learned how to: -->
Вы отлично начали свое путешествие в Rust! В этой главе вы узнали, как:

<!-- * Install the latest stable version of Rust using `rustup`
* Update to a newer Rust version
* Open locally installed documentation
* Write and run a “Hello, world!” program using `rustc` directly
* Create and run a new project using the conventions of Cargo -->
* Установить последнюю стабильную версию Rust, используя `rustup`
* Обновиться до новой версии Rust
* Открыть локально установленную документацию
* Написать и запустить программу “Hello, world!”, используя `rustc` напрямую
* Создайте и запустите новый проект, используя конвенции Cargo

<!-- This is a great time to build a more substantial program to get used to reading
and writing Rust code. So, in Chapter 2, we’ll build a guessing game program.
If you would rather start by learning how common programming concepts work in
Rust, see Chapter 3 and then return to Chapter 2. -->
Настало время для создания более сложных программ, чтобы привыкнуть к чтению
и написанию кода на Rust. Итак, во второй главе мы создадим игру-угадайку. Если
вы хотите начать с изучения общих концепций программирования в Rust,
см. Главу 3, а затем вернитесь к Главе 2.

[installation]: ch01-01-installation.html#installation
