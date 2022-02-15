Original Repository: [ryanmcdermott/clean-code-javascript](https://github.com/ryanmcdermott/clean-code-javascript)

# clean-code-javascript-uz

## Mundarija

1. [Kirish](#kirish)
2. [O'zgaruvchilar](#Ozgaruvchilar)
3. [Funksiyalar](#funksiyalar)
4. [Obyektlar va ma'lumotlar strukturasi](#obyektlar-va-ma'lumotlar-strukturasi)
5. [Klasslar](#klasslar)
6. [SOLID](#solid)
7. [Testlash](#testlash)
8. [Paralellik](#parallellik)
9. [Error'lar bilan ishlash](#error'lar-bilan-ishlash)
10. [Formatlash](#formatlash)
11. [Kommentlar](#kommentlar)
12. [Tarjima](#tarjima) 

## Kirish

![Humorous image of software quality estimation as a count of how many expletives
you shout when reading code](https://www.osnews.com/images/comics/wtfm.jpg)

Robert C. Martinning ["Clean Code"](https://www.amazon.com/Clean-Code-Handbook-Software-Craftsmanship/dp/0132350882) kitobidan dasturiy ta'minot muhandisligi tamoyillari, JavaScript uchun moslashtirildi. Bu uslublar bo'yicha qo'llanma emas.
Bu JavaScript-da [o'qilishga, o'zgartirishga oson va qayta ishlatiladigan](https://github.com/ryanmcdermott/3rs-of-software-architecture) dasturiy ta'minot yaratish bo'yicha qo'llanma.

Bu yerdagi barcha prinsplarga qat'iy rioya qilish shart emas. Bular shunchaki ko'rsatmalar boshqa hech narsa emas, lekin ular
_Clean code_ mualliflari tomonidan ko'p yillik jamoaviy tajriba orqali yig'ilgan.

Bizning dasturiy ta'minot muhandisligi (software engineering) bo'yicha tajribamiz 50 yildan biroz oshgan va biz hali ham ko'p narsalarni o'rganmoqdamiz. Dasturiy ta'minot arxitekturasi arxitekturaning o'zi kabi qari bo'lsa, bizda amal qilish qiyinroq qoidalar bo'lishi mumkin. Hozircha ushbu ko'rsatmalar siz va sizning jamoangiz yozadigan kodining sifatini baholash uchun asosiy mezon bo'lib xizmat qilsin.

Yana bir narsa: bularni bilishingiz sizni darhol yaxshi dasturchiga aylantirmaydi va bu qoidalar bilan ko'p yil ishlash orqali xatolardan to'liq qutulasiz degani emas. Har bir kod bo'lagi birinchi qoralama sifatida boshlanadi, huddi yumshoq loy o'zining yakuniy qattiq shakliga aylanganidek. Va nihoyat, biz boshqalar bilan birgalikda ishlab  kamchiliklarni yo'q qilamiz. Hom qoralamalarni yaxshilayman deb o'zingizni mag'lub etmang. Buni o'rniga kodni o'zini mag'lub eting!

## **Ozgaruvchilar**

### Ma'noli va talaffuz qilishga oson o'zgaruvchi nomlaridan foydalaning

**Yomon:**

```javascript
const yyyymmdstr = moment().format("YYYY/MM/DD");
```

**Yaxshi:**

```javascript
const currentDate = moment().format("YYYY/MM/DD");
```

**[⬆ tepaga qaytish](#Mundarija)**
