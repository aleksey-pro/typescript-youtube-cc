# typescript-youtube-cc

https://www.youtube.com/watch?v=nyIpDs2DJ_c&list=PLqKQF2ojwm3nW-cQeSER79xdpK3vL5c-g&index=3

Typescript crash course for youtube

определение annotations типов и предположение inference типов

1) Обьекты можно делать через Object literals
```
const obj: {a: number: b: number}  = {
  a: 10,
  b: 20
}
```

2) Когда мы при объявлении переменной сразу присваиваем ей значение - указание типа можно опускать. Исключения:

- JSON: `let result: {x: string, y: string} = JSON.parse('{"x":"10","y":"20"}')`;
- присваиваем значения позже
- мы присваиваем перееной один тип (true), а ему присваивается другой тип (number) http://joxi.ru/gmv1eDBSq3KR4r
- присваиваем массиву пустой массив - `const arr = []`;

3) Если в функции все аргументы жестко определены, не обезательно писать какой тип она возвартит, но лучше это делать

4) Деструктуризаия внутри аргументв ф-ции, если параметр - объект
```
const obj  = {
  a: 10,
  b: 20
}
const logObjr = ({a, b} : {a: number: b: number}) : void  => {console.log(a): console.log(b)};
```

5) Деструктуризация с определением типов
```
const age: number = profile.age === const {age} : {age: number} = profile;
const {coords: {lat, lang}} : {coords: {lat: number, lang: number}} = profile;
```

6) При работе с массивами - ts знает какие типы внутри, поэтому при извлечении элемента из массива  - он знает типа этого элемента (предложит нужные методы), и не даст добавить в массив элемент другого типа

7) определяем tuple - `type Drink = [string, boolean, number]`;

8) в constructor класса можно передать аргумент, который передается при вызове инстанса. 
`constructor(public color: string) {...}`

9) Интерфейс используется когда мы в параметры подаем разные классы, у которых есть общие свойства для валидации

10) Типизация Call
function call<TS extends any[], R>(fn: (...args: TS) => R, ..args: TS): R {
  return fn(...args)
}

11) Unknown - как и any, но не может быть переопределен при использовании в любой другой тип. Кроме как в any. Используется 

12) Partial - повзоляет создать тип из другого типа, где все значения будут опциональными
type1 = {a: b, c: d}, type2 = Partial<type1> = {a?: b, c?: d}}
  
13) <reference lib=""> - для полключения типов для библиотек полифиллов. Чтобы не конфликтовало с основнми definitions TS.
  
14) Omit - повзоляет создать тип из другого типа без определенных полей
type1 = {a: b, c: d}, type2 = Omit<type1, 'a'> = {c: d}

15) Дектораторы - добвляют аннтоации.Применяются для св-в, методов, аргументов метода в класссах.
