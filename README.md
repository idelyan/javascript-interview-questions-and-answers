# javascript-interview-questions-and-answers
Javascript interview questions and answers
Типы данных
1. Что такое переменная в JavaScript и как объявляются переменные?
Переменная в JavaScript - это именованная область памяти, которая используется для хранения данных, которые могут быть изменены во время выполнения программы. Переменные позволяют хранить, изменять и использовать значения в коде.

### Объявление переменных в JavaScript

В JavaScript переменные могут быть объявлены с использованием следующих ключевых слов: `var`, `let` и `const`.

1. **var**
   - Используется для объявления переменной. 
   - До введения `let` и `const` это был единственный способ объявлять переменные.
   - Область видимости переменных, объявленных с `var`, ограничена функцией, в которой они объявлены, или глобальной областью видимости, если объявлены вне функции.
   - Переменные, объявленные с `var`, подвержены поднятию (hoisting), что означает, что их можно использовать до фактического объявления в коде.

   ```javascript
   var x = 10;
   console.log(x); // 10
   ```

2. **let**
   - Введен в ECMAScript 6 (ES6).
   - Область видимости переменных, объявленных с `let`, ограничена блоком, в котором они объявлены (блочная область видимости).
   - Также подвержен поднятию, но в отличие от `var`, нельзя использовать переменную до ее объявления (будет ошибка).

   ```javascript
   let y = 20;
   console.log(y); // 20
   ```

3. **const**
   - Также введен в ECMAScript 6 (ES6).
   - Используется для объявления переменных, которые нельзя переназначить после их инициализации (переменные-константы).
   - Область видимости переменных, объявленных с `const`, также ограничена блоком.
   - Значение переменной, объявленной с `const`, должно быть инициализировано при объявлении.

   ```javascript
   const z = 30;
   console.log(z); // 30
   // z = 40; // Ошибка: Assignment to constant variable.
   ```

### Примеры использования

- Объявление и инициализация переменных:
  ```javascript
  var name = "John"; // с использованием var
  let age = 25;      // с использованием let
  const city = "New York"; // с использованием const
  ```

- Переменные, объявленные с `let` и `const`, имеют блочную область видимости:
  ```javascript
  if (true) {
      let greeting = "Hello";
      console.log(greeting); // "Hello"
  }
  // console.log(greeting); // Ошибка: greeting is not defined

  if (true) {
      const farewell = "Goodbye";
      console.log(farewell); // "Goodbye"
  }
  // console.log(farewell); // Ошибка: farewell is not defined
  ```

- Поднятие переменных (hoisting) для `var`:
  ```javascript
  console.log(a); // undefined
  var a = 5;
  ```

- Поднятие переменных (hoisting) для `let` и `const`:
  ```javascript
  // console.log(b); // Ошибка: Cannot access 'b' before initialization
  let b = 10;

  // console.log(c); // Ошибка: Cannot access 'c' before initialization
  const c = 15;
  ```

### Заключение

Таким образом, `var` подходит для использования в более старых кодах, где он часто использовался, но сейчас рекомендуется использовать `let` и `const` из-за их улучшенной области видимости и контроля над изменяемостью переменных.

2. Какие типы данных существуют в JavaScript?<br>
<p>В JavaScript существует несколько типов данных, которые можно разделить на две категории: примитивные типы и объекты.</p>

### Примитивные типы данных

1. **Number**
   - Представляет как целые числа, так и числа с плавающей запятой.
   - Специальные значения: `Infinity`, `-Infinity`, и `NaN` (Not a Number).
   
   ```javascript
   let num = 42;
   let pi = 3.14;
   let infinity = Infinity;
   let notANumber = NaN;
   ```

2. **String**
   - Представляет последовательность символов.
   - Строки можно заключать в одинарные (`'`), двойные (`"`), или обратные (`\``) кавычки.
   
   ```javascript
   let greeting = "Hello, World!";
   let name = 'John';
   let message = `Hello, ${name}!`;
   ```

3. **Boolean**
   - Представляет два значения: `true` и `false`.
   
   ```javascript
   let isActive = true;
   let isCompleted = false;
   ```

4. **Undefined**
   - Переменная, объявленная, но не инициализированная, имеет значение `undefined`.
   
   ```javascript
   let someVariable;
   console.log(someVariable); // undefined
   ```

5. **Null**
   - Представляет намеренное отсутствие какого-либо объектного значения.
   
   ```javascript
   let emptyValue = null;
   ```

6. **Symbol** (введен в ES6)
   - Представляет уникальное и неизменное значение, часто используется как уникальные идентификаторы для свойств объектов.
   
   ```javascript
   let uniqueId = Symbol("id");
   ```

7. **BigInt** (введен в ES2020)
   - Представляет целые числа произвольной точности.
   
   ```javascript
   let bigIntNumber = 1234567890123456789012345678901234567890n;
   ```

### Объектные типы данных

1. **Object**
   - Коллекция пар ключ-значение. Объекты могут содержать примитивные типы данных, другие объекты и функции.
   
   ```javascript
   let person = {
       name: "Alice",
       age: 30,
       greet: function() {
           console.log("Hello!");
       }
   };
   ```

2. **Array**
   - Упорядоченная коллекция элементов. Массивы являются подтипом объектов и могут содержать значения любых типов.
   
   ```javascript
   let numbers = [1, 2, 3, 4, 5];
   let mixedArray = [1, "two", { key: "value" }, [3, 4]];
   ```

3. **Function**
   - Функции в JavaScript также являются объектами.
   
   ```javascript
   function sayHello() {
       console.log("Hello, World!");
   }

   let greet = function() {
       console.log("Hi there!");
   };
   ```

4. **Date**
   - Специальный объект для работы с датами и временем.
   
   ```javascript
   let now = new Date();
   ```

5. **RegExp**
   - Объект для работы с регулярными выражениями.
   
   ```javascript
   let pattern = /hello/;
   let result = pattern.test("hello world");
   ```

6. **Map**
   - Коллекция ключ-значение, где ключи могут быть любого типа.
   
   ```javascript
   let map = new Map();
   map.set('key', 'value');
   ```

7. **Set**
   - Коллекция уникальных значений любого типа.
   
   ```javascript
   let set = new Set([1, 2, 3, 4, 4]);
   ```

### Примеры использования

- Работа с примитивными типами:
  ```javascript
  let age = 25; // Number
  let name = "Alice"; // String
  let isStudent = false; // Boolean
  let empty = null; // Null
  let notDefined; // Undefined
  let unique = Symbol("id"); // Symbol
  let bigNumber = 1234567890123456789012345678901234567890n; // BigInt
  ```

- Работа с объектами:
  ```javascript
  let user = {
      username: "john_doe",
      password: "12345",
      login: function() {
          console.log("User logged in");
      }
  };
  
  let list = [1, 2, 3, 4, 5];
  
  function greet() {
      console.log("Hello!");
  }
  
  let now = new Date();
  
  let regex = /world/;
  ```

JavaScript предоставляет разнообразные типы данных, что делает его гибким и мощным инструментом для веб-разработки.

3. Объясните разницу между `let`, `const` и `var`.
`let`, `const` и `var` - это ключевые слова, используемые для объявления переменных в JavaScript, но они имеют различные свойства и поведение. Давайте рассмотрим их отличия более подробно:

### `var`

1. **Область видимости:**
   - `var` имеет функциональную область видимости, что означает, что переменная, объявленная с помощью `var` внутри функции, доступна везде внутри этой функции. Если `var` объявлена вне функции, она доступна глобально.

   ```javascript
   function example() {
       var x = 10;
       if (true) {
           var y = 20;
       }
       console.log(x); // 10
       console.log(y); // 20 - доступна, хотя объявлена внутри блока
   }
   example();
   // console.log(x); // Ошибка: x не определена
   ```

2. **Поднятие (hoisting):**
   - Переменные, объявленные с `var`, поднимаются (hoisted) к началу своей области видимости. Это означает, что объявление переменной перемещается вверх к началу функции или глобального контекста.

   ```javascript
   console.log(a); // undefined - переменная поднята, но значение еще не присвоено
   var a = 5;
   ```

3. **Повторное объявление:**
   - Переменные, объявленные с `var`, могут быть повторно объявлены в одной и той же области видимости.

   ```javascript
   var b = 1;
   var b = 2; // допустимо
   console.log(b); // 2
   ```

### `let`

1. **Область видимости:**
   - `let` имеет блочную область видимости, что означает, что переменная, объявленная с `let`, доступна только внутри блока кода (например, внутри фигурных скобок `{}`).

   ```javascript
   if (true) {
       let x = 10;
       console.log(x); // 10
   }
   // console.log(x); // Ошибка: x не определена
   ```

2. **Поднятие (hoisting):**
   - Переменные, объявленные с `let`, также поднимаются, но не инициализируются. Они находятся в "временной мертвой зоне" до тех пор, пока не будет выполнена строка кода, в которой происходит их объявление.

   ```javascript
   // console.log(c); // Ошибка: Cannot access 'c' before initialization
   let c = 5;
   ```

3. **Повторное объявление:**
   - Переменные, объявленные с `let`, не могут быть повторно объявлены в одной и той же области видимости.

   ```javascript
   let d = 1;
   // let d = 2; // Ошибка: Identifier 'd' has already been declared
   ```

### `const`

1. **Область видимости:**
   - `const` имеет блочную область видимости, аналогично `let`.

   ```javascript
   if (true) {
       const x = 10;
       console.log(x); // 10
   }
   // console.log(x); // Ошибка: x не определена
   ```

2. **Поднятие (hoisting):**
   - Переменные, объявленные с `const`, поднимаются, но не инициализируются, и также находятся в "временной мертвой зоне" до тех пор, пока не будет выполнена строка кода, в которой происходит их объявление.

   ```javascript
   // console.log(e); // Ошибка: Cannot access 'e' before initialization
   const e = 5;
   ```

3. **Повторное объявление и присвоение:**
   - Переменные, объявленные с `const`, не могут быть повторно объявлены в одной и той же области видимости.
   - Переменным, объявленным с `const`, должно быть присвоено значение при объявлении, и это значение не может быть изменено (не может быть переназначено). Однако, если `const` указывает на объект, его свойства могут изменяться.

   ```javascript
   const f = 1;
   // f = 2; // Ошибка: Assignment to constant variable

   const obj = { name: "Alice" };
   obj.name = "Bob"; // допустимо
   console.log(obj.name); // "Bob"
   ```

### Краткое резюме

- `var`:
  - Функциональная область видимости.
  - Подвержен поднятию.
  - Можно повторно объявлять.
  
- `let`:
  - Блочная область видимости.
  - Подвержен поднятию, но находится в "временной мертвой зоне".
  - Нельзя повторно объявлять.
  
- `const`:
  - Блочная область видимости.
  - Подвержен поднятию, но находится в "временной мертвой зоне".
  - Нельзя повторно объявлять.
  - Требует инициализации при объявлении.
  - Неизменяемое значение (кроме свойств объектов).

Использование `let` и `const` предпочтительно в современном JavaScript из-за их улучшенной области видимости и контроля над изменением переменных.

4. Что такое замыкание (closure) и для чего оно используется?
### Что такое замыкание (closure)?

Замыкание (closure) в JavaScript — это функция, которая запоминает своё лексическое окружение, то есть контекст, в котором она была создана. Замыкание даёт доступ к внешней функции из внутренней функции. В JavaScript замыкания создаются каждый раз, когда функция создаётся.

### Как работают замыкания?

Когда функция создаётся, она сохраняет ссылку на своё лексическое окружение, что включает переменные из области видимости, в которой функция была объявлена. Это позволяет функции сохранять доступ к этим переменным даже после завершения выполнения внешней функции.

### Пример замыкания:

Рассмотрим пример, чтобы понять, как это работает:

```javascript
function outerFunction() {
    let outerVariable = "I am from outer scope";

    function innerFunction() {
        console.log(outerVariable);
    }

    return innerFunction;
}

const closureFunction = outerFunction();
closureFunction(); // Выведет: "I am from outer scope"
```

В этом примере:
1. `outerFunction` объявляет переменную `outerVariable` и внутреннюю функцию `innerFunction`.
2. `innerFunction` имеет доступ к переменной `outerVariable`, которая находится в лексической области видимости `outerFunction`.
3. `outerFunction` возвращает `innerFunction`.
4. Переменная `closureFunction` хранит ссылку на `innerFunction`.
5. Когда вызывается `closureFunction`, она выводит значение переменной `outerVariable`, даже после того, как `outerFunction` завершила выполнение.

### Применение замыканий:

1. **Инкапсуляция данных**:
   Замыкания позволяют создавать приватные переменные и функции. Это полезно для инкапсуляции данных и методов, которые не должны быть доступны извне.

   ```javascript
   function createCounter() {
       let count = 0;
       return {
           increment: function() {
               count++;
               return count;
           },
           decrement: function() {
               count--;
               return count;
           },
           getCount: function() {
               return count;
           }
       };
   }

   const counter = createCounter();
   console.log(counter.increment()); // 1
   console.log(counter.increment()); // 2
   console.log(counter.decrement()); // 1
   console.log(counter.getCount());  // 1
   ```

2. **Модули**:
   Замыкания часто используются для создания модулей. Модуль — это функция, которая возвращает объект с методами, которые могут взаимодействовать с приватными данными.

   ```javascript
   const Module = (function() {
       let privateVar = "I am private";

       function privateMethod() {
           console.log(privateVar);
       }

       return {
           publicMethod: function() {
               privateMethod();
           }
       };
   })();

   Module.publicMethod(); // Выведет: "I am private"
   // Module.privateMethod(); // Ошибка: privateMethod не определен
   ```

3. **Функции с коллбэками**:
   Замыкания полезны при работе с коллбэками, особенно в асинхронном коде.

   ```javascript
   function delayedGreeting(name) {
       setTimeout(function() {
           console.log("Hello, " + name);
       }, 1000);
   }

   delayedGreeting("Alice"); // Через 1 секунду выведет: "Hello, Alice"
   ```

4. **Создание фабрик функций**:
   Замыкания позволяют создавать функции, конфигурированные определённым образом.

   ```javascript
   function createMultiplier(multiplier) {
       return function(number) {
           return number * multiplier;
       };
   }

   const double = createMultiplier(2);
   const triple = createMultiplier(3);

   console.log(double(5)); // 10
   console.log(triple(5)); // 15
   ```

### Заключение

Замыкание — мощный инструмент в JavaScript, позволяющий создавать функции с доступом к переменным из их лексического окружения, даже после завершения выполнения внешней функции. Это полезно для инкапсуляции данных, создания модулей, работы с коллбэками и многих других сценариев, что делает замыкания одним из ключевых концептов JavaScript.

5. Что такое область видимости (scope) и какие виды областей видимости существуют в JavaScript?
Область видимости (scope) в JavaScript — это контекст, в котором определяются и доступны переменные и функции. Область видимости определяет, где именно в коде можно обращаться к этим переменным и функциям.

### Виды областей видимости в JavaScript:

1. **Глобальная область видимости (Global Scope)**
2. **Функциональная область видимости (Function Scope)**
3. **Блочная область видимости (Block Scope)**
4. **Область видимости модуля (Module Scope)**

#### 1. Глобальная область видимости (Global Scope)

Переменные и функции, объявленные в глобальной области видимости, доступны в любом месте кода.

```javascript
var globalVar = "I'm global";

function globalFunction() {
    console.log(globalVar);
}

globalFunction(); // "I'm global"
console.log(globalVar); // "I'm global"
```

#### 2. Функциональная область видимости (Function Scope)

Переменные, объявленные внутри функции, доступны только внутри этой функции и её вложенных функций. Это свойство относится к переменным, объявленным с помощью `var`.

```javascript
function outerFunction() {
    var functionVar = "I'm local to outerFunction";

    function innerFunction() {
        console.log(functionVar); // "I'm local to outerFunction"
    }

    innerFunction();
    // console.log(functionVar); // "I'm local to outerFunction"
}

outerFunction();
// console.log(functionVar); // Ошибка: functionVar не определена
```

#### 3. Блочная область видимости (Block Scope)

Переменные, объявленные с помощью `let` и `const`, имеют блочную область видимости, что означает, что они доступны только внутри блока кода, где они были объявлены (например, в блоке `if`, `for`, `{}`).

```javascript
if (true) {
    let blockVar = "I'm block-scoped";
    const blockConst = "I'm also block-scoped";
    console.log(blockVar); // "I'm block-scoped"
    console.log(blockConst); // "I'm also block-scoped"
}

// console.log(blockVar); // Ошибка: blockVar не определена
// console.log(blockConst); // Ошибка: blockConst не определена
```

#### 4. Область видимости модуля (Module Scope)

Переменные и функции, объявленные внутри модуля (файл с расширением `.js`, подключаемый через `import`/`export`), имеют модульную область видимости и недоступны за пределами модуля, если они явно не экспортируются.

```javascript
// module.js
export const moduleVar = "I'm in a module";
export function moduleFunction() {
    console.log("I'm a function in a module");
}

// main.js
import { moduleVar, moduleFunction } from './module.js';

console.log(moduleVar); // "I'm in a module"
moduleFunction(); // "I'm a function in a module"
```

### Иерархия областей видимости

Переменные, объявленные в более внутренней области видимости, могут затенять (shadow) переменные с тем же именем из внешней области видимости.

```javascript
let x = "global";

function outer() {
    let x = "outer";

    function inner() {
        let x = "inner";
        console.log(x); // "inner"
    }

    inner();
    console.log(x); // "outer"
}

outer();
console.log(x); // "global"
```

### Заключение

Области видимости (scope) в JavaScript обеспечивают контроль над доступностью переменных и функций, определяя контекст, в котором они могут быть использованы. Глобальная, функциональная, блочная и модульная области видимости помогают организовать код и управлять данными, предотвращая конфликты имен и повышая читаемость и безопасность кода.



Тестирование

React

Node.js

База данных
