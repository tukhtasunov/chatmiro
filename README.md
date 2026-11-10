# Chatmiro — Instagram va Telegram uchun AI sotuv agenti

**Mijoz yozadi — Chatmiro sotadi.** 🌐 [chatmiro.com](https://chatmiro.com)

> Bu repozitoriy loyiha bilan tanishish uchun. Asosiy kod yopiq (private) saqlanadi.

## Muammo

O‘zbekistondagi kichik bizneslar savdosining katta qismi Instagram Direct va Telegram orqali o‘tadi. Do‘kon egasi har bir xabarga o‘zi javob beradi: «narxi qancha?», «bormi?», «yetkazasizmi?». Kechasi va dam olish kunlari kelgan xabarlar javobsiz qoladi, mijoz esa boshqa do‘kondan oladi.

## Yechim

Chatmiro — do‘kon egasining o‘z ma’lumotlari asosida ishlaydigan AI sotuvchi:

1. **Kanal ulanadi** — Instagram Professional akkaunt yoki Telegram bot bir necha bosishda.
2. **Agent o‘rgatiladi** — mahsulotlar, narxlar (aniq yoki oraliq, so‘m yoki $), qoldiq, yetkazib berish va to‘lov shartlari. Excel’dan ko‘chirish mumkin.
3. **Agent sotadi** — har bir xabarga mijoz tilida (o‘zbek, rus, ingliz) javob beradi, ism va telefon oladi, buyurtmani Inbox’ga tushiradi.

## Asosiy imkoniyatlar

| | |
|---|---|
| 🧠 To‘qimaydi | Javobdagi narx, raqam va va’dalar bilimga solishtiriladi; bilmasa — «tekshirib aytaman» deb, savolni egaga yuboradi |
| 📥 Bitta Inbox | Instagram Direct, izohlar va Telegram bir joyda |
| 📚 O‘rganadi | Sotuvchi yozgan javobni tasdiqlasa, agent keyingi safar shunday javob beradi |
| 🧾 Lid yig‘adi | Ism, familiya, telefon, yosh — egasi tanlagan maydonlar |
| ⏸ Nazorat | Bitta tugma bilan agentni to‘xtatish; xabarlar baribir Inbox’ga tushadi |
| 🛡 Admin panel | Platforma bo‘yicha barcha agentlarni yoqish/o‘chirish, statistika |

## Arxitektura

```
Instagram / Telegram / Sayt chati
              │  webhook
              ▼
     Node.js (Express) server
              │
   ┌──────────┴────────────┐
   │  Agent konveyeri       │
   │  1. Bilim yig‘ish      │  ← mahsulotlar, FAQ, egasining matni
   │  2. Gemini (o‘ylash)   │
   │  3. Narx/va’da nazorati│
   │  4. Sifat tekshiruvi   │
   │  5. Lid / operator     │
   └──────────┬────────────┘
              ▼
   Mijozga javob + egasiga Inbox
```

**Stek:** Node.js, Express, Google Gemini, Telegram Bot API, Instagram Graph API (Meta), PM2, Linux VPS.

**Sifat:** 1 800 dan ortiq avtomatik test; deploy faqat barcha testlar o‘tganda serverga chiqadi va avval ma’lumotlar zaxirasi olinadi.

## Asoschi

**Nurmuhammad Tuxtasunov** — Namangan, O‘zbekiston
✉️ info@chatmiro.com · 📞 +998 94 822 25 27
