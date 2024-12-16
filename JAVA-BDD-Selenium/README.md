# BDD Framework for Selenium with Java

This repository contains a Behavior-Driven Development (BDD) framework for automating web applications using Selenium WebDriver and Java. This framework uses a scenario as simple as Google search scenario. The framework is designed to support easy-to-read test scenarios written in Gherkin syntax and executed using Cucumber. It integrates with popular tools like Maven for build management and TestNG for test execution.

## Tools and Technologies Used:

1. **Language**: Java 8
2. **Testing Framework**: TestNG
3. **BDD Framework**: Cucumber-JVM
4. **Automation Tool**: Selenium WebDriver
5. **Build Tool**: Maven
6. **Logging**: Log4j
7. **Headless Browser**: PhantomJS

## Setting Up the Project

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/selenium_BDD_framework.git
   ```

2. Navigate to the project folder:
   ```bash
   cd selenium_BDD_framework
   ```

3. Install dependencies using Maven:
   ```bash
   mvn clean install
   ```

## Running the Tests

There are two scenarios: `@scenario1` and `@scenario2`. These tests are run on **Chrome 54.0** and **Firefox 46** on **Ubuntu 14.04 64-bit**.

- To run both scenarios (by default, the browser will be Chrome):
  ```bash
  mvn test
  ```

- To run tests with a configurable browser (for Firefox, use `-Dbrowser=firefox`):
  ```bash
  mvn test -Dbrowser=chrome
  ```

- To run tests headlessly (using PhantomJS):
  ```bash
  mvn test -Dheadless=yes
  ```

- To run a specific scenario (e.g., `@scenario3`):
  ```bash
  mvn test -Dcucumber.options="--tags @scenario3"
  ```

- To run multiple scenarios (e.g., `@scenario3` and `@scenario2`):
  ```bash
  mvn test -Dcucumber.options="--tags @scenario3,@scenario2"
  ```

## Features of the Framework:

1. **BDD Framework**: Uses Cucumber-JVM. Features can be written easily using Given, When, Then, etc.
2. **Configurable Browser**: The browser (Chrome/Firefox) can be configured at runtime from the command line.
3. **Headless Testing**: Tests can be run headlessly with PhantomJS if required.
4. **Screenshot on Failure**: Screenshots are taken for failed scenarios and saved under the `/outputFiles` folder.
5. **HTML Reports**: An HTML report is generated after each test run and can be found in `/target/cucumber-html-report/index.html`.

## Framework Structure:

- **Features**: Contains different test scenario files.
- **Framework**: Contains reusable framework-level code.
- **Logger Package**: Contains `Log.java`, which manages logs in the console and saves them in `LogFile.txt` for each run.
- **Logic Package**: Contains classes where actions and assertions happen. Also, includes classes to start the execution.
- **OutputFiles**: Stores all output files (screenshots, CSV, TXT files).
- **Pages**: Contains web elements corresponding to specific pages.

## Execution Report:

After running the tests, an execution report will be generated in the `index.html` file found in `/target/cucumber-html-report/`.
