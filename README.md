# `ember` — starter skeleton (Lab 1)
### Виконала: _Донець А.М._

## M1 - Збірка та запуск проєкту
![M1](./demo/screenshot_20260918_204327-region.png)


## M2 - "Коробку" ініційовано нулями
![M2](./demo/screenshot_20260918_222909-region.png)

## M3 - mem_set/mem_get працюють
![M3](./demo/screenshot_20260918_225623-region.png)

## Quit працює
![Quit](./demo/screenshot_20260918_230844-region.png)


## Досліди
### Код дослідів описано в ./excercises, скомпільована у ./excercises/bin

### 1 - sizeof — ширина на цій машині

Отримано типовий х64

```
~/Documents/progamming/lab-01 master*
❯ g++ ./excercises/1.cpp -o ./excercises/bin/1

~/Documents/progamming/lab-01 master*
❯ ./excercises/bin/1
1 4 4 8 8
1 2
```

### 2 - Переповнення: wrap vs UB

Виконалося переповнення максимального значення INT 

_2147483648 + 1 = -2147483648_

_Макссимальне значення + 1 = Мінімальне значення_

```
~/Documents/progamming/lab-01 master*
❯ g++ ./excercises/2.cpp -o ./excercises/bin/2

~/Documents/progamming/lab-01 master*
❯ ./excercises/bin/2
0
-2147483648
```

### 3 - Числа з рухомою комою

Отримано _0.1 + 0.2 != 0.3_ через бінарну неточність представлення чисел в комп'ютері.

0.1 = 0b 0001 1001 1001 1001 1001 ...

0.2 = 0b 0011 0011 0011 0011 0011 ...

0.3 = 0b 0100 1100 1100 1100 1100 ...

Але, через будь-яке округлення бітів в кінці, результат зсувається, тому при порівняні чисел з комою, можливі неточності. Й результат може бути:

0.1 + 0.2 = 0.300000000000....00001 != 0.3

```
~/Documents/progamming/lab-01 master*
❯ g++ ./excercises/3.cpp -o ./excercises/bin/3

~/Documents/progamming/lab-01 master*
❯ ./excercises/bin/3
0.3
false
```

### 4 - Символ — це теж число
Символи перетворюють через ASCII таблицю. 
```
~/Documents/progamming/lab-01 master*
❯ g++ ./excercises/4.cpp -o ./excercises/bin/4

~/Documents/progamming/lab-01 master*
❯ ./excercises/bin/4
65 65 65 A
B
2 2.5
```
![ASCII table](./demo/ascii.png)
