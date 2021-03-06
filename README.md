# Sum-big-numbers-Asm
http://sorokin.github.io/cpp-year2013/task-1.html
<html xmlns="http://www.w3.org/1999/xhtml">
  <head>
    <title>Задание №1</title>
    <meta http-equiv="Content-Type" content="text/html; charset=utf-8"/>
   
  </head>
  <body>
    <h2>Задание №1</h2>
    <p>По адресу <a href="http://github.com/sorokin/cpp-year2013">http://github.com/sorokin/cpp-year2013</a> лежит пример двух программ на
    ассемблере. Программа <span class="codein"><a href="https://github.com/sorokin/cpp-year2013/blob/master/helloasm/hello.asm">hello.asm</a></span> &mdash; это программа выводящая строку "Hello, world". В ней подробно прокомментирована каждая строчка. Программа <span class="codein"><a href="https://github.com/sorokin/cpp-year2013/blob/master/helloasm/add.asm">add.asm</a></span> &mdash; это программа, которая выполняет сложение двух длинных чисел.</p>
    <p>Вам необходимо разобраться в этих примерах и написать на их основе программы выполняющие вычитание и умножение
    беззнаковых длинных чисел.</p>
    <p>Обратите внимание, что приведенные примеры заточены на конкретную архитектуру процессора (x86-64), конкретный ассемблер (NASM)
    и операционную систему (Linux).</p>
    <p>Разрешается писать программы под другие архитектуры, ассемблеры и операционные системы,
    при этом вам придется самим переписать код на нужную архитектуру и разобраться как сделать ввод-вывод. Если вы будете делать программу
    под архитектуру отличную от x86_64 или i386, предварительно согласуйте это со мной.</p>
    <h3>Запуск примеров</h3>
    <p>Для того, чтобы запустить примеры на понадобится любой 64-битный дистрибутив Linux. Чтобы проверить битность вашего дистрибутива,
    можно исполнить команду:</p>
    <div class="codeblock">
    $ uname -m
    </div>
    <p>Если команда выводит <span class="codein">x86_64</span>, то система 64-битная, если <span class="codein">i386</span> или <span class="codein">i686</span> &mdash; 32-битная.</p>
    <p>Для работы нам потребуются следующие инструменты:</p>
    <ul>
      <li>NASM &mdash; собственно сам ассемблер</li>
      <li>GNU Binutils &mdash; пакет программ для работы с бинарными файлами от проекта GNU (нам из них понадобится только <span class="codein">ld</span>)</li>
      <li>GCC &mdash; коллекция компиляторов проекта GNU (нам из них понадобится только драйвер <span class="codein">gcc</span>)</li>
      <li>GDB &mdash; отладчик</li>
      <li>Qt Creator &mdash; IDE</li>
      <li>CMake &mdash; система сборки</li>
      <li>Git &mdash; система контроля версий</li>
    </ul>
    <p>Чтобы установить эти программы (в Debian-based дистрибутивах) необходимо исполнить команду:</p>
    <div class="codeblock">
    $ sudo apt-get install nasm binutils gcc gdb qtcreator cmake git
    </div>
    <p>Чтобы взять исходный код примеров необходимо исполнить команду:</p>
    <div class="codeblock">
    $ git clone https://github.com/sorokin/cpp-year2013.git
    </div>
    <p>После этого в текущем каталоге появится каталог <span class="codein">cpp-year2013</span>. Заходим внутрь:</p>
    <div class="codeblock">
    $ cd cpp-year2013/helloasm
    </div>
    <p>Проверяем, что всё компилируется:</p>
    <div class="codeblock">
    $ cmake .<br/>
    $ make
    </div>
    <p>В текущем каталоге должны появится файлы <span class="codein">hello</span> и <span class="codein">add</span>. Проверяем, что всё работает:</p>
    <div class="codeblock">
    $ ./hello<br/>
    Hello, world!<br/>
    $ ./add<br/>
    10000000000000000000000000000000000000<br/>
    100000000000000000000000000000000000000000000000000000000000000<br/>
    100000000000000000000000010000000000000000000000000000000000000
    </div>
    <p>Чтобы редактировать код в IDE, необходимо запустить Qt Creator:</p>
    <div class="codeblock">
    $ qtcreator
    </div>
    <p>И попытаться открыть файл <span class="codein">helloasm/CMakeLists.txt</span>.</p>
    <p><img class="centered" src="task-1-qtcreator.png" alt="qtcreator"/></p>
    <p>Известная особенность: поскольку мы не создаем корректных стековых фреймов и не генерим dwarf-символов для отладки, то отладчик не может
    корректно показать стек вызовов (видно на скриншоте), по этой же причине иногда не работает Step Over (F10).</p>

  </body>
</html>


