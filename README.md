# Докеризация приложения КупиПодариДай

В сервисе вишлистов **КупиПодариДай** каждый зарегистрированный пользователь может рассказать о том, какой подарок он бы хотел получить, а также скинуться на подарок для другого пользователя, указав сумму, которую готов на это потратить

## Инструкция по деплою

Деплой проекта осуществляется с помощью докера в несколько шагов:

1. Сборка:  
```sudo docker compose -f docker-compose.yml up --build```

2. Пуш образов:  
```
  docker login
  docker push nickname/kupipodariday-backend-opti:1.0.0
  docker push nickname/kupipodariday-frontend-opti:1.0.0
```

3. Копирование файла с константами окружения, а также конфигом для деплоя:  
```scp .env docker-compose.prod.yml nickname@xxx.xxx.xxx.xxx:/home/nickname/kupipodariday```

4. После подключения на сервер:  
```
cd kupipodariday
docker compose -f docker-compose.prod.yml down
docker compose -f docker-compose.prod.yml up -d --build
```

## Адреса
- IP адрес 84.201.133.101
- Frontend https://annie.kpd.nomorepartiesco.ru/
- Backend https://api.annie.kpd.nomorepartiesco.ru/  
