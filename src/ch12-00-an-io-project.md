<!-- # An I/O Project: Building a Command Line Program -->
# Проект c вводом-выводом: создание программы для командной строки

<!-- This chapter is a recap of the many skills you’ve learned so far and an
exploration of a few more standard library features. We’ll build a command line
tool that interacts with file and command line input/output to practice some of
the Rust concepts you now have under your belt. -->
Эта глава представляет собой резюме многих навыков, которые вы изучили до сих
пор, и исследование нескольких дополнительных стандартных функций библиотеки.
Мы создадим инструмент командной строки, который взаимодействует с файлами и
вводом/выводом, чтобы попрактиковаться в некоторых концепциях Rust, которые вы
освоили.

<!-- Rust’s speed, safety, single binary output, and cross-platform support make it
an ideal language for creating command line tools, so for our project, we’ll
make our own version of the classic command line tool `grep` (**g**lobally
search a **r**egular **e**xpression and **p**rint). In the simplest use case,
`grep` searches a specified file for a specified string. To do so, `grep` takes
as its arguments a filename and a string. Then it reads the file, finds lines
in that file that contain the string argument, and prints those lines. -->
Скорость, безопасность, единый двоичный вывод и кроссплатформенная поддержка Rust
делают его идеальным языком для создания инструментов командной строки, поэтому
для нашего проекта мы сделаем собственную версию классического инструмента
командной строки `grep` (**g**lobally search a **r**egular **e**xpression and
**p**rint). В простейшем случае `grep` ищет указанный файл для указанной
строки. Для этого `grep` принимает в качестве аргументов имя файла и строку.
Затем он читает файл, находит в этом файле строки, содержащие строковый аргумент,
и печатает эти строки.

<!-- Along the way, we’ll show how to make our command line tool use features of the
terminal that many command line tools use. We’ll read the value of an
environment variable to allow the user to configure the behavior of our tool.
We’ll also print error messages to the standard error console stream (`stderr`)
instead of standard output (`stdout`), so, for example, the user can redirect
successful output to a file while still seeing error messages onscreen. -->
Попробуем показать, как заставить нашу программу использовать функции терминала,
которые используются многими инструментами командной строки. Мы прочтем значение
переменной окружения, чтобы пользователь мог настроить поведение нашего инструмента.
Мы также будем печатать сообщения об ошибках в стандартный поток консоли ошибок
(`stderr`) вместо стандартного вывода (`stdout`), поэтому, например, пользователь
может перенаправить успешный вывод в файл, все еще видя сообщения об ошибках на экране.

<!-- One Rust community member, Andrew Gallant, has already created a fully
featured, very fast version of `grep`, called `ripgrep`. By comparison, our
version of `grep` will be fairly simple, but this chapter will give you some of
the background knowledge you need to understand a real-world project such as
`ripgrep`. -->
Один из участников сообщества Rust, Эндрю Галлант, уже создал полнофункциональную,
очень быструю версию `grep`, называемую `ripgrep`. Для сравнения, наша версия `grep`
будет довольно простой, но эта глава даст вам некоторые базовые знания, необходимые
для понимания реального проекта, такого как `ripgrep`.

<!-- Our `grep` project will combine a number of concepts you’ve learned so far: -->
Наш проект `grep` объединит несколько концепций, которые вы уже изучили:

<!-- * Organizing code (using what you learned about modules in [Chapter 7][ch7]<!--
  ignore ->)
* Using vectors and strings (collections, [Chapter 8][ch8]<!-- ignore ->)
* Handling errors ([Chapter 9][ch9]<!-- ignore ->)
* Using traits and lifetimes where appropriate ([Chapter 10][ch10]<!-- ignore
  ->)
* Writing tests ([Chapter 11][ch11]<!-- ignore ->) -->
* Организация кода (используя то, что вы узнали о модулях в [Главе 7][ch7]<!--
  ignore -->)
* Использование векторов и строк (коллекций, [Глава 8][ch8]<!-- ignore -->)
* Обработка ошибок ([Глава 9][ch9]<!-- ignore -->)
* Использование trait'ов и lifetim'ов, где это уместно ([Глава 10][ch10]<!-- ignore
  -->)
* Написание тестов ([Глава 11][ch11]<!-- ignore -->)

<!-- We’ll also briefly introduce closures, iterators, and trait objects, which
Chapters [13][ch13]<!-- ignore -> and [17][ch17]<!-- ignore -> will cover in
detail. -->
Мы также кратко представим замыкания, итераторы и объекты признаков, которые
будут подробно описаны в Главах [13][ch13]<!-- ignore --> и
[17][ch17]<!-- ignore -->.

[ch7]: ch07-00-managing-growing-projects-with-packages-crates-and-modules.html
[ch8]: ch08-00-common-collections.html
[ch9]: ch09-00-error-handling.html
[ch10]: ch10-00-generics.html
[ch11]: ch11-00-testing.html
[ch13]: ch13-00-functional-features.html
[ch17]: ch17-00-oop.html
