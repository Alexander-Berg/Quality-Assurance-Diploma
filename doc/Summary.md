# Automation report
## Scheduled:

1. Planing of tests automation.
    
2. Automation:
   * Automation of positive & negative UI scenarios, tour purchase service testing ("Оплата по карте" и "Кредит по данным карты");
   * Automation of API csenarios;
   * Implementation of support MySQL DB & PostgeSQL;
   * Integration with report systems (Gradle/Allure);
   * Integration with report system (Appveyor CI).
   
3.Prepararion of test automation documentation
   
## Done

1. By automation plan ([Plan.md](Plan.md)),
in project was implemented tests automation of all planned scenarios:
   * Positive scanarious of tour purchase with debit card;
   * Positive scenarios of tour purchase by card on credit;
   * Scenarios of positive & negative testing for all type fields (Card Number, Month, Year, Owner, CVC/CVV).

2.Integrated to work with Appveyor CI ([.appveyor.yml](../.appveyor.yml)).

3. Integrated to work with Gradle/Allure ([build.gradle](../build.gradle)).
   
4.Report was made after testing: ([Report.md](Report.md))
   Inside the report:
   * Test cases count;
   * Succesful/failed cases statistics percentage;
   * General recomendations about bug fixing.
   
## Triggered risks:
* Spent more time than planned to configure & launch Bank cards emulator;
* Some difficulties with 2 DB start ("MySQL" и "PostgreSQL"), and correct connection to them;
* Some difficulties with writing DB tests;
* Spent more time than planned to Appveyor CI integration.

## Time Summary:
1. Test plan development:
   Planned - 24 hours, actually spent - 19 hours.
2. Software and tools preparation, autotests writing: 
    * Planned - 32 hours, spent - 48 hours.
3. Reporting summary documentation : 
    * Planned - 8 hours, spent - 6 часов.
4. Bugs search and documentation:
    * Planned 8 hours, +15%-25% for risks, spent 9 hours.

### Plan of time management: 
* 70 hours +15%-25% with risks (~10-18 часов).

### Time spent: 
* 72 hours

## Time spent Summary:
1. Tests automation planni: 
    * Planned deadline 23.07.2021, done 20.07.2021.
2. Tests Automation: 
    * Planned deadline 05.08.2021, done 26.07.2021.
3.  Tests  Automation Report docs : 
    * Planned deadline 10.08.2021, done 30.07.2021.
4. Automation accounting documents: 
    * Planned deadline 16.08.2021, done 2.08.2021.