# RPC - Remote Procedure Call 
Работа с удаленными процедурами: 
- Распределение выполнения задач. 
  Например, один компьютер обрабатывает базу данных, а другой обладает большими вычислительными мощностями. 
- Выполнение различных блоков задачи, включая общение между разными удаленными системами.
## Архитектура RPC
![rpc_arch](https://github.com/c0mrade12211/go_grpc_proto/assets/132468035/f49902b3-5744-4cf2-984a-497d5d49858c)

 
## Архитектура gRPC 
Преимущества: 
1. Абстракция - это просто вызов функции. 
2. Поддерживается на многих языках. 
3. Эффективность. 
4. HTTP вызовы могут быть запутывающими. 
 
![Пример архитектуры gRPC]
stub реализован для сериализации и десериализации 
![grpc_arch](https://github.com/c0mrade12211/go_grpc_proto/assets/132468035/adee416f-26b0-443e-b446-7e321b537e83)

 
## Что такое gRPC? 
gRPC - это RPC (Remote Procedure Call), где сетевые вызовы абстрагированы от кода. Он предоставляет инструменты для кодогенерации и поддерживает использование различных протоколов. 


## Мультиплексирование запроса и ответа:
1. В традиционном HTTP невозможно отправить несколько запросов или получить несколько ответов в одном соединении.
2. В HTTP/2 это стало возможным благодаря двоичному кодированию
   
## Языки программирования, поддерживающие gRPC 
Вы можете создавать системы с использованием gRPC на следующих языках: 
- C#/.NET 
- C++ 
- Dart 
- Go 
- Java 
- Kotlin 
- PHP 
- Python 
- Ruby 
 
## PROTOCOL BUFFERS 
Protobuf (Protocol Buffers) - это наиболее используемый механизм сериализации структурированных данных в gRPC. В основном данные и функциональные контракты хранятся в виде прото-файлов. 
 
### Что не так с JSON? 
- Динамическая схема - набор полей строго не регламентирован. 
- Медленный парсинг данных. 
- Отсутствие типизации - JSON это просто ключ-значение строка. 
- Большой размер данных. 
 
### Плюсы PROTOBUF: 
- Меньший размер относительно JSON. 
- Типизация данных. 
- Схема данных. 
 
### Типы данных в PROTOBUF 
Более подробную информацию о типах данных в PROTOBUF можно найти в [документации](https://protobuf.dev/programming-guides/proto3/#scalar). 
 
## Сравнение JSON и PROTOBUF 
Пример генерации кода из .proto файла и сравнение размеров сериализованных данных в форматах JSON и PROTOBUF доступен в репозитории [JSON and PB compare](https://github.com/zexy-swami/go_and_grpc/tree/main/code/json_and_pb_compare). 
 
## gRPC и HTTP 
### Что не так с HTTP? 
- Создает новое соединение на каждый запрос. 
- Head of blocking - нет возможности асинхронной передачи контента. 
- Нет server push. 
 
### Преимущества HTTP/2.0 
- Одно TCP соединение. 
- Бинарный протокол - повышение гибкости передачи данных. 
- Сжатие заголовков. 
 
Сравнение скорости передачи контента в HTTP версиях 1.1 и 2 доступно по ссылке [http://www.http2demo.io/](http://www.http2demo.io/). 
 
## Пример запуска gRPC сервера и клиента на языке Go 
Пример запуска gRPC сервера и клиента на языке Go можно найти в репозитории [gRPC example](https://github.com/zexy-swami/go_and_grpc/tree/main/code/grpc_example).
