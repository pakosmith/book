<!-- # Managing Growing Projects with Packages, Crates, and Modules -->
# Управление растущими проектами с помощью пакетов, крейтов и модулей

<!-- As you write large programs, organizing your code will be important because
keeping track of your entire program in your head will become impossible. By
grouping related functionality and separating code with distinct features,
you’ll clarify where to find code that implements a particular feature and
where to go to change how a feature works. -->
Когда вы будете писать большие программы, организация вашего кода будет иметь
важное значение, потому что отслеживать всю вашу программу в вашей голове станет
невозможным. Группируя связанные функциональные возможности и разделяя код с
различными функциями, вы выясните, где найти код, который реализует определенную
функцию, и куда обратиться, чтобы изменить работу этой функции.

<!-- The programs we’ve written so far have been in one module in one file. As a
project grows, you can organize code by splitting it into multiple modules and
then multiple files. A package can contain multiple binary crates and
optionally one library crate. As a package grows, you can extract parts into
separate crates that become external dependencies. This chapter covers all
these techniques. For very large projects of a set of interrelated packages
that evolve together, Cargo provides workspaces, which we’ll cover in the
[“Cargo Workspaces”][workspaces]<!-- ignore -> section in Chapter 14. -->
Программы, которые мы писали до сих пор, были в одном модуле в одном файле.
По мере роста проекта вы можете организовать код, разбив его на несколько
модулей, а затем и на несколько файлов. Пакет может содержать несколько бинарных
крейтов и, возможно, один библиотечный крейт. По мере роста пакета вы можете
извлекать его части в отдельные крейты, которые становятся внешними зависимостями.
Эта глава охватывает все эти техники. Для очень больших проектов из набора
взаимосвязанных пакетов, которые развиваются вместе, Cargo предоставляет
рабочие пространства, о которых мы расскажем в разделе 
[«Рабочие пространства Cargo»][workspaces]<!-- ignore --> Главы 14.

<!-- In addition to grouping functionality, encapsulating implementation details
lets you reuse code at a higher level: once you’ve implemented an operation,
other code can call that code via the code’s public interface without knowing
how the implementation works. The way you write code defines which parts are
public for other code to use and which parts are private implementation details
that you reserve the right to change. This is another way to limit the amount
of detail you have to keep in your head. -->
В дополнение к группировке функциональности, инкапсуляция деталей реализации
позволяет вам повторно использовать код на более высоком уровне: после того,
как вы реализовали операцию, другой код может вызывать этот код через открытый
интерфейс кода, не зная, как работает реализация. То, как вы пишете код,
определяет, какие части являются общедоступными для использования другим
кодом, а какие - частными деталями реализации, которые вы оставляете за собой
право изменять. Это еще один способ ограничить количество деталей, которые вы
должны держать в голове.

<!-- A related concept is scope: the nested context in which code is written has a
set of names that are defined as “in scope.” When reading, writing, and
compiling code, programmers and compilers need to know whether a particular
name at a particular spot refers to a variable, function, struct, enum, module,
constant, or other item and what that item means. You can create scopes and
change which names are in or out of scope. You can’t have two items with the
same name in the same scope; tools are available to resolve name conflicts. -->
Схожее понятие - это область видимости: вложенная область, в которой
написан код, имеет набор имен, определенных в “области видимости”. При
чтении, написании и компиляции кода программистам и компиляторам необходимо
знать, относится ли конкретное имя в определенном месте к переменной, функции,
структуре, перечислению, модулю, константе или другому элементу и что означает
этот элемент. Вы можете создавать области и решать, какие имена входят или
выходят за их пределы видимости. Вы не можете иметь два предмета с одинаковым
именем в одной и той же области видимости; инструменты доступны для разрешения
конфликтов имен.

<!-- Rust has a number of features that allow you to manage your code’s
organization, including which details are exposed, which details are private,
and what names are in each scope in your programs. These features, sometimes
collectively referred to as the *module system*, include: -->
Rust имеет ряд функций, которые позволяют вам управлять организацией вашего
кода, включая то, какие детали открыты, какие детали являются частными,
и какие имена есть в каждой области в ваших программах. Эти особенности, иногда
совместно называемые *модульной системой*, включают в себя:

<!-- * **Packages:** A Cargo feature that lets you build, test, and share crates
* **Crates:** A tree of modules that produces a library or executable
* **Modules** and **use:** Let you control the organization, scope, and
  privacy of paths
* **Paths:** A way of naming an item, such as a struct, function, or module -->
* **Пакеты:** Особенность Cargo, которая позволяет создавать, тестировать и
обмениваться крейтами
* **Крейты:** Дерево модулей, создающее библиотеку или исполняемый файл
* **Модули** и **use:** Позволяет контролировать организацию кода, область
видимости и конфиденциальность путей
* **Пути:** Способ именования элемента, такого как структура, функция или модуль

<!-- In this chapter, we’ll cover all these features, discuss how they interact, and
explain how to use them to manage scope. By the end, you should have a solid
understanding of the module system and be able to work with scopes like a pro! -->
В этой главе мы рассмотрим все эти функции, обсудим, как они взаимодействуют,
и объясним, как их использовать для управления областью видимости. К концу вы
должны иметь четкое представление о модульной системе и уметь работать с такими
областями как профессионал!

[workspaces]: ch14-03-cargo-workspaces.html
