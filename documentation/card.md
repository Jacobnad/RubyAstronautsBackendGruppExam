# Add produkt

http://localhost:8080/api/cart

Post 

body JSON

{
  "title": "Cappuccino",
  "desc": "Bryggd på idags bönor.",
  "price": 39
}

return 

{
  "message": "Coffee added to cart!"
}


# Hämta alla nya produkter 

Get 

body Tom 

http://localhost:8080/api/cart


return:

[
  {
    "title": "Cappuccino",
    "desc": "Bryggd på idags bönor.",
    "price": 39,
    "_id": "I9kzXZhEkV8zBZeg"
  },
  {
    "id": 1,
    "title": "Bryggkaffe",
    "desc": "Bryggd på månadens bönor.",
    "price": 39,
    "_id": "xRKZvGfx4S3eEdpj"
  }
]


# Delet prudukt 

Method: DELETE

URL: http://localhost:3000/api/cart/1

Body Tom 

Return 

{
  "message": "Coffee removed from cart!"
}

