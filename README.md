# Jooto-automation-test

This is an automation test framework for [Jooto](https://www.jooto.com/).


## Getting started
#### Intergration Frameworks
- [Cucumber in java](https://cucumber.io/docs/installation/java/).
- [Selenium 3](https://www.seleniumhq.org/download/).
- [JUnit5](https://junit.org/junit5/).


#### Setup the source Root
- For making sure that JUnit can detect the runner class, you have to setup the folder [/src](https://github.com/PRTIMES/Jooto-automation-test/tree/base-structure/src) became the source root for Java project.


#### Setup Libraries
- Before using the framework, you need to add necessary libraries beblow:
  - Apache libraries:  org.apache.commons.io & org.apache.poi in [root/lib/apache/](https://github.com/PRTIMES/Jooto-automation-test/tree/base-structure/lib/apache).
  - Selenium library: selenium-server-standalone.jar in [root/lib/Selenium](https://github.com/PRTIMES/Jooto-automation-test/tree/base-structure/lib/Selenium). From firefox 52 onwards or the others, you should use "selenium-server-standalone-3.13.0.jar".
  - Cucumber for JUnit libraries in [root/lib/cucumberJUnit](https://github.com/PRTIMES/Jooto-automation-test/tree/base-structure/lib/cucumberJUnit).
  - Others libraries: a-javabeans.jar in [root/lib/others](https://github.com/PRTIMES/Jooto-automation-test/tree/base-structure/lib/others) & JUnit5.
- You can also use [Maven dependencies](https://mvnrepository.com/) to configure the necessary library.

#### Setup Configuration Properties
- The properties is configured in [config.properties](https://github.com/PRTIMES/Jooto-automation-test/blob/base-structure/config.properties) to choose the driver paths by each OS you are using.By default, this project is configured for Linux OS.
- The format constants for @CucumberOptions is configured in [BaseConstants class](https://github.com/PRTIMES/Jooto-automation-test/blob/base-structure/src/main/com/mdm/baseLib/BaseConstants.java).

## Test Workflows
- The first, **JUnit Runner** class in [src/test/resources/suiteRunner](https://github.com/PRTIMES/Jooto-automation-test/tree/base-structure/src/test/resources/suiteRunner) will be run. Then it get the feature and glue path to find out **the feature files** need to run. By default, the feature path is [resources/features](https://github.com/PRTIMES/Jooto-automation-test/tree/base-structure/resources/features).
- Secondly, **the feature files** will be run to match with **the step definition** in java classes in [/src/test/stepDefinitions](https://github.com/PRTIMES/Jooto-automation-test/tree/base-structure/src/test/stepDefinitions).
- After that, cucumber hooks will be called to run before and after running the step definitions.
- Finally, JUnit annotations (@AfterClass) will be run to handle the project report.


## Base Classes Meaning
- **src/main/com/mdm/baseLib**: contains and only contains all of the base source code which can be used for many different test websites.
- **BaseConstants**: contains all of common constants and enumeration.
- **Driver**: contains main methods to initialize the driver.
- **ExceptionHandle**: contains methods to handle exceptions happened when running test and related to base framework code.
- **FileUtil**: contains main methods to work with files.
- **Page**: contains main methods which will be used frequently in pages.
- **TestBase**: contains main methods to work with the webdriver and elements inside it.
- **TestCase**: contains main methods to handle test hooks. 
- **Utils**: contains the other common method in base framework.


## POM(Page Object Model) Pattern
- This framework are using Page Object Model Pattern to design web UI pages and manage their actions.
- For examples: You should look at [LoginPage](https://github.com/PRTIMES/Jooto-automation-test/blob/base-structure/src/test/ebx/page/LoginPage.java) class for more details.


## Locator Management
- This framework are using excel file to manage all of the web element locators.
- For more details, see:
  - [The sample excel file **Jooto_object_repository**](https://github.com/PRTIMES/Jooto-automation-test/blob/base-structure/object_repository/Jooto_object_repo.xlsx).
  - The method _loc() in [Page class]().















