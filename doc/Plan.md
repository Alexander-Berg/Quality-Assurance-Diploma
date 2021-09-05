# Automation testing plan for complex web service (Tour purchase from bank)
## List of automated scenarios:
### 1. Positive scenario for  "Оплата по карте" & "Кредит по данным карты"

_**1.1.** Correctly filled fields "Оплата по карте"._
* Press the button "Купить".

**Expected result:** 
* In tab "Купить" emerges field with headline "Оплата по карте".

_**1.2.** Standart purchase by debit card with "APPROVED" result, and with typed valid data:_
* In field "Номер карты" type "4444 4444 4444 4441";
* In field "Месяц" type "08";
* In field "Год" type "22";
* Field "Владелец" using data from "Faker" generator on latin symbols;
* In field "CVC/CVV" type "123";
* Press button "Продолжить".

**Expected result:** 
* Button "Продолжить" changing to "Отправляем запрос в Банк..." with swirling loading icon.
* In top right corner appears window with message "Операция одобрена Банком".

_**1.3.** Standart purchase  by debit card with status "DECLINED" and with valid  data in type fields:_
* In field "Номер карты" type "4444 4444 4444 4442";
* In field "Месяц" type "08";
* In field "Год" type "22";
* Field "Владелец" filled with data from  "Faker" generation library on latin;
* In field "CVC/CVV" type "123";
* Press button "Продолжить".

**Expected result:**
* Button "Продолжить" changing to button "Отправляем запрос в Банк..." with swirling loading screen.
* In top right cornet message appear "Ошибка! Банк отказал в проведении операции".

_**1.4.** Database shows correct values after payment, and status "APPROVED", with valid input data:_
* In field "Номер карты" type "4444 4444 4444 4441";
* In field "Месяц" type "08";
* In field "Год" type "22";
* Field "Владелец" filled with data generator "Faker"on latin alphabet.
* In field "CVC/CVV" type "123";
* Press button "Продолжить".

**Expected result:**
* Button "Продолжить" changing to  "Отправляем запрос в Банк..." with spinning loading indicator;
* Pop up message will appear in top right screen "Операция одобрена Банком";
* in database table «payment_entity», in row «amount», will appear right summary - '45000'.

_**1.5.** Succesful loading screen "Кредит по данным карты":_
* press the tab "Купить в кредит".

**Expected result:**
*In tab"Купить в кредит" will appear form to fullfil "Кредит по данным карты".

_**1.6.**Issuance of Credit with message "APPROVED" and with correct data inputed:_
* In field "Номер карты" type "4444 4444 4444 4441";
* In field "Месяц" type "08";
* In field "Год" type "22";
* Field "Владелец" filled with data generation service "Faker" on latin alphabet;
* In field "CVC/CVV" type "123";
* Press the button "Продолжить".

**Expected result:**
* Button "Продолжить" changing to button "Отправляем запрос в Банк..." with spinning loading indicator;
* Po up screen will sppear in top right corner"Операция одобрена Банком".

_**1.7.**  Insuance of credit with status "DECLINED" with valid data on input:_
* In field "Номер карты" type "4444 4444 4444 4442";
* In field "Месяц" type "08";
* In field "Год" type "22";
* Field "Владелец" filled with generation service "Faker" on latin alphabet;
* In field "CVC/CVV" type "123";
* Press the button "Продолжить".

**Expected result:**
* Button "Продолжить" will change to "Отправляем запрос в Банк..." with spinning loading indicator
* In top right corner popup message will appear "Ошибка! Банк отказал в проведении операции".

---

### 2. Negative scenario for forms "Оплата по карте" and "Кредит по данным карты"

_**2.1.** Standard purchase with debit card:_
* In field "Номер карты" type "0000 0000 0000 0001";
* In field "Месяц" type "08";
* In field "Год" type "22";
* Field "Владелец" filled with data generation library "Faker" on latin alphabet;
* In field "CVC/CVV" type "123";
* Press the button "Продолжить".

**Expected result:**
* Button "Продолжить" will change to button "Отправляем запрос в Банк..." with spinning loading indicator;
* In top right corner popup screen will appear with message "Ошибка! Банк отказал в проведении операции".

_**2.2.** Standart payment by debit card with "APPROVED" status and non valid data "Месяц":_
* In field "Номер карты" type "4444 4444 4444 4441";
* In field "Месяц" type "99";
* In field "Год" type"22";
* Field "Владелец" filled with data library "Faker" on latin alphabet;
* In field "CVC/CVV" type "123";
* Press the button "Продолжить".

**Expected result:**
* below field "Месяц"  red colored message appeares "Неверно указан срок действия карты".

_**2.3.** Standart payment by debit card with status "APPROVED" and non valid data "Год":_
* In field "Номер карты" input "4444 4444 4444 4441";
* In field "Месяц" type "08";
* In field "Год" type "20";
* Field "Владелец" filled  with "Faker" data generator on latin alphabet
* In field "CVC/CVV" type "123";
* Press the button "Продолжить".

**Expected result:**
* Below field "Год" red colord message appears "Истёк срок действия карты".

_**2.4.** Standart payment by debit card with status "APPROVED" and non valid data "Год":_
* In field "Номер карты" type "4444 4444 4444 4441";
* In field "Месяц" type "08";
* In field "Год" type "99";
* Field "Владелец" filled with "Faker" data generation library on latin alphabet
* In field "CVC/CVV" type "123";
* Press the button "Продолжить".

**Expected result:**
* Below field "Год" red colored message appeares "Неверно указан срок действия карты".

_**2.5.** Standart payment by debit card with "APPROVED" and non valid data in field "Владелец":_
* In field "Номер карты" type "4444 4444 4444 4441";
* In field "Месяц" type "08";
* In field "Год" type "22";
* Field "Владелец" filled with "Faker" data generation library with Cyrilic alphabet
* In field "CVC/CVV" type "123";
* Press the button "Продолжить".

**Expected result:**
* Below field "Владелец" message appears «Неверный формат».
* Button "Продолжить" not changing to "Отправляем запрос в Банк..." with spinning loading indicator. Data is not sent.

_**2.6.** Empty input form "Оплата по карте":_
* Press the button "Продолжить".

**Expected result:**
* Below fields "Номер карты", "Месяц", "Год", "CVC/CVV", message will appear "Неверный формат";
* Below field "Владелец" - "Поле обязательно для заполнения";
* Data is not sent.

_**2.7.** Input of form "Оплата по карте" with valid data, after sending empty form:_
* Press the button "Продолжить".
* In field "Номер карты" type "4444 4444 4444 4441";
* In field "Месяц" type "08";
* In field "Год" type "22";
* Field "Владелец" filled with "Faker" data generation library on latin alphabet 
* In field "CVC/CVV" type "123";
* Press the button "Продолжить".

*Expected result:**
* After pressing button "Продолжить", with empty form, data is not sent;
   * Under fields "Номер карты", "Месяц", "Год", "CVC/CVV", red colored message will appear "Неверный формат»
   * Under field "Владелец" messsge will appear "Поле обязательно для заполнения».
* After correct data typing, button "Продолжить" changes to  "Отправляем запрос в Банк..." with spinning loading indicator. 
   * Data sent. In top right corner pop up message will apear"Операция одобрена Банком". * Pop up window with text «visible».
* Messages (Red colored), about not correct data or invalid data not appears.


_**2.8.** Invalid input on field "Оплата по карте" with wrong data:_
* In field "Номер карты" type "0000 0000 0000 0001";
* In field "Месяц" type "80";
* In field "Год"  type"99";
* Field "Владелец" filled with "Faker" data generation library on cyrillic alphabet.
* In field "CVC/CVV" type "66";
* Press the button "Продолжить".

**Expected result:**
* Under fields "Номер карты", "Месяц", "Год", "Владелец", "CVC/CVV", message will appear "Неверный формат".

_**2.9.**Insuance of credit with non valid credit card number:_
* In field "Номер карты" type "9999 9999 9999 9999";
* In field "Месяц" type "08";
* In field "Год" type "22";
* Field "Владелец" filled with "Faker" on latin alphabet;
* In field "CVC/CVV" type "123";
* Press button "Продолжить".

**Expected result:**
* Button "Продолжить" changes to button  "Отправляем запрос в Банк..." with spinning loading indicator.
* In right top corner message will appear "Ошибка! Банк отказал в проведении операции".

_**2.10.** Insuanse of credit with "APPROVED" status and non valid data in field "Месяц":_
* In field "Номер карты" type "4444 4444 4444 4441";
* In field "Месяц" type "99";
* In field "Год" type "22";
* Field "Владелец" filled with "Faker" data generation libeary on latin alphabet.
* In field "CVC/CVV" type "123";
* Press the button "Продолжить".

**Expected result:**
* Under field "Месяц" red colored message appears "Неверно указан срок действия карты".

_**2.11.** Insuance of credit with "APPROVED" status and non valid data in field "Год":_
* In field "Номер карты" type "4444 4444 4444 4441";
* In field "Месяц" type "08";
* In field "Год" type "21";
* Field "Владелец" filled with "Faker" on latin
* In field "CVC/CVV" type "123";
* Press the button "Продолжить".

**Expected result:**
* Under field "Год" red colored message will appear "Истёк срок действия карты".

_**2.12.** Insuanse of credit with status "APPROVED" and non valid data in field "Год":_
* In field "Месяц" type "08";
* In field "Год" type "99";
* Field "Владелец" filled with "Faker" on latin alphabet
* In field "CVC/CVV" type "123";
* Press the button "Продолжить".

**Expected result:**
* Under field "Год" red colored message will appear "Неверно указан срок действия карты".

_**2.13.** Insuanse of credit with status "APPROVED" and non valid data in field "Владелец":_
* In field "Номер карты" type "4444 4444 4444 4441";
* On field "Месяц" type "08";
* In field "Год" type "25";
* Field "Владелец" filled with "Faker" data generation library on latin alphabet.
* In field "CVC/CVV" type"123";
* Press the button "Продолжить".

**Expected Result:**
* Under field "Владелец" red colored message appears "Неверный формат".

_**2.14.** Send empty field «Кредит по данным карты»:_
* Press the button "Продолжить".

**Expected result:**
* Under fields "Номер карты", "Месяц", "Год", "CVC/CVV", red colored message appeares "Неверный формат";
* Under field "Владелец" -  message "Поле обязательно для заполнения". 
* Data not sent.

_**2.15.** Input on field «Кредит по данным карты» with valid data after incorect form sending:_
* Press the button "Продолжить".
* In field "Номер карты" type "4444 4444 4444 4441";
* in field "Месяц" type "08";
* In field "Год" type "22";
* Field "Владелец" filled with "Faker" data generation library on latin alphabet.
* In field "CVC/CVV" type "123";
* Press the button "Продолжить".

**Expected result:**
* After pressing button "Продолжить", with emty data fields,data is not sent. 
   * Under fields "Номер карты", "Месяц", "Год", "CVC/CVV", red colored message will appear  "Неверный формат»
   * Under field "Владелец" - message "Поле обязательно для заполнения».
* With correct typed data, button "Продолжить" changing to "Отправляем запрос в Банк..." with spinning loading indicator. 
   * Data is sent. 
   * In top right corner pop up message will appear "Операция одобрена Банком".
   * Pop up window with message «visible».
* Red colored messages , with incorrect data messages or no data messages, not appeared.


_**2.16.** Input on form «Кредит по данным карты» with non valid data:_
* In field "Номер карты" type "9999 9999 9999 9999";
* In field "Месяц" type "80";
* In field "Год" type "99";
* Field "Владелец" filled with "Faker" fata generation library on cyrillic;
* In field "CVC/CVV" type "66";
* Press the button "Продолжить".

**Expected result:**
* Под полями "Номер карты", "Месяц", "Год", "Владелец", "CVC/CVV", появляется сообщение красными буквами "Неверный формат".

### List of tools to be used:
_**1. IntelliJ IDEA** - Integrated development enviroment;_

Advantages:
* Code highlight;
* Autofill;
* Hotkeys;
* Customization;
* Plugin shop.

_**2. Java (JDK 11)** - OOP oriented code language;_
  
Advantages:
* Simple;
* Object oriented;
* Security;
* Performance;
* Stability;
* Independent from hardware and OS;
* Dinamical & Adapted;
* Convenient & effective network possibilities;

_**4. Gradle** - Code build system;_

Advantages:
* JVM new generation build framework,includes Ant & Maven advantages;
* Uses Groovy DSL instead of XML;
* Supports dependency control methods, compatible with Maven и Ivy;
* Supports Ant и Maven migration.

_**5. JUnit5** - library for code testing;_

Advantages:
* Usee functionality of Java 8 or later versions;
* Added a lot of functions for test writing;
* Added support for multiple testing processes.

_**6. Lombok** - library for code generation;_

Advantages:
* Simple code generation;
* No semantics;
* Works foe every version from Java 6

_**7. Selenide** - tool for web services testing;_

Advantages:
* Integrated delay
* Browser shutdown after tests
* Code is simple and convinient for reading
* Auto screenshot of failed tests
* Selinium compatible.

_**8. AppVeyor** - CI for testing;_

Advantages:
* Support of multiple VCS:
* GitHub.com & GitHub Enterprise
* Bitbucket.com &  Bitbucket server
* GitLab.com & GitLab Enterprise
* Azure DevOps (repositories Git & TFVC)
* Configuration of CI projects through user interface or file appveyor.yml.
* Full sud acsess to virtual machine
* SQL Server 2017 for Linux.
* Bash & PowerShell for build flow managment.
* Parralel configuration for Windows & Linux.
* Integrated Docker service.
* Integrated NuGet server.
* Cross platform Build Worker API like in  Windows (messages, test result).

_**9. Allure** - tool to create informative testing reports;_

Advantages:
* Support any code language;
* Informative test reports;
* Modularity & extensibility.
  
_**10. Faker** - Generation data library for  fake users;_

Advantages:
* Faker allows to ease random data generation for testing.
  
_**11. Git** - Version Control System;_

Advantages:
* Rollback to any development version; 
* Logging of any project changes ;
* Fast and convinient file updates on server (сравнивал на личном опыте, это удобней FTP загрузки);
* Team work support.

_**12. GitHub** - most popular VCS._

Advantages:
*  VCS with offline support.
* GitHub is most popular VCS with alot of open source projects and big communities.
* GitHub has side integrations to ease work processes.
---

### List of automation risks:
* There can be errors in autotests writig;
* There can be errors in autotests due to technical difficulties;
* There can be errors in autotests due to code changing;
* There can be unjustified costs of automation;
* There can be errors with card emulator ;
* There can be difficulties with launch & set up of DB ("MySQL" и "PostgreSQL"), and valid connection to them.

### Interval estimation with risks (in hours):
**Interval estimation of tests automation is 72 hours.**
1. Planing phase: 20 hours;
2. Tests automation: 36 hours;
3. Report documentation of tests automation: 8 hours;
5. Risks & unexpected consequences managment (+15%-25% time) ~10-18 hours.

### Deadlines & time managment:
1. Planing phase: up to 23.07.2021
2. Testing Automation: up to 28.07.2021
3. Test Reports & summary documents: up to 04.08.2021
4. Automation report & summary: up to 10.08.2021