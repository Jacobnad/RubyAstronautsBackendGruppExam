# Discounts -

lägga ny descount

post 

http://localhost:7070/api/discounts

i body t.ex.
{
  "title": "Köp 1, få 1 gratis!",
  "desc": "Köp en Croissant och få en gratis. Gäller till 2025-05-01.",
  "products": [
    {
      "productId": "UQWXNsKroS9bKZL0",
      "amount": 1
    }
  ],
  "expiresAt": "2025-05-01T00:00:00.000Z",
  "discount": 50
}


return 

{
  "success": true,
  "message": "Discount added successfully.",
  "status": 200,
  "discount": {
    "title": "Köp 1, få 1 gratis!",
    "desc": "Köp en Croissant och få en gratis. Gäller till 2025-05-01.",
    "products": [
      {
        "productId": "UQWXNsKroS9bKZL0",
        "amount": 1
      }
    ],
    "expiresAt": "2025-05-01T00:00:00.000Z",
    "discount": 50,
    "createdAt": "2025-04-19T20:28:01.070Z"
  }
}

Delet discount 
http://localhost:7070/api/discounts/ID

TEX 

http://localhost:7070/api/discounts/YJrz3p89Abd0pVaS

Return 

{
  "success": true,
  "message": "Discount removed successfully.",
  "status": 200,
  "removedDiscount": {
    "title": "Gustav Adolfs brygga!!",
    "desc": "För att fira att Gustav II Adolf varit död ett tag så har vi dragit igång ett riktigt bra kap! Vid köp av en bryggkaffe och en Gustav Adolfsbakelse så får du detta för ett pangpris på 40 kr! Med tanke på våra sinnessjuka priser vanligtvis så vore det väldigt konstigt om du inte tog del av detta erbjudande! Detta erbjudandet har absolut inget att göra med att vi råkade beställa på tok för mycket grädde och mandelmassa som vi måste göra oss av med. Erbjudandet är giltigt fram till 2024-07-01",
    "products": [
      {
        "productId": "acDrF5CFhSivFUau",
        "amount": 1
      },
      {
        "productId": "rrAM4mwd6ZiBNlXx",
        "amount": 1
      }
    ],
    "expiresAt": "2024-07-01T00:00:00.000Z",
    "discount": 58,
    "createdAt": "2024-06-11T11:28:03.354Z",
    "_id": "YJrz3p89Abd0pVaS",
    "modifiedAt": "2024-06-11T11:29:19.244Z"
  }
}