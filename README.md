## Задание: подписка на NATS-streaming

Cервис по отправке и получению сообщений при помощи брокера сообщений NATS-streaming




### Взаимодействие с брокером сообщений:
- Скрипт ```main.go``` в пакете ```producer``` выполняет роль клиента, который публикует сообщения в NATS
с содержанием файла ```model.json```
- Скрипт ```main.go``` в пакете ```consumer``` выполняет роль подписчика на канал. Он читает сообщения из NATS,
парсит значения и сохраняет в базу данных postgres.
- Сервис содержит кэширование сообщений
- Информацию по каждому заказу можно смотреть по ссылке ```http://localhost:8080/orders/id```

Сервис использует порт 5432 для postgres и 8080 для http

### Технологии:
- GO
- NATS-streaming
- Postgres
- GORM
- Gin

Для запуска сервиса настройте запуск NATS и запустите локально nats-streaming-server,
затем запустите скрипт ```./producer/main.go```, а потом ```./consumer/main.go```
