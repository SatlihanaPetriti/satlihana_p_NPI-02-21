

МИНИСТЕРСТВО ОБРАЗОВАНИЯ И НАУКИ РОССИЙСКОЙ ФЕДЕРАЦИИ ФЕДЕРАЛЬНОЕ ГОСУДАРСТВЕННОЕ АВТОНОМНОЕ ОБРАЗОВАТЕЛЬНОЕ УЧРЕЖДЕНИЕ ВЫСШЕГО ОБРАЗОВАНИЯ РОССИЙСКИЙ УНИВЕРСИТЕТ ДРУЖБЫ НАРОДОВ

<u>Факультет физико-математических и естественных наук</u>

<u>Кафедра информационных технологий</u>







​									



​								**ОТЧЕТ по лабораторной работе 4
​								ТЕМА **«Модель гармонических колебаний »
​						**по дисциплине «Математическое моделирование»**













**Выполнил:**
Студент группы НПИбд-02-21
Студенческий билет № 1032205641
Сатлихана Петрити  











**Содержание**

------

[TOC]



------

 Список иллюстраций

​	[Рисунок 1: График модели 1]()

​	[Рисунок 2: График модели 2]()

​	[Рисунок 3: График модели 3]()









#### Цель работы

Изучение и анализе линейного гармонического осциллятора как универсальной модели.

#### Последовательность выполнения работы

##### **Вариант 62**

Постройте фазовый портрет гармонического осциллятора и решение уравнения гармонического осциллятора для следующих случаев :

1. Колебания гармонического осциллятора без затуханий и без действий внешней силы . *x*′′+4.3*x*=0

2. Колебания гармонического осциллятора c затуханием и без действий внешней силы . *x*′′+6*x*′+5=0

3. Колебания гармонического осциллятора c затуханием и под действием внешней силы *x*′′+10*x*′+9*x*=8sin(7*t*)

   На интервале *t*∈[0,80] (шаг 0.05) с начальными условиями x0=0.8, y0=-1.2

   

##### Код 1 & 2 & 3:

###### Колебания гармонического осциллятора без затуханий и без действий внешней силы . *x*′′+4.3*x*=0

```
model lab4
// x'' + g* x' + w^2* x =f(t)
// w -частота
// g -затухание
parameter Real w= sqrt(4.3);
parameter Real g= 0.00;

parameter Real x0= 0.8;
parameter Real y0= -1.2;

Real x(start=x0);
Real y(start=y0);

// правая часть уравнения f(t)
function f 
  input Real t;
  output Real result;
algorithm
  result := 0; //1,2
//result := 8*sin(7*t);
end f;

equation
///Вектор-функция f(t, x)
///для решения системы дифференциальных уравнений
///x' = y(t, x)
///где x - искомый вектор
der(x)= y;
der(y)= -w*w*x - g*y -f(time);
end lab4;

```



![figure 1](C:\Users\Acer\Downloads\ADM\Mm\figure 1.png)

​											Рисунок 1: График модели 1

###### Колебания гармонического осциллятора c затуханием и без действий внешней силы . *x*′′+6*x*′+5=0 

```
model lab4
// x'' + g* x' + w^2* x =f(t)
// w -частота
// g -затухание
parameter Real w= sqrt(5);
parameter Real g= 6;

parameter Real x0= 0.8;
parameter Real y0= -1.2;

Real x(start=x0);
Real y(start=y0);
// правая часть уравнения f(t)
function f 
  input Real t;
  output Real result;
algorithm
  result := 0; //1,2
//result := 8*sin(7*t);
end f;

equation
///Вектор-функция f(t, x)
///для решения системы дифференциальных уравнений
///x' = y(t, x)
///где x - искомый вектор
der(x)= y;
der(y)= -w*w*x - g*y -f(time);
end lab4;

```

![figure 2](C:\Users\Acer\Downloads\ADM\Mm\figure 2.png)

​											Рисунок 2: График модели 2

###### Колебания гармонического осциллятора c затуханием и под действием внешней силы *x*′′+10*x*′+9*x*=8sin(7*t*)

```
model lab4
// x'' + g* x' + w^2* x =f(t)
// w -частота
// g -затухание
parameter Real w= sqrt(9);
parameter Real g= 10;

parameter Real x0= 0.8;
parameter Real y0= -1.2;

Real x(start=x0);
Real y(start=y0);
// правая часть уравнения f(t)
function f 
  input Real t;
  output Real result;
algorithm
 //result := 0; //1,2
  result := 8*sin(7*t);
end f;

equation
///Вектор-функция f(t, x)
///для решения системы дифференциальных уравнений
///x' = y(t, x)
///где x - искомый вектор
der(x)= y;
der(y)= -w*w*x - g*y -f(time);

end lab4;

```

 ![figure 3](C:\Users\Acer\Downloads\ADM\Mm\figure 3.png)
					Рисунок 3: График модели 3

#### Вывод

Я научилaсь анализировать линейный гармонический генератор как универсальную модель.