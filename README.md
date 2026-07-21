# Currency Converter — with SonarQube Static Analysis

A command-line Java currency converter built as an exercise in code quality tooling: the focus of this coursework was integrating **SonarQube** static analysis into the build, alongside the converter logic itself.

## What it does

Takes an amount and a source currency as command-line arguments and prints the converted value in the other two supported currencies, using fixed conversion rates.

Supported currencies: `dollars`, `pounds`, `euros`.

## Code Quality

This project runs through [SonarQube](https://www.sonarsource.com/products/sonarqube/) for static analysis, configured via `sonar-project.properties`. SonarQube flags:

- Code smells and maintainability issues
- Potential bugs
- Duplicated code
- Cyclomatic complexity

One bug is left in deliberately, in the `pounds` conversion branch, where the dollar calculation uses `+` instead of `*`. It's there so Sonar's analysis has something real to catch and report on, rather than running against a spotless file.

## Tech Stack

- **Java**
- **SonarQube** — static code analysis

## Running it

Compile and run, passing the amount and currency as arguments:

```bash
javac CurrencyConverter.java
java CurrencyConverter <amount> <dollars|pounds|euros>
```

Example:

```bash
java CurrencyConverter 100 dollars
```

Output:

```
100.0 Dollars = 74 Pounds
100.0 Dollars = 88 Euros
Thank you so much for using the converter.
```

## About

Built for the DevOps module of my BSc (Hons) Computing at Glasgow Caledonian University — first coursework in a two-part series exploring code quality gates and CI/CD (see the companion [CI/CD pipeline project](../cicd-pipeline)).
