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

Yana bir narsa: bularni bilishingiz sizni darhol yaxshi dasturchiga aylantirib qo'ymaydi va bu qoidalar bilan ko'p yil ishlash orqali xatolardan to'liq qutula olmaysiz. Har bir kod bo'lagi birinchi qoralama sifatida boshlanadi, huddi yumshoq loy o'zining yakuniy qattiq shakliga aylanganidek. Va nihoyat, biz boshqalar bilan birgalikda ishlab  kamchiliklarni yo'q qilamiz. Hom qoralamalarni yaxshilayman deb o'zingizni mag'lub etmang! Buni o'rniga kodni o'zini mag'lub eting!

## **O'zgaruvchilar**

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

### Bir xil turdagi o'zgaruvchilar uchun bir xil lug'atdan foydalaning

**Yomon:**

```javascript
getUserInfo();
getClientData();
getCustomerRecord();
```

**Yaxshi:**

```javascript
getUser();
```

**[⬆ tepaga qaytish](#Mundarija)**

### Qidirishga oson nomlardan foydalaning

Biz yozganimizdan ko'ra ko'proq kodni o'qiymiz. Muhimi, o‘qilishi va izlanishi oson kod yozishimiz. Tushunarsiz o'zgaruvchilar yaratishimiz orqali biz kodimizni o'qiydiganlarni qinaymiz. O'zgaruvchilaringiz qidirishga oson bo'lsin. Buddy.js va ESLint kabi vositalar nomsiz konstantalarni aniqlashga yordam beradi.


**Yomon:**
```javascript
// What the heck is 86400000 for?
setTimeout(blastOff, 86400000);
```
**Yaxshi:**
```javascript
// Declare them as capitalized named constants.
const MILLISECONDS_PER_DAY = 60 * 60 * 24 * 1000; //86400000;
setTimeout(blastOff, MILLISECONDS_PER_DAY);
```
**[⬆ tepaga qaytish](#Mundarija)**

### Tushunarli o'zgaruvchilardan foydalaning

**Yomon:**
```javascript
const address = "One Infinite Loop, Cupertino 95014";
const cityZipCodeRegex = /^[^,\\]+[,\\\s]+(.+?)\s*(\d{5})?$/;
saveCityZipCode(
  address.match(cityZipCodeRegex)[1],
  address.match(cityZipCodeRegex)[2]
);
```

**Yaxshi:**
```javascript
const address = "One Infinite Loop, Cupertino 95014";
const cityZipCodeRegex = /^[^,\\]+[,\\\s]+(.+?)\s*(\d{5})?$/;
const [_, city, zipCode] = address.match(cityZipCodeRegex) || [];
saveCityZipCode(city, zipCode);
```
**[⬆ tepaga qaytish](#Mundarija)**

### Hayoliy xaritalashdan saqlaning

**Yomon:**
```javascript
const locations = ["Austin", "New York", "San Francisco"];
locations.forEach(l => {
  doStuff();
  doSomeOtherStuff();
  // ...
  // ...
  // ...
  // Wait, what is `l` for again?
  dispatch(l);
});
```
**Yaxshi:**
```javascript
const locations = ["Austin", "New York", "San Francisco"];
locations.forEach(location => {
  doStuff();
  doSomeOtherStuff();
  // ...
  // ...
  // ...
  dispatch(location);
});
```

**[⬆ tepaga qaytish](#Mundarija)**
