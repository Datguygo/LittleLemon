Little Lemon Capstone - API Paths for Peer Review
=================================================

Base URL: http://127.0.0.1:8000

Setup
-----
1. Activate the virtual environment: source env/bin/activate
2. Start MySQL (Docker): docker start littlelemon-mysql
3. From the littlelemon/ folder: python manage.py runserver

Static HTML (home page)
-----------------------
GET  /restaurant/

Menu API
--------
GET     /restaurant/menu/
POST    /restaurant/menu/
GET     /restaurant/menu/<id>
PUT     /restaurant/menu/<id>
PATCH   /restaurant/menu/<id>
DELETE  /restaurant/menu/<id>

Alternate menu paths:
GET/POST  /restaurant/menu/items
GET/PUT/PATCH/DELETE  /restaurant/menu/items/<id>

Table Booking API (requires authentication)
-------------------------------------------
GET     /restaurant/booking/tables/
POST    /restaurant/booking/tables/
GET     /restaurant/booking/tables/<id>/
PUT     /restaurant/booking/tables/<id>/
PATCH   /restaurant/booking/tables/<id>/
DELETE  /restaurant/booking/tables/<id>/

User Registration and Authentication
------------------------------------
GET/POST  /auth/users/                 (list users / register)
POST      /auth/token/login/           (login, returns auth token)
POST      /auth/token/logout/          (logout)
POST      /restaurant/api-token-auth/  (obtain DRF auth token)

Insomnia testing tips
---------------------
1. Register: POST /auth/users/ with username, password, re_password
2. Login: POST /auth/token/login/ or POST /restaurant/api-token-auth/
   Body JSON example: {"username": "youruser", "password": "yourpass"}
3. For booking endpoints, set Auth -> Bearer Token and paste the token
4. Menu endpoints can be tested without a token

Admin panel
-----------
GET  /admin/
