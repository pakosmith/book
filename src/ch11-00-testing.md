<!-- # Writing Automated Tests -->
# Написание автоматических тестов

<!-- In his 1972 essay “The Humble Programmer,” Edsger W. Dijkstra said that
“Program testing can be a very effective way to show the presence of bugs, but
it is hopelessly inadequate for showing their absence.” That doesn’t mean we
shouldn’t try to test as much as we can! -->
В своем эссе 1972 года “Смиренный программист”, Эдсгер В. Дейкстра сказал,
что “тестирование программы может быть очень эффективным способом показать
наличие ошибок, но безнадежно неадекватно для того, чтобы показать их
отсутствие”. Но это не значит, что мы не должны пытаться проверять столько,
сколько можем!

<!-- Correctness in our programs is the extent to which our code does what we intend
it to do. Rust is designed with a high degree of concern about the correctness
of programs, but correctness is complex and not easy to prove. Rust’s type
system shoulders a huge part of this burden, but the type system cannot catch
every kind of incorrectness. As such, Rust includes support for writing
automated software tests within the language. -->
Корректность в наших программах - это степень, в которой наш код делает то,
что мы намереваемся сделать. Rust разработан с высокой степенью озабоченности
по поводу корректности программ, но корректность сложна и ее нелегко доказать.
Система типов Rust несет огромную часть этого бремени, но она не может уловить
все виды ошибок. Таким образом, Rust поддерживает написание автоматических
программных тестов.

<!-- As an example, say we write a function called `add_two` that adds 2 to whatever
number is passed to it. This function’s signature accepts an integer as a
parameter and returns an integer as a result. When we implement and compile
that function, Rust does all the type checking and borrow checking that you’ve
learned so far to ensure that, for instance, we aren’t passing a `String` value
or an invalid reference to this function. But Rust *can’t* check that this
function will do precisely what we intend, which is return the parameter plus 2
rather than, say, the parameter plus 10 or the parameter minus 50! That’s where
tests come in. -->
В качестве примера, скажем, мы напишем функцию с именем `add_two`, которая добавляет
2 к любому числу, переданному ей. Эта функции принимает целое число в качестве
параметра и возвращает целое число в качестве результата. Когда мы реализуем и
компилируем эту функцию, Rust выполняет все проверки типов и заимствования, которые
вы уже изучили, чтобы убедиться, что, например, мы не передаем значение `String`
или недопустимую ссылку на эту функцию. Но Rust *не может* проверить, что эта функция
будет делать именно то, что мы намереваемся, то есть возвращать параметр плюс 2, а
не, скажем, параметр плюс 10 или параметр минус 50! Вот тут на помощь и приходят тесты.

<!-- We can write tests that assert, for example, that when we pass `3` to the
`add_two` function, the returned value is `5`. We can run these tests whenever
we make changes to our code to make sure any existing correct behavior has not
changed. -->
Мы можем написать тесты, которые проверяют, например, что когда мы передаем `3`
в функцию `add_two`, возвращаемое значение равно `5`. Мы можем запускать эти
тесты всякий раз, когда вносим изменения в наш код, чтобы убедиться, что любое
существующее правильное поведение не изменилось.

<!-- Testing is a complex skill: although we can’t cover every detail about how to
write good tests in one chapter, we’ll discuss the mechanics of Rust’s testing
facilities. We’ll talk about the annotations and macros available to you when
writing your tests, the default behavior and options provided for running your
tests, and how to organize tests into unit tests and integration tests. -->
Тестирование - сложный навык: хоть мы и не можем охватить каждую деталь о том, как
писать хорошие тесты в масштабах одной главы, мы обсудим механизм тестирования Rust.
Мы расскажем об аннотациях и макросах, доступных вам при написании тестов,
поведении и опциях по умолчанию, предоставляемых для выполнения тестов, и о том,
как организовать тесты в модульные тесты и интеграционные тесты.
