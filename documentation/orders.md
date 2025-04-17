# Skapa order 

Post 

http://localhost:8080/api/orders/create 

EX i body

{
  "userId": 1,
  "firstName": "Gramos",
  "items": [
    {
      "id": 1,
      "title": "Bryggkaffe",
      "desc": "Bryggd på månadens bönor.",
      "price": 39,
      "quantity": 2
    },
    {
      "id": 2,
      "title": "Latte",
      "desc": "Med havremjölk.",
      "price": 49,
      "quantity": 1
    }
  ],
  "totalPrice": 88,
  "date": "2025-04-17"
}


Return 

{
  "userId": 1,
  "firstName": "Gramos",
  "items": [
    {
      "id": 1,
      "title": "Bryggkaffe",
      "desc": "Bryggd på månadens bönor.",
      "price": 39,
      "quantity": 2
    },
    {
      "id": 2,
      "title": "Latte",
      "desc": "Med havremjölk.",
      "price": 49,
      "quantity": 1
    }
  ],
  "totalPrice": 88,
  "date": "2025-04-17",
  "_id": "JqSIJpLx8L2HmiM8"
}