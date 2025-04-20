# Navigation -



## GET - `http://localhost:8080/api/navigation`
Hämtar alla navigeringsobjekt.

### Returns
{
  "success": true,
  "message": "Navigation items found.",
  "status": 200,
  "navigationItems": [
    {
      "title": "Min profil",
      "url": "/profile",
      "isAdmin": false,
      "_id": "EXENHpAEBN8mRNNO"
    },
    {
      "title": "Vårt kaffe",
      "url": "/about",
      "isAdmin": false,
      "_id": "PhwUWf3ALdZ9WAow"
    },
    {
      "title": "Orderstatus",
      "url": "/status",
      "isAdmin": false,
      "_id": "T0wR8CxAbBMsimlf"
    },
    {
      "title": "Meny",
      "url": "/menu",
      "isAdmin": false,
      "_id": "yI14O5DPQPMFA93j"
    }
  ]
}