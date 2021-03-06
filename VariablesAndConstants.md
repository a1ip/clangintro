###Переменные и константы

Все переменные до их использования должны быть определены (объявлены). При этом задается тип, а затем идет список из одной или более переменных этого типа, разделенных запятыми. Например:

```c
int a, b, c;
char x, y;
```

В языке различают понятия объявления переменной и ее определения. Объявление устанавливает свойства объекта: его тип (например, целый), размер (например, 4 байта) и т.д. Определение наряду с этим вызывает выделение памяти (в приведенном примере дано определение переменных).

Переменные можно разделять по строкам произвольным образом, например:

```c
float a;
float b;
```

Переменные в языке Си могут быть инициализированы при их определении:

```c
int a = 25, h = 6;
char g = 'Q', k = 'm';
float r = 1.89;
long double n = r*123;
```

Выясним теперь, где в тексте программы определяются данные. В языке возможны глобальные и локальные объекты. Первые определяются вне функций и, следовательно, доступны для любой из них. Локальные объекты по отношению к функциям являются внутренними. Они начинают существовать, при входе в функцию и уничтожаются после выхода из нее. Ниже показана структура программы на Си и возможные места в программе, где определяются глобальные и локальные объекты.

```c
int a;      /* Определение глобальной переменной */

int function (int b, char c);   /* Объявление функции (т.е. описание
                                   ее заголовка)*/

void main (void)
{                  //Тело программы
     int d, e;           //Определение локальных переменных
     float f;            //Определение локальной переменной
       ...
}
int function (int b, char c) /* Определение функции и формальных
                                параметров (по существу - локальных
                                переменных) b и c */
{                  //Тело функции
     char g;             //Определение локальной переменной
       ...
}
```

Отметим, что выполнение программы всегда начинается с вызова функции `main( )`, которая содержит тело программы. Тело программы, как и тело любой другой функции, помещается между открывающей и закрывающей фигурными скобками.

В языке Си все определения должны следовать перед операторами, составляющими тело функции. В языке Си&nbsp;++ это ограничение снято и определения могут находиться в любом месте программы. Если они сделаны в функции, то соответствующие объекты будут локальными, а если вне функций, то глобальными.

Наряду с переменными в языке существуют следующие виды констант:

*   _вещественные,_ например `123.456`, `5.61е-4`\. Они могут снабжаться суффиксом F (или f), например `123.456F`, `5.61e-4f`;
*   _целые,_ например `125`;
*   _короткие целые,_ в конце записи которых добавляется буква (суффикс) `H` (или `h`), например `275h`, `344H`;
*   _длинные целые,_ в конце записи которых добавляется буква (суффикс) `L` (или `l`), например `361327L`;
*   _беззнаковые,_ в конце записи которых добавляется буква `U` (или `u`), например `62125U`;
*   _восьмеричные,_ в которых перед первой значащей цифрой записывается нуль (`0`), например `071`;
*   _шестнадцатеричные,_ в которых перед первой значащей цифрой записывается пара символов нуль-икс (`0x`), например `0x5F`;
*   _символьные_ - единственный символ, заключенный в одинарные кавычки, например `'О'`, `'2'`, `'.'` и т.п. Символы, не имеющие графического представления, можно записывать, используя специальные комбинации, например `\n` (код 10), `\0` (код 0). Эти комбинации выглядят как два символа, хотя фактически это один символ. Так же можно представить любой двоичный образ одного байта: `'\NNN'`, где `NNN` - от одной до трех восьмеричных цифр. Допускается и шестнадцатеричное задание кодов символов, которое представляется в виде: `'\х2В'`, `'\хЗ6'` и т.п.;
*   _строковые_ - последовательность из нуля символов и более, заключенная в двойные кавычки, например: "Это строковая константа". Кавычки не входят в строку, а лишь ограничивают ее. Строка представляет собой массив из перечисленных элементов, в конце которого помещается байт с символом `'\0'`. Таким образом, число байтов, необходимых для хранения строки, на единицу превышает число символов между двойными кавычками;
*   _константное выражение,_ состоящее из одних констант, которое вычисляется во время трансляции (например: `а=60+301`);
*   типа _long double,_ в конце записи которых добавляется буква `L` (или `l`), например: `1234567.89L`.