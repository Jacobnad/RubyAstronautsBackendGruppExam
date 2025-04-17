# skapa konto

Post
http://localhost:8080/auth/register

ex:

{
  "username": "jacobGHDAY1",
  "password": "mypassword222",
  "email": "Jacob.ghday@example.com"
}

return 

{
  "success": true,
  "status": 201,
  "message": "User created successfully",
  "data": {
    "username": "jacobGHDAY1",
    "password": "mypassword222",
    "email": "Jacob.ghday@example.com",
    "_id": "1ksHIGNl4wGV0V7T"
  }
}


# Inlogning

post

http://localhost:8080/auth/login

EX:

{
  "username": "Gramos1",
  "password": "mypassword111"
  
}

return


{
  "success": true,
  "status": 200,
  "message": "User logged in successfully",
  "data": {
    "username": "Gramos1",
    "password": "mypassword111",
    "email": "Gramos@example.com",
    "_id": "nXm3IIuBykmJXYxu"
  }
}


# Logout 

post

http://localhost:3000/logout

Headers: (ingen särskild krävs om du inte använder autentisering)

Body: lämna tom (ingen body behövs)


return

{
  "success": true,
  "status": 200,
  "message": "User logged out successfully"
}


