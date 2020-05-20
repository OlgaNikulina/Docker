
# Подготовка приложения db-api.jar к тестированию в СУБД PostgreSql

## Начало работы
1. jar файл полжить в проект рядом с файлом application.properties:
```spring.datasource.url=jdbc:postgresql://192.168.99.100:5432/my_db
   spring.datasource.username=app
   spring.datasource.password=pass
```
 и docker-compose.yml. В docker-compose.yml прописать настройки запуска и переменные окружения: 
```
version: '3.1'

services:
  postgres:
    image: postgres:12-alpine
    ports:
      - '5432:5432'
    restart: always
    volumes:
      - "./db-data:/var/lib/postgresql/data"
    environment:
      - POSTGRES_USER=app
      - POSTGRES_PASSWORD=pass
      - POSTGRES_DB=my_db
```                                                                                                                                                         
                                                                                                                                                                        
### Prerequisites
На ПК должна быть установлена JDK, IntelliJ IDEA, Docker Toolbox

### Установка и запуск
1. Выполнить команду docker-compose up. База данных должна запуститься.
2. Выполнить команду java -jar db-api.jar. Приложение должно открываться в браузере.   
