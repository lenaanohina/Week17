# Week 17. Ответы на вопросы.

## 1. Что такое объекты в JavaScript?

В JavaScript объекты - это основа языка. Они представляют собой коллекции свойств(ключ-значение), которые могут содержать различные типы данных, такие как строки, числа, функции и другие объекты.

## 2. Как создать объект в JavaScript?

Объекты создаются при помощи фигурных скобок {}, с помощью конструктора Object(), а также с помощью Object.create().

## 3. Как создать класс в JavaScript?

Для создания класса в JavaScript используются ключевые слова class и constructor. Вот пример создания класса:

```js
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }
}
```

## 4. Как добавить методы в класс?

Чтобы добавить методы в класс, можно определить их внутри блока класса. Вот пример:

```js
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  sayHello() {
    console.log(`Привет, меня зовут ${this.name}!`);
  }
}
```

## 5. Как создать экземпляр класса?

Чтобы создать экземпляр класса, можно использовать оператор new. Вот пример:

```js
let person = new Person("John", 30);
```

## 6. Что выведет код?

```js
const person = {
  name: "Алиса",
  age: 25,
};

console.log(person.name); //Выведет: Алиса
```

## 7. Что выведет код? Почему именно так?

```js
const person = {
  name: "John",
  age: 25,
};

let city = person.city;
city = Moscow;

console.log(person); //Выведет ошибку. Свойство "city" не существует в объекте "person".
```

## 8. Что выведет код? Почему именно так?

```js
class Animal {
  constructor(name) {
    this.name = name;
  }

  sound() {
    console.log("Animal sound");
  }
}

class Dog extends Animal {
  sound() {
    console.log("Woof!");
  }
}

const dog = new Dog("Buddy");

dog.sound(); //Выведет: Woof!
//Потому, что у класса Dog есть метод sound(), который переопределяет метод sound() у родительского класса Animal.
```

## 9. Что выведет код? Почему именно так?

```js
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  introduce() {
    console.log(`Hi, my name is ${this.name} and I'm ${this.age} years old.`);
  }
}

class Student extends Person {
  constructor(name, age, major) {
    super(name, age);
    this.major = major;
  }

  study() {
    console.log(`I'm studying ${this.major}.`);
  }
}

const person = new Person("John", 25);
const student = new Student("Alice", 20, "Computer Science");

const introduceFunc = person.introduce;
introduceFunc(); //Выведет ошибку. Когда introduceFunc() вызывается в этой строке, значение this становится неопределенным и попытка получить доступ к свойству name (this.name) вызывает ошибку.
```

## 10. Что выведет код? Почему именно так?

```js
function sayHello() {
  console.log(`Hello, ${this.name}!`);
}

let name = "Nina";

const person1 = {
  name: "Alice",
  greet: sayHello,
};

const person2 = {
  name: "Bob",
  greet: sayHello,
};

sayHello(); //Hello, undefined!
person1.greet(); //Hello, Alice!
person2.greet(); //Hello, Bob!
//В первом случае при вызове функции sayHello() без контекста (this не указан), this.name будет равно undefined, так как переменная name определена в глобальной области видимости.
//Во втором (также как и в третьем) случае, всё в порядке, т.к. при вызове person1.greet(), контекстом (значением this) является объект person1.
```
