# typescript-youtube-cc
Typescript crash course for youtube

определение annotations типов и предположение inference типов

1) Обьекты можно делать через Object literals

const obj: {a: number: b: number}  = {
  a: 10,
  b: 20
}

2) Когда мы при объявлении переменной сразу присваиваем ей значение - указание типа можно опускать. Исключения:
- JSON: let result: {x: string, y: string} = JSON.parse('{"x":"10","y":"20"}'); 
- присваиваем значения позже
- мы присваиваем перееной один тип (true), а ему присваивается другой тип (number) http://joxi.ru/gmv1eDBSq3KR4r

3) Если в функции все аргументы жестко определены, не лобезательно писать какой тип она возвартит, но лучше это делать

4) Деструктуризаия внутри аргументв ф-ции, если параметр - объект
const obj  = {
  a: 10,
  b: 20
}
const logObjr = ({a, b} : {a: number: b: number}) : void  => {console.log(a): console.log(b)};

5) Диструктуризация с определением типов
const age: number = profile.age === const {age} : {age: number} = profile;
const {coords: {lat, lang}} : {coords: {lat: number, lang: number}} = profile;
