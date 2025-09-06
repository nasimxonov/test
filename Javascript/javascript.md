# JavaScript Interview Savollari

## JavaScript Asoslari

1. JavaScript da primitive va reference types o'rtasidagi farq nima?

Primitive types: string, number, boolean, null, undefined, symbol, bigint. Qiymat bo‘yicha saqlanadi.

Reference types: object, array, function. Xotirada manzil (reference) orqali saqlanadi.

2. Hoisting nima va u qanday ishlaydi?

Hoisting – JavaScriptda deklaratsiyalar kodning yuqorisiga ko‘tariladi.

var bilan e’lon qilingan o‘zgaruvchilar undefined holatida, function deklaratsiyalari esa to‘liq ko‘tariladi.

3. var, let va const o'rtasidagi farqlar nimalar?

var: function scope, hoisting bilan undefined bo‘ladi, qayta e’lon qilish mumkin.

let: block scope, qayta e’lon qilib bo‘lmaydi, lekin qiymati o‘zgartiriladi.

const: block scope, qayta e’lon va o‘zgartirish mumkin emas.

4. Closure nima va qanday ishlaydi? Misol keltiring.

Closure – funksiya o‘zining tashqi scopeidagi o‘zgaruvchilarga kirish imkoniyatiga ega bo‘lsa.

function outer() {
let count = 0;
return function inner() {
count++;
return count;
};
}
const counter = outer();
console.log(counter()); // 1
console.log(counter()); // 2

5. JavaScript da "this" keyword qanday ishlaydi?

this qiymati funksiyaning chaqirilish usuliga bog‘liq:

Global scope → window (strict mode’da undefined).

Object method ichida → o‘sha object.

Constructor (new bilan) → yangi object.

Arrow function → tashqi scope’dagi this ni oladi.

Functions va Scope

6. Arrow function va regular function o'rtasidagi farqlar nima?

Arrow functionda this, arguments yo‘q, ular tashqi scope’dan meros qilib oladi.

Syntaxi qisqa.

Constructor sifatida ishlatilmaydi.

7. JavaScript da scope turlari qanday va ularning farqi nima?

Global scope: Hammaning kirish imkoni bor.

Function scope: Funksiya ichida e’lon qilingan o‘zgaruvchilar tashqaridan ko‘rinmaydi.

Block scope (let, const bilan): {} ichida cheklangan.

8. IIFE (Immediately Invoked Function Expression) nima va nega ishlatiladi?

IIFE – darhol chaqiriladigan funksiya.

Maqsad: Global scope’ni iflos qilmaslik.

(function() {
console.log("Hello IIFE");
})();

9. Function declaration va function expression o'rtasidagi farq nima?

Function declaration hoisting qilinadi, chaqirishdan oldin yozish mumkin.

Function expression (masalan, const foo = function() {}) hoisting qilinmaydi.

10. JavaScript da currying nima va qanday amalga oshiriladi?

Currying – funksiya bir nechta argument o‘rniga ketma-ket bitta argument qabul qiladigan funksiya qaytaradi.

function add(a) {
return function(b) {
return a + b;
};
}
console.log(add(2)(3)); // 5

Asinxron JavaScript

11. Event Loop qanday ishlaydi? Call Stack, Task Queue, Microtask Queue nima?

Call Stack: Funksiyalar ketma-ket bajariladi.

Task Queue (macrotask): setTimeout, setInterval callbacklari shu yerda turadi.

Microtask Queue: Promise callbacklari shu yerda turadi (priority yuqori).

Event Loop stackni kuzatadi va bo‘shaganda queue’dagi vazifalarni bajaradi.

12. Promise nima va qanday holatlar mavjud?

Promise – kelajakdagi qiymatni ifodalaydi.

Holatlar:

pending – bajarilmoqda.

fulfilled – muvaffaqiyatli.

rejected – xatolik.

13. async/await qanday ishlaydi va Promise dan farqi nima?

async funksiya har doim Promise qaytaradi.

await Promise tugashini kutadi.

Farqi: Kodni soddalashtiradi, “synchronous style” yozish imkonini beradi.

14. Callback hell nima va uni qanday oldini olish mumkin?

Callback hell – ichma-ich callbacklar natijasida kod o‘qilmas bo‘lib qolishi.

Yechim: Promise, async/await ishlatish.

15. Promise.all(), Promise.race(), Promise.allSettled() farqlari nima?

Promise.all(): Hammasi bajarilishini kutadi, biri reject bo‘lsa butun promise reject bo‘ladi.

Promise.race(): Eng birinchi tugagan Promise natijasini qaytaradi.

Promise.allSettled(): Barcha Promise tugashini kutadi (fulfilled yoki rejected).

Objects va Prototypes

16. Prototypal inheritance JavaScript da qanday ishlaydi?

Har bir object **proto** orqali boshqa object’dan meros oladi.

Barcha objectlar oxir-oqibat Object.prototype ga bog‘lanadi.

17. Object.create(), Object.assign() va spread operator farqlari nima?

Object.create(proto): Yangi object yaratadi va berilgan prototypeni o‘rnatadi.

Object.assign(target, source): Bitta objectni boshqasiga copy qiladi.

Spread (...): Object yoki array elementlarini yoyadi.

18. JavaScript da class syntax qanday ishlaydi? (ES6)

ES6 class – syntactic sugar, aslida prototypal inheritance ishlatiladi.

class Person {
constructor(name) {
this.name = name;
}
greet() {
return `Hello ${this.name}`;
}
}

19. Object destructuring va array destructuring qanday ishlaydi?

Object destructuring:

const {name, age} = {name: "Ali", age: 25};

Array destructuring:

const [a, b] = [1, 2];

20. JavaScript da getter va setter lar qanday yaratiladi?

class User {
constructor(name) {
this.\_name = name;
}
get name() {
return this.\_name;
}
set name(newName) {
this.\_name = newName;
}
}

Advanced Concepts

21. JavaScript da memoization nima va qanday implementatsiya qilinadi?

Memoization – natijalarni cache qilib, bir xil argumentlar bilan qayta hisoblashni oldini olish.

function memoizedAdd() {
let cache = {};
return function(n) {
if (cache[n]) return cache[n];
let result = n + 10;
cache[n] = result;
return result;
};
}

22. Debouncing va Throttling o'rtasidagi farq nima?

Debouncing: Oxirgi chaqirilgandan keyin ma’lum vaqt o‘tgach bajaradi (input search).

Throttling: Belgilangan vaqt oralig‘ida faqat bir marta ishlaydi (scroll event).

23. JavaScript da WeakMap va WeakSet nima va qachon ishlatiladi?

WeakMap: Key faqat object bo‘lishi mumkin, garbage collection’da avtomatik tozalanadi.

WeakSet: Faqat objectlar saqlanadi, reference yo‘qolganda avtomatik o‘chadi.

24. JavaScript da Symbol type nima va nega kerak?

Symbol – unique va immutable qiymat. Object keylarini collisiondan saqlash uchun ishlatiladi.

25. JavaScript da Proxy va Reflect API lar qanday ishlaydi?

Proxy: Objectni o‘rab, uni tutib olish imkonini beradi (trap’lar orqali).

Reflect: Proxy bilan ishlash uchun utilit funksiyalar to‘plami.
