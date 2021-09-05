# QA Diploma [![Build status]()

# Quality assurance Engineer Diploma project

<<<<<<< HEAD
This Diploma project represents complex servise testing automatization,which interacts with Bank Database and API.
=======
My Diploma project represents a complex web service testing automatization, which interacts with Bank's database & API.
>>>>>>> d907fdfeb62f84336902d58c1077c42be26838ab

## Documentation

[Дипломное задание](https://github.com/netology-code/qa-diploma.git)

[План автоматизации тестирования веб-формы сервиса покупки туров интернет-банка](doc/Plan.md)

[Отчёт о проведенном тестировании](doc/Report.md)

[Отчёт о проведённой автоматизации](doc/Summary.md)

## Preconditions

<<<<<<< HEAD
Перед запуском необходимо выполнить следующие предусловия. Если у вас уже есть необходимое ПО, то понадобится только п.1 и запуск Docker.
=======
Before launch you need to fullfill next requirments:
1. Clone git [repository](https://github.com/Aleks4404/DiplomaProjectOfTheProfessionTester)
or use VCS Git integrated in IntelliJ IDEA
2. Install and launch Docker Desktop. Installation process depends on operating system.
[Docker Download](https://docs.docker.com/get-docker/)
3. Open project in IntelliJ IDEA
>>>>>>> d907fdfeb62f84336902d58c1077c42be26838ab

*Предусловия:*
1. Необходимо склонировать репозиторий или скачать архив по [ссылке](https://github.com/Aleks4404/DiplomaProjectOfTheProfessionTester.git). Или воспользоваться VCS Git, встроенной в
   IntelliJ IDEA.
2. Установить и запустить Docker Desktop. Это можно сделать [здесь](https://docs.docker.com/get-docker/) в зависимости от операционной системы. Дополнительные инструкции по установке Docker [ссылке](https://github.com/netology-code/aqa-homeworks/blob/master/docker/installation.md)
3. Открыть проект в IntelliJ IDEA

### Application Launch

1. Запустить необходимые базы данных (MySQL и PostgreSQL), а также NodeJS. Параметры для запуска хранятся в
   файле `docker-compose.yml`. Для запуска необходимо ввести в терминале команду:

<<<<<<< HEAD
> * `docker-compose up -d`

2. В новой вкладке терминала ввести следующую команду в зависимости от базы данных
=======
1. Launch requered databases (MySQL и PostgreSQL), and NodeJS. Launch parameters in file `docker-compose.yml`.
2. Write Launch command in terminal:
> * `docker-compose up -d`

3. In new terminal tab exeute command depending on database:
>>>>>>> d907fdfeb62f84336902d58c1077c42be26838ab

> * `java -Dspring.datasource.url=jdbc:mysql://localhost:3306/app -jar ./artifacts/aqa-shop.jar` - для MySQL
> * `java -Dspring.datasource.url=jdbc:postgresql://localhost:5432/app -jar ./artifacts/aqa-shop.jar` - для PostgreSQL

<<<<<<< HEAD
3. Проверка работающих контейнеров:
=======
4. Verification that containers works:
>>>>>>> d907fdfeb62f84336902d58c1077c42be26838ab

> * `docker ps`

> ![Starting the container](doc/pic/StartConteyner.png)

<<<<<<< HEAD
4. Приложение должно запуститься по адресу
=======
5. Application must start on this adress:
>>>>>>> d907fdfeb62f84336902d58c1077c42be26838ab

> * `http://localhost:8080/`
 
## Autotests

1. Для запуска автотестов с "MySQL",  необходимо открыть новую вкладку терминала и ввести следующую команду:
> * `gradlew test -Dselenide.headless=true -Durlbd=jdbc:mysql://localhost:3306/app --info`

2. Для запуска автотестов с "PostgreSQL",  необходимо открыть новую вкладку терминала и ввести следующую команду:
> * `gradlew test -Dselenide.headless=true -Durlbd=jdbc:postgresql://localhost:5432/app --info`

## Test reports 

1. Для запуска и просмотра отчета по результатам тестирования, с помощью "Allure", выполнить по очереди команды:
> * `gradlew allureReport`
> * `gradlew allureServe`

##  SUT shutdown

1. Для завершения работы SUT, необходимо в терминале, где был запущен SUT, ввести команду:
> * `Ctrl+C`

## Shutdown Docker container
1. Для остановки работы контейнеров "Docker-Compose", необходимо ввести в терминал следующую команду: 

> * `docker-compose down`
