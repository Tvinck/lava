# Lava Webhook API

## 📌 Что делает:
Этот Flask-сервер:
- принимает webhook от SaleBot (POST /webhook)
- получает данные (sum, orderId, client_id)
- формирует payload
- подписывает через HMAC SHA256
- отправляет в Lava API
- возвращает invoice_url обратно

## 🧪 Пример запроса:
POST /webhook

```json
{
  "sum": 199,
  "orderId": "order_test_123",
  "client_id": "123456789"
}
```

## 📦 Ответ:
```json
{
  "status": "ok",
  "invoice_url": "https://pay.lava.ru/..."
}
```

## 🚀 Запуск:
```bash
pip install -r requirements.txt
python main.py
```