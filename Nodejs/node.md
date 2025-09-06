# Node.js Interview Savollari

## Asosiy Tushunchalar

1. Node.js nima va u qanday ishlaydi?

Node.js – Chrome’ning V8 JavaScript engine’iga asoslangan runtime.

Event-driven, non-blocking I/O modeli bilan ishlaydi. Bu serverlarni yuqori samarali va scalable qiladi.

2. Node.js ning Event Loop tushunchasi nima? Qanday fazalardan iborat?

Event Loop – asinxron kodni boshqaruvchi mexanizm.

Fazalari:

Timers (setTimeout, setInterval)

Pending callbacks

Idle, prepare

Poll (yangi I/O kutish va bajarish)

Check (setImmediate)

Close callbacks

3. process.nextTick() va setImmediate() o'rtasidagi farq nima?

process.nextTick(): Hozirgi faza tugashidan oldin bajariladi.

setImmediate(): Event Loop’ning check fazasida bajariladi.

4. Node.js da Callback Hell nima va uni qanday hal qilish mumkin?

Callback Hell – ichma-ich callbacklar ko‘payib ketib, kod o‘qilmay qolishi.

Yechimlar: Promise, async/await, modularization.

5. Node.js da Buffer nima va qachon ishlatiladi?

Buffer – binar ma’lumotlarni (fayl, stream, TCP soket) saqlash uchun maxsus object.

Masalan, faylni o‘qishda yoki yozishda kerak bo‘ladi.

NPM va Modullar

6. package.json va package-lock.json fayllarining farqi nima?

package.json: Loyihaning dependencies, scriptlar va metadata’si.

package-lock.json: O‘rnatilgan versiyalarni aniq saqlaydi (repeatable install uchun).

7. Node.js da CommonJS va ES6 modullar o'rtasidagi farqlar nimalar?

CommonJS (require, module.exports) – Node.js’ning standart modullar tizimi.

ES6 modules (import, export) – JavaScript standartlari. Tree-shaking va statik analiz qulay.

8. NPM da semantic versioning (semver) qanday ishlaydi?

Format: MAJOR.MINOR.PATCH

MAJOR: Orqaga mos emas o‘zgarishlar.

MINOR: Yangi feature, moslikni buzmaydi.

PATCH: Xatoliklarni tuzatish.

9. Node.js da circular dependency muammosi nima va uni qanday hal qilasiz?

Circular dependency – modul A → B → A tarzida bir-biriga bog‘liq bo‘lsa.

Yechimlar: Kodni refaktor qilish, interface orqali ajratish, dynamic import ishlatish.

10. Global va local NPM paketlar o'rtasidagi farq nima?

Global: Barcha loyihalarda ishlatiladi (-g flag bilan o‘rnatiladi).

Local: Faqat loyiha ichida (node_modules papkasida).

Asinxron Dasturlash

11. Callback, Promise va Async/Await o'rtasidagi farqlar nimalar?

Callback: Funksiya argument sifatida uzatiladi.

Promise: Asinxron natija obyekti (then/catch).

Async/Await: Promise’ni synchronous ko‘rinishda ishlatish.

12. Node.js da Stream lar nima? Stream turlarini sanab bering.

Stream – katta hajmdagi ma’lumotni bo‘lib-bo‘lib qayta ishlash.

Turlari: Readable, Writable, Duplex, Transform.

13. EventEmitter klassi nima va qanday ishlaydi?

EventEmitter – event-based patternni amalga oshiradi.

Listener qo‘shish: .on(event, callback)

Event yuborish: .emit(event)

14. Worker Threads va Cluster modullari o'rtasidagi farq nima?

Worker Threads: Bir jarayon ichida ko‘p oqim ishlatish. CPU-bound vazifalar uchun.

Cluster: Bir nechta Node.js jarayonlari yaratadi. Multi-core CPU’dan foydalanish uchun.

15. Node.js da memory leak sabablari va uni qanday aniqlash mumkin?

Sabablar: Weak reference yo‘qligi, global o‘zgaruvchilar, event listenerlarni o‘chirib yubormaslik.

Aniqlash: process.memoryUsage(), Chrome DevTools, clinic.js.

Express.js va Web Development

16. Middleware nima va Express.js da qanday ishlaydi?

Middleware – request va response o‘rtasida ishlovchi funksiyalar.

Masalan: autentifikatsiya, logging, error handling.

17. Express.js da error handling middleware qanday yoziladi?

Maxsus 4 ta argumentli funksiya:

app.use((err, req, res, next) => {
res.status(500).json({ message: err.message });
});

18. req.params, req.query va req.body o'rtasidagi farq nima?

req.params: URL parametrlari (/user/:id).

req.query: URL query string (?name=Ali).

req.body: Request body (POST, PUT orqali yuborilgan ma’lumot).

19. CORS nima va Express.js da uni qanday sozlash mumkin?

CORS (Cross-Origin Resource Sharing) – boshqa domenlardan request qilishga ruxsat beruvchi mexanizm.

Sozlash: cors paketini ishlatish.

const cors = require('cors');
app.use(cors());

20. Express.js da routing qanday ishlaydi? Route parametrlari nima?

Routing – URL’ga qarab handler tanlash.

Route parametrlari – dinamik qiymatlar (/users/:id).

Xavfsizlik va Performance

21. Node.js ilovalarida SQL injection dan qanday himoyalanish mumkin?

Prepared statements ishlatish.

ORM/Query Builder ishlatish.

User inputni sanitize qilish.

22. JWT (JSON Web Token) nima va qanday ishlaydi?

JWT – user autentifikatsiyasi uchun token.

Header + Payload + Signature’dan iborat.

Server tokenni imzolaydi, client keyin request bilan yuboradi.

23. Node.js da environment variables qanday ishlatiladi va nega muhim?

Configlarni (API keys, DB credentials) kodga kiritmasdan .env faylda saqlash.

process.env.VARIABLE_NAME orqali foydalaniladi.

24. Rate limiting nima va Node.js da qanday implementatsiya qilinadi?

Rate limiting – ma’lum vaqt oralig‘ida request sonini cheklash.

Implementatsiya: express-rate-limit paketi bilan.

25. Node.js ilovasi performance ni qanday monitoring qilish va optimizatsiya qilish mumkin?

Monitoring: PM2, New Relic, Datadog, Node.js profiler.

Optimallashtirish: Caching, clustering, streamlardan foydalanish, async kodni samarali yozish.
