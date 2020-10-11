## Авторизация JWT"
####**Авторизация в Rest приложении через token**

В качестве запросов к серверу использовал консольную утилиту [Curl](https://curl.haxx.se/download.html)

После запуска проекта необходимо:

* **В коммандной строке перейти в папку bin установленной утилиты curl.**

![alt text](images/1.jpg)

* **Проверка, что безопасность работает. Попытка получить пользователей без авторизации.**\
набор команды: curl http://localhost:8080/all

![alt text](images/2.jpg)

* **Регистрация пользователя**\
набор команды: curl -H Content-Type:application/json -X POST -d "{\"username\":\"admin\",\"password\":\"password\"}" http://localhost:8080/users/sign-up

![alt text](images/3.jpg)

* **Получить у этого пользователя token**\
набор команды: curl -i -H Content-Type:application/json -X POST -d "{\"username\":\"admin\",\"password\":\"password\"}" http://localhost:8080/login

![alt text](images/4.jpg)

* **Получить всех пользователей с этим token.**\
набор команды: curl -H "Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzUxMiJ9.eyJzdWIiOiJhZG1pbiIsImV4cCI6MTYwMzMxMzk4MH0.vvX0NEh8pgxkRxrbUWaaLIJvGw3h6YzDl9uusm643e3ZUnS0U5zQi796Y54ds8y7yVTrPAEDnTn972LMfYLGkg" http://localhost:8080/users/all

![alt text](images/5.jpg)