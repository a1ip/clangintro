###Как вводить и выводить информацию

Операции ввода/вывода в языке Си организованы посредством библиотечных функций (причем их довольно много).

Самый простой механизм ввода - чтение по одному символу из стандартного входного потока (с клавиатуры) с помощью функции `getchar( )`. Она имеет следующий прототип (т.е. описание заголовка):

```c
int getchar(void);
```

Здесь определен тип единственного аргумента (`void`) и тип возвращаемого функцией значения (`int`).

Оператор вида:

```c
х = getchar( );
```

присваивает переменной `х` очередной вводимый символ. Переменная `х` должна иметь символьный или целый тип.

Другая функция - `putchar(х)` выдает значение переменной `x` в стандартный выходной поток (на экран дисплея). Функция `putchar( )` имеет прототип:

```c
int putchar(int);
```

Объявления `getchar( )` и `putchar( )` сделаны в заголовочном файле `stdio.h`, содержащем описания заголовков библиотечных функций стандартного ввода/вывода. Чтобы библиотечные функции стали доступны программе, к ней необходимо подключить данный файл. Подключение осуществляется с помощью директивы препроцессора

```c
#include <stdio.h>
```

помещаемой в начало программы (подробнее см. в разделе 5).

Заметим, что для функции `getchar( )` после выбора символа необходимо нажать клавишу `<Enter>`. Иногда это создает определенные неудобства. Функции `getch( )` и `getche( )` устраняют их. Они имеют следующие прототипы:

```c
int getch(void);
int getche(void);
```

Обе эти функции вводят символ сразу же после нажатия соответствующей клавиши (здесь не надо дополнительно нажимать клавишу `<Enter>`). Отличие между ними заключается в том, что `getche( )` отображает вводимый символ на экране дисплея, а `getch( )` - нет. Прототипы этих функций содержатся в файле `conio.h` (консольный ввод/вывод). Для их использования файл `conio.h` также следует подключить к программе с помощью директивы `#include <conio.h>`.
