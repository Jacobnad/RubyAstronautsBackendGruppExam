# register som admin 

`http://localhost:8080/api/auth/login`

POST 

Ex

{
  "username": "AdminUser",
  "password": "adminpass",
  "validatePassword": "adminpass",
  "email": "admin@site.com",
  "firstName": "Admin",
  "lastName": "User",
  "address": "Adminvägen 1"
}

return 

{
  "success": true,
  "message": "User registered successfully.",
  "status": 201
}

# lägga till admin eller tabort admin 

efter inlogningen 

till ex 
Get
`http://localhost:8080/api/auth/admin/set/1W7HS`

gå till hidder skriv i key Authorization och i valu token som du fick när du gjorde inlogningen 

välja ROw

send 

# RETURN 

{
  "success": true,
  "message": "User with username: AdminUser has admin rights from now.",
  "status": 201
}

ELLER 

{
  "success": true,
  "message": "User with username: AdminUser has no longer admin rights.",
  "status": 201
}

Bara Admin har rätt att hämta alla users 

med samma stig 

efter inlogning

Get 
`http://localhost:8080/api/auth/users`

gå till hidder skriv i key Authorization och i valu token som du fick när du gjorde inlogningen 

välja ROw

send 

Return

{
  "success": true,
  "message": "Users found.",
  "status": 201,
  "users": [
    {
      "username": "AdminUser",
      "userId": "1W7HS",
      "email": "admin@site.com",
      "firstName": "Admin",
      "lastName": "User",
      "address": "Adminvägen 1",
      "isAdmin": false,
      "_id": "273unjjDXdqCwNDh"
    },
    {
      "username": "Jacob",
      "userId": "RO6LL",
      "email": "Jacob@olaconny.se",
      "firstName": "Jacob",
      "lastName": "Jacobson",
      "address": "Bananskalsvägen 40, 50505 Göteborg",
      "isAdmin": true,
      "_id": "3wzAzlIUg0WqhOzt"
    },
    {
      "username": "Mimmi",
      "userId": "WMQYV",
      "email": "nisse@lasse.se",
      "firstName": "Mimmi",
      "lastName": "Mimmi",
      "address": "Knektvägen 21, 68631 Sunne",
      "isAdmin": false,
      "_id": "oEyZ5xOwZsaWeESP"
    },
  ]
}

hämta en user 

Get 

`http://localhost:8080/api/auth/users/WMQYV`


hämta descount
`http://localhost:8080/api/discounts`


Return 

{
  "success": true,
  "message": "Discounts found.",
  "status": 200,
  "filterOptions": {},
  "discounts": [
    {
      "title": "2 för 1!",
      "desc": "Köp 2 Kaffe Latte, få den ena på köpet!",
      "products": [
        {
          "productId": "UQWXNsKroS9bKZL0",
          "amount": 2
        }
      ],
      "expiresAt": "2025-04-18T00:00:00.000Z",
      "discount": 54,
      "createdAt": "2025-04-11T10:10:56.782Z",
      "_id": "7pQQTkbGBak02v51"
    },
    {
      "title": "Gustav Adolfs brygga!!",
      "desc": "För att fira att Gustav II Adolf varit död ett tag så har vi dragit igång ett riktigt bra kap! Vid köp av en bryggkaffe och en Gustav Adolfsbakelse så får du detta för ett pangpris på 40 kr! Med tanke på våra sinnessjuka priser vanligtvis så vore det väldigt konstigt om du inte tog del av detta erbjudande! Detta erbjudandet har absolut inget att göra med att vi råkade beställa på tok för mycket grädde och mandelmassa som vi måste göra oss av med. Erbjudandet är giltigt fram till 2025-07-01",
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
      "expiresAt": "2025-04-01T00:00:00.000Z",
      "discount": 58,
      "createdAt": "2025-04-11T11:28:03.354Z",
      "_id": "YJrz3p89Abd0pVaS",
      "modifiedAt": "2025-04-11T11:29:19.244Z"
    }
  ]
}