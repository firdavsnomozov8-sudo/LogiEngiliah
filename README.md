# LogiEnglish AI — Python starter

Python loyihasi: FastAPI web ilova + aiogram Telegram bot + SQLite/SQLAlchemy.

## Kiritilgan funksiyalar
- LogiEnglish AI nomi va yangi tariflar
- English / IELTS / Logistics bo‘limlari uchun boshlang‘ich web sahifa
- To‘lov chekini yuklash (admin qo‘lda tekshiradi)
- Admin API orqali to‘lovni tasdiqlash/rad etish
- IELTS va logistika obunasini tasdiqlashdan keyin muddatga ochish
- Telegram `/start` va Web App tugmasi
- Ixtiyoriy AI Tutor moduliga OpenAI API ulash
- `/health` health-check endpoint

## Tariflar
- Logistika: 49 990 so‘m / oy
- Kunlik limit qo‘shimchasi: 14 990 so‘m
- IELTS: 59 000 so‘m / oy
- IELTS: 219 000 so‘m / 3 oy

## Kompyuterda ishga tushirish
1. Python 3.11+ o‘rnating.
2. ZIPni oching va loyiha papkasiga kiring.
3. Virtual muhit yarating:
   `python -m venv .venv`
4. Faollashtiring:
   Windows: `.venv\\Scripts\\activate`
   Linux/macOS: `source .venv/bin/activate`
5. Kutubxonalar:
   `pip install -r requirements.txt`
6. `.env.example` faylidan `.env` nusxa yarating va kerakli qiymatlarni kiriting.
7. Web:
   `python run.py`
   Brauzerda `http://127.0.0.1:8000` oching.
8. Bot alohida terminalda:
   `python bot.py`

## Admin to‘lov boshqaruvi
`SECRET_KEY` ni o‘zgartiring. Kutilayotgan to‘lovlar:
`GET /admin/payments?admin_key=YOUR_SECRET`
Tasdiqlash:
`POST /admin/payments/{id}/approve?admin_key=YOUR_SECRET`
Rad etish:
`POST /admin/payments/{id}/reject?admin_key=YOUR_SECRET`

Admin API hozircha oddiy secret-key bilan himoyalangan; production uchun autentifikatsiya, HTTPS va audit log qo‘shish kerak.

## Muhim cheklovlar
Bu ZIP — ishga tushadigan boshlang‘ich Python skeleti, yakuniy tijoriy platforma emas.
- Click/Payme avtomatik to‘lov API integratsiyasi yo‘q; chek qo‘lda ko‘riladi.
- Botdan kelgan to‘lov chekini admin’ga avtomatik forward qilish hali ulanmagan.
- Telegram Web App initData imzosi va foydalanuvchi autentifikatsiyasi production darajasida tekshirilmaydi.
- Kunlik foydalanish limitini o‘lchash va qo‘shimcha limit sarfi hali to‘liq amalga oshirilmagan.
- IELTS darslari, logistika darslari, 600 000+ lug‘at va AI suhbat kontenti to‘liq dataset sifatida kiritilmagan.
- AI Tutor faqat OPENAI_API_KEY qo‘yilganda ishlaydi.
- Railway/Render deploy konfiguratsiyasi boshlang‘ich; real serverga deploy va test bajarilmagan.

Productionga chiqarishdan oldin xavfsizlik, to‘lov provayderlari, Telegram auth, fayl saqlash va obuna qoidalarini yakunlash zarur.
