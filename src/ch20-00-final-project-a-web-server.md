<!-- # Final Project: Building a Multithreaded Web Server -->
# Финальный проект: создание многопоточного веб-сервера

<!-- It’s been a long journey, but we’ve reached the end of the book. In this
chapter, we’ll build one more project together to demonstrate some of the
concepts we covered in the final chapters, as well as recap some earlier
lessons. -->
Это был долгий путь, но мы дошли до конца книги. В этой главе мы вместе
создадим еще один проект, чтобы продемонстрировать некоторые концепции,
которые мы рассмотрели в последних главах, а также повторим некоторые
предыдущие уроки.

<!-- For our final project, we’ll make a web server that says “hello” and looks like
Figure 20-1 in a web browser. -->
Для нашего финального проекта мы создадим веб-сервер, который выводит в
окне веб-браузера “hello” как показано на Рисунке 20-1.

![hello from rust](img/trpl20-01.png)

<!-- <span class="caption">Figure 20-1: Our final shared project</span> -->
<span class="caption">Рисунок 20-1: Наш последний совместный проект</span>

<!-- Here is the plan to build the web server: -->
Вот план по созданию веб-сервера:

<!-- 1. Learn a bit about TCP and HTTP.
2. Listen for TCP connections on a socket.
3. Parse a small number of HTTP requests.
4. Create a proper HTTP response.
5. Improve the throughput of our server with a thread pool. -->
1. Узнать немного о TCP и HTTP.
2. Прослушать TCP соединения на сокете.
3. Разобрать небольшое количество HTTP-запросов.
4. Создать правильный HTTP-ответ.
5. Улучшить пропускную способность нашего сервера с помощью пула потоков.

<!-- But before we get started, we should mention one detail: the method we’ll use
won’t be the best way to build a web server with Rust. A number of
production-ready crates are available on [crates.io](https://crates.io/) that
provide more complete web server and thread pool implementations than we’ll
build. -->
Но прежде чем мы начнем, мы должны упомянуть одну деталь: метод, который мы
будем использовать - не лучший способом создания веб-сервера на Rust. На 
[crates.io](https://crates.io/) доступно несколько готовых к работе крейтов,
которые предоставляют более полную реализацию веб-сервера и пула потоков,
чем та, что мы собираемся создать.

<!-- However, our intention in this chapter is to help you learn, not to take the
easy route. Because Rust is a systems programming language, we can choose the
level of abstraction we want to work with and can go to a lower level than is
possible or practical in other languages. We’ll write the basic HTTP server and
thread pool manually so you can learn the general ideas and techniques behind
the crates you might use in the future. -->
Однако наша цель в этой главе - помочь вам научиться, а не идти легким путем.
Поскольку Rust является языком системного программирования, мы можем выбрать
уровень абстракции, с которым хотим работать, и можем перейти на более низкий
уровень, чем это возможно в других языках. Мы напишем базовый HTTP-сервер и
пул потоков вручную, чтобы вы могли изучить общие идеи и методы, которые
вы можете использовать в ваших крейтах в будущем.
