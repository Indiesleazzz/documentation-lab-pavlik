# ⚙️ Встановлення та запуск DormHub

## Що потрібно
| Інструмент | Версія | Для чого |
|---|---|---|
| Java (JDK) | 21+ | серверна частина (Spring Boot) |
| Node.js | 20+ | збирання вебінтерфейсу |
| PostgreSQL | 15+ | база даних |
| Git | будь-яка | отримання коду |
| Браузер | Chrome / Firefox / Edge | робота з системою |

Для звичайних користувачів потрібен лише **браузер** і **навчальний Google-акаунт**.

## Кроки запуску (для розробника)
```bash
git clone https://github.com/<username>/dormhub.git
cd dormhub
# 1. База даних
createdb dormhub
# 2. Налаштування
cp .env.example .env        # вказати DB_URL, DB_USER, DB_PASSWORD, GOOGLE_CLIENT_ID
# 3. Сервер
./mvnw spring-boot:run      # API на http://localhost:8080
# 4. Вебінтерфейс
cd web && npm install && npm run dev   # UI на http://localhost:5173
```

## Перевірка роботи
1. Відкрийте `http://localhost:8080/api/health` — відповідь `{"status":"UP"}`.
2. Відкрийте `http://localhost:5173` — з'являється сторінка входу DormHub.
3. Увійдіть тестовим акаунтом `commandant@test.local` — у меню видно розділ «Кімнати».

> ⚠️ Якщо API не запускається — перевірте, що PostgreSQL працює і дані в `.env` правильні.
