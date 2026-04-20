TC ID: 1
Modül: Login
Başlık: Geçerli kullanıcı ile başarılı giriş
Ön Koşul:
Test Tipi: Positive

Endpoint: POST /auth

Adımlar:
Request çağrılır
{
  "username": "admin",
  "password": "password123"
}

Beklenen:
- Status: 200
- token != null


TC ID: 2
Modül: Login
Başlık: Geçersiz kullanıcı bilgileri ile giriş denemesi
Ön Koşul: 
Test Tipi: Negative

Endpoint: POST /auth

Adımlar:
Request çağrılır
{
  "username": "admin11111",
  "password": "password123"
}

Beklenen:
"reason": "Bad credentials" yanıtı alınır


TC ID: 3
Modül: Booking
Başlık: Rezervasyon sorgulama
Ön Koşul: 
Test Tipi: Positive

Endpoint: GET /booking

Adımlar:
İlgili formata uygun şekilde request çağrılır
https://restful-booker.herokuapp.com/booking/:id

Beklenen:
Rezervasyon numarasına ait bilgilerin listelendiği görülür
- 200 OK
- Array döner
- response time < 1s


TC ID: 4
Modül: Booking
Başlık: Geçersiz bilgilerle rezervasyon sorgulama
Ön Koşul: 
Test Tipi: Negative

Endpoint: GET /booking

Adımlar:
Sistemde olmayan bir rezervasyon sorgulanır
https://restful-booker.herokuapp.com/booking/999999999

Beklenen:
404 Not Found yanıtı aldığı görülür



TC ID: 5
Modül: Booking
Başlık: Rezervasyon oluşturma
Ön Koşul: 
Test Tipi: Positive

Endpoint: GET /CreateBooking

Adımlar:
Request çağrılır
{
    "firstname": "Test",
    "lastname": "Customer",
    "totalprice": 157,
    "depositpaid": true,
    "bookingdates": {
        "checkin": "2026-01-01",
        "checkout": "2026-01-05"
    },
    "additionalneeds": "Breakfast"
}

Beklenen:
bookingid değerini içeren yanıt alınır
- 200 OK
