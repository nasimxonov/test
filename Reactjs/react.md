# React.js Interview Savollari

## React Asoslari

1. React nima va Virtual DOM qanday ishlaydi?
   React – bu UI yaratish uchun kutubxona. Virtual DOM – bu DOM ning yengil nusxasi bo‘lib, React o‘zgarishlarni avval Virtual DOM da hisoblab, faqat kerakli qismini real DOM ga yangilaydi.

2. JSX nima va u qanday JavaScript ga o‘giriladi?
   JSX – JavaScript ichida HTML yozish imkonini beruvchi sintaksis. U transpilyatsiya jarayonida React.createElement() chaqiruvlariga o‘giriladi.

3. React da Component lar qanday turlari mavjud? Farqlari nima?

Functional Component – oddiy funksiya, hooklardan foydalanadi.

Class Component – class asosida yoziladi, lifecycle methodlarga ega.

4. Props va State o‘rtasidagi asosiy farqlar nimalar?

Props – tashqaridan keladi, o‘zgarmaydi (immutable).

State – komponent ichida saqlanadi va o‘zgarishi mumkin.

5. React.Fragment nima va qachon ishlatiladi?
   <React.Fragment> yoki <> </> – ortiqcha <div> qo‘shmasdan bir nechta elementni qaytarish uchun ishlatiladi.

🔵 Hooks va State Management

6. useState va useReducer hooks lari o‘rtasidagi farq nima?

useState – oddiy state boshqarish uchun.

useReducer – murakkabroq state logikalari uchun, reducer funksiyasi bilan ishlaydi.

7. useEffect hook ning dependency array si qanday ishlaydi?

[] – faqat bir marta ishlaydi (componentDidMount).

[x] – faqat x o‘zgarsa qayta ishlaydi.

yo‘q – har renderda ishlaydi.

8. Custom Hook nima va qanday yaratiladi?
   Custom Hook – o‘z funksiyangizni use bilan boshlab yozish. Hooklarni qayta ishlatish uchun yoziladi.

9. useMemo va useCallback hooks lari qachon va nega ishlatiladi?

useMemo – og‘ir hisoblashlarni optimallashtirish uchun.

useCallback – funksiyani qayta yaratishni oldini olish uchun.

10. useContext hook nima va Context API qanday ishlaydi?
    useContext – Context API orqali global ma’lumotlarni olish uchun ishlatiladi. Context provider bilan ma’lumot yuqoridan pastga uzatiladi.

Component Lifecycle va Rendering

11. React da reconciliation jarayoni qanday ishlaydi?
    Reconciliation – Virtual DOM va oldingi Virtual DOM ni taqqoslab, faqat o‘zgargan qismini real DOM ga qo‘llash jarayoni.

12. React.memo() nima va qachon ishlatiladi?
    React.memo() – functional komponentni memoizatsiya qiladi. Faqat props o‘zgarganda qayta render bo‘ladi.

13. Pure Component nima va Regular Component dan farqi?
    PureComponent – props va state shallow compare qilib, o‘zgarmasa render qilmaydi. Oddiy komponent esa har safar render bo‘ladi.

14. Controlled va Uncontrolled componentlar o‘rtasidagi farq nima?

Controlled – input qiymati React state orqali boshqariladi.

Uncontrolled – input qiymati DOM orqali boshqariladi (ref).

15. React da key prop ning ahamiyati nima?
    key – React ga elementlarni aniqlashda yordam beradi. Uniqe key ishlatilsa, reconciliation samarali ishlaydi.
    Advanced Concepts
16. React da Higher-Order Component (HOC) nima?
    HOC – komponentni argument sifatida olib, yangi komponent qaytaradigan funksiya. Kodni qayta ishlatishda qo‘llanadi.

17. Render Props pattern nima va qanday ishlatiladi?
    Render Props – komponentga funksiya ko‘rinishida prop berib, UI ni moslashuvchan qilish usuli.

18. React da Code Splitting qanday amalga oshiriladi?
    Code splitting – import() yoki React.lazy() orqali kodni bo‘laklarga ajratish, faqat kerak bo‘lganda yuklash.

19. React.lazy() va Suspense qanday ishlaydi?

React.lazy() – komponentni dinamik import qiladi.

Suspense – lazy komponent yuklanayotgan paytda fallback UI ko‘rsatadi.

20. Error Boundary nima va qanday yaratiladi?
    Error Boundary – komponent daraxtida xatolarni tutuvchi class komponent. componentDidCatch va getDerivedStateFromError ishlatiladi.

⚡ State Management va Optimization

21. Redux va Context API ni qachon ishlatish kerak?

Context API – kichik loyihalarda oddiy global state uchun.

Redux – katta loyihalarda murakkab state boshqaruvi uchun.

22. React da performance optimization usullari qanday?

React.memo, useMemo, useCallback ishlatish

Lazy loading

Keylarni to‘g‘ri ishlatish

Virtualization (masalan, react-window)

23. React DevTools dan qanday foydalanish mumkin?
    DevTools – komponent daraxtini, state va propslarni debugging qilish imkonini beradi. Performance tab orqali optimizatsiya tekshiriladi.

24. Server-Side Rendering (SSR) va Client-Side Rendering (CSR) farqi nima?

SSR – sahifa serverda render bo‘ladi (masalan, Next.js). SEO uchun yaxshi.

CSR – sahifa browserda render bo‘ladi (oddiy React). Foydalanuvchi tezkor interaktivlik oladi.

25. React 18 da yangi Concurrent Features (Suspense, Transitions) nima?

Suspense – asinxron yuklanishlarni boshqaradi.

Transitions – katta o‘zgarishlarda UI ni silliq va foydalanuvchi uchun qulay qiladi.
