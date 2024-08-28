<h1 align="center">SKY-TRADERS-API</h1>

[Получение списка активных сделок](#activeDeals)

[Принятие сделки](#acceptDeal)

[Подтверждение оплаты (для сделок по покупке)](#approvePayment)

[Подтверждение получения средств (для сделок по продаже)](#approveReceiving)

Чтобы получить токен для API, необходимо связаться с администратором SKY CRYPTO.
API PROD - tbd, API TEST - https://papi.trcrfortest.co

<a name="activeDeals"></a>
## Получение списка активных сделок

```http
  GET rest/v3/proposed-deals?type=sell
```
или
```http
  GET rest/v3/proposed-deals?type=buy
```

#### Response example

```javascript
[
    {
        "amount_currency": 2000.0,
        "currency": "rub",
        "id": "aatzVZWRt0",
        "symbol": "btc"
    }
]
```

<a name="acceptDeal"></a>
## Принятие сделки

```http
  PATCH rest/v3/deals/{deal_id}
```

#### Body example

```javascript
{
    "requisite": "Test 1234567",
    "state": "confirmed"
}
```

#### Response example

```javascript
{
    "amount_currency": 2000.0,
    "buyer_id": 156337,
    "currency": "rub",
    "deal_id": "aatzVZWRt0",
    "lot_owner": 156334,
    "requisite": "Test 1234567",
    "seller_id": 186717,
    "state": "confirmed",
    "symbol": "btc"
}
```

<a name="approvePayment"></a>
## Подтверждение оплаты (для сделок по покупке)

```http
  PATCH rest/v3/deals/{deal_id}
```

#### Body example

```javascript
{
    "state": "paid"
}
```

#### Response example

```javascript
{
    "amount_currency": 2000.0,
    "buyer_id": 156337,
    "currency": "rub",
    "deal_id": "aatzVZWRt0",
    "lot_owner": 156334,
    "requisite": "Test 1234567",
    "seller_id": 186717,
    "state": "paid",
    "symbol": "btc"
}
```

<a name="approveReceiving"></a>
## Подтверждение получения средств (для сделок по продаже)

```http
  PATCH rest/v3/deals/{deal_id}
```

#### Body example

```javascript
{
    "state": "closed"
}
```

#### Response example

```javascript
{
    "amount_currency": 2000.0,
    "buyer_id": 156337,
    "currency": "rub",
    "deal_id": "aatzVZWRt0",
    "lot_owner": 156334,
    "requisite": "Test 1234567",
    "seller_id": 186717,
    "state": "closed",
    "symbol": "btc"
}
```
