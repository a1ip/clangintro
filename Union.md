###Объединение (***union***)

Объединение - это некоторая переменная, которая может хранить (в разное время) объекты различного типа и размера. В результате появляется возможность работы в одной и той же области памяти с данными различного вида. Для описания объединения используется ключевое слово `union`, а соответствующий синтаксис аналогичен структурам.

Пусть задано определение:

```c
union r {int ir; float fr; char cr;} z;
```

Здесь `ir` имеет размер 2 байта, `fr` - 4 байта, `cr` - 1 байт. Размер переменной `z` будет равен размеру самого большого из трех приведенных типов (т.е. 4 байтам). В один и тот же момент времени `z` может иметь значение только одной из переменных `ir`, `fr` или `cr`.