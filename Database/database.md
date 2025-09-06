# Database Interview Savollari

## Database Asoslari

1. RDBMS va NoSQL database lar o'rtasidagi asosiy farqlar nima?

RDBMS: Relational (jadval asosida), qat'iy schema, SQL ishlatiladi, ACID qo'llab-quvvatlaydi.

NoSQL: Document, Key-Value, Graph yoki Column-based, moslashuvchan schema, tezkor o‘sish va big data uchun qulay, ko‘p hollarda eventual consistency ishlatiladi.

2. ACID xususiyatlari nima va har birini tushuntiring.

A (Atomicity): Transaction butunlay bajariladi yoki umuman bajarilmaydi.

C (Consistency): Har doim valid holatda qoladi.

I (Isolation): Parallel transactionlar bir-biriga xalaqit qilmaydi.

D (Durability): Commit qilingandan keyin ma’lumot doimiy saqlanadi.

3. Database normalization nima? Normal formalar (1NF, 2NF, 3NF) ni tushuntiring.

Normalization – ortiqcha ma’lumotni kamaytirish va data integrityni ta’minlash.

1NF: Har bir ustunda atomar qiymat bo‘lishi kerak.

2NF: 1NF + qisman bog‘lanish yo‘q. (Har bir non-key ustun butun primary keyga bog‘liq bo‘lishi kerak).

3NF: 2NF + transitiv bog‘lanish yo‘q. (Non-key ustun boshqa non-key ustunga bog‘liq bo‘lmasligi kerak).

4. Primary Key, Foreign Key va Unique Key o'rtasidagi farqlar nima?

Primary Key: Har bir row uchun unikal identifikator, NULL bo‘lmaydi.

Foreign Key: Boshqa jadvaldagi primary keyga murojaat qiladi.

Unique Key: Unikal qiymatlar bo‘lishi kerak, lekin NULL bo‘lishi mumkin.

5. Database indexing qanday ishlaydi va nega muhim?

Indexlar ma’lumotlarni tez topish uchun ishlatiladi (odatda B-Tree yoki Hash strukturasi).

Muhimligi: query tez ishlaydi, lekin insert/update sekinlashishi mumkin (chunki index ham yangilanadi).

SQL va Query Optimization

6. JOIN turlari (INNER, LEFT, RIGHT, FULL OUTER) qanday ishlaydi?

INNER JOIN: Ikkala jadvalda mos kelgan rowlarni qaytaradi.

LEFT JOIN: Chap jadvaldagi hamma rowlar + o‘ngdan mos kelganlari.

RIGHT JOIN: O‘ng jadvaldagi hamma rowlar + chapdan mos kelganlari.

FULL OUTER JOIN: Har ikkala jadvaldagi barcha rowlar (mos kelmaganlar ham).

7. WHERE va HAVING clause lari o'rtasidagi farq nima?

WHERE: Guruhlashdan oldin filtering qiladi.

HAVING: Guruhlashdan keyin filtering qiladi (aggregate funksiyalar bilan ishlatiladi).

8. Subquery va JOIN qachon ishlatiladi? Qaysi biri samaraliroq?

Subquery: Bir query ichida boshqa query natijasidan foydalanish.

JOIN: Jadvallarni bog‘lab ishlatish.

Ko‘pincha JOIN samaraliroq, chunki optimizator uni yaxshiroq bajaradi.

9. SQL da aggregate functions (COUNT, SUM, AVG, MAX, MIN) qanday ishlaydi?

COUNT: Nechta row borligini hisoblaydi.

SUM: Qiymatlarni yig‘adi.

AVG: O‘rtacha qiymat.

MAX: Eng katta qiymat.

MIN: Eng kichik qiymat.

10. Database transaction nima va COMMIT, ROLLBACK qanday ishlaydi?

Transaction – SQL amallar ketma-ketligi.

COMMIT: O‘zgarishlarni doimiy saqlaydi.

ROLLBACK: O‘zgarishlarni bekor qiladi.

NoSQL va MongoDB

11. MongoDB da document-based model qanday ishlaydi?

Ma’lumotlar JSON/ BSON hujjatlarida saqlanadi. Har bir hujjat mustaqil, jadvalga o‘xshamaydi.

12. MongoDB da aggregation pipeline nima?

Ma’lumotlarni filterlash, guruhlash, hisoblash, sort qilish uchun ketma-ket bosqichli ishlov berish mexanizmi.

13. MongoDB da sharding va replication o'rtasidagi farq nima?

Replication: Data ko‘paytirib saqlanadi (fault tolerance va high availability uchun).

Sharding: Data qismlarga bo‘linadi va bir nechta serverlarda tarqatiladi (scalability uchun).

14. SQL va NoSQL database larni qachon tanlash kerak?

SQL: Strong consistency, complex queries, relational data uchun.

NoSQL: Big Data, moslashuvchan schema, tezkor yozish/o‘qish, real-time ilovalar uchun.

15. MongoDB da indexlar qanday yaratiladi va turlarini ayting.

db.collection.createIndex({field: 1}) orqali yaratiladi.

Turlari: Single field, Compound, Multikey, Text, Geospatial, Hashed.

Performance va Optimization

16. Database query optimization usullari qanday?

Index ishlatish.

EXPLAIN query orqali tahlil qilish.

Denormalizatsiya kerak bo‘lsa ishlatish.

LIMIT bilan qaytariladigan rowlarni kamaytirish.

Joins va subquerylarni optimallashtirish.

17. N+1 query problem nima va uni qanday hal qilish mumkin?

Muammo: Har bir element uchun alohida query yuborish (N+1 marta).

Yechim: JOIN ishlatish, yoki ORM da eager loading ishlatish.

18. Database connection pooling nima va nega kerak?

Oldindan ochilgan connectionlar to‘plami.

Har safar yangidan ulanish emas, balki mavjudini ishlatadi → tezlik va samaradorlik oshadi.

19. Database caching strategiyalari qanday?

Query natijalarini cache qilish.

Materialized view ishlatish.

Redis/Memcached bilan tezkor cache qilish.

20. Slow query lar qanday aniqlanadi va optimizatsiya qilinadi?

Slow query log orqali aniqlanadi.

EXPLAIN bilan tekshiriladi.

Index qo‘shiladi yoki query qayta yoziladi.

Advanced Concepts

21. Database da deadlock nima va qanday oldini olinadi?

Deadlock – ikkita transaction bir-birini kutib qolishi.

Oldini olish: Locklarni tartibli ishlatish, timeout qo‘yish, transactionlarni kichik qilish.

22. CAP theorem nima va distributed systems ga qanday ta'sir qiladi?

CAP: Consistency, Availability, Partition Tolerance.

Distributed system bir vaqtning o‘zida uchtasini emas, faqat ikkitasini ta’minlay oladi.

23. Database backup va recovery strategiyalari qanday?

Full backup, Incremental backup, Differential backup.

Recovery → Point-in-time recovery, log-based recovery.

24. Database migration nima va qanday tools ishlatiladi?

Migration – schema yoki ma’lumotni bir versiyadan boshqasiga o‘tkazish.

Tools: Flyway, Liquibase, Django ORM migrations, Alembic (SQLAlchemy).

25. ORM (Object-Relational Mapping) ning afzalliklari va kamchiliklari nima?

Afzalliklari: Koding soddalashadi, SQL yozish shart emas, portability.

Kamchiliklari: Performance pasayishi, kompleks querylarni ifodalash qiyin.
