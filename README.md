# Quality Code Checklist

Welcome to the Quality Code Checklist Repository! This repository is dedicated to providing a comprehensive checklist for writing high-quality code based on insights from various online articles.

## Articles
### 1.[What Is Code Quality? Overview + How to Improve Code Quality](https://www.perforce.com/blog/sca/what-code-quality-overview-how-improve-code-quality)

This article delves into code quality metrics, exploring the subjective nature of what constitutes good and bad code. It highlights the significance of code quality and its far-reaching impact on software reliability and security, particularly in safety-critical systems.

Code quality encompasses factors like cleanliness, longevity, consistency, functionality, clarity, and documentation.Even rigorous testing and manual code reviews may fall short in uncovering all code errors, as studies suggest low efficiency rates in these processes.

Low-quality code harbors potential risks, especially when it comes to safety or security breaches, potentially resulting in catastrophic outcomes.
Achieving high-quality code is a shared responsibility among developers, testers, and managers throughout the development cycle.

Measuring code quality requires a nuanced approach, considering aspects such as reliability, maintainability, testability, portability, and reusability. Metrics like defect count, severity, cyclomatic complexity, and Halstead complexity are crucial for assessing code quality. Improving code quality involves using coding standards, analyzing code early, following best practices in code reviews, and selectively refactoring legacy code. Early quality analysis can lower long-term maintenance costs and reduce technical debt.

Selecting the right code quality tools, such as static analyzers like Helix QAC and Klocwork, can facilitate adherence to coding standards and overall quality improvement.

#### Checklist Summary

- [x] Understand that code quality is a subjective concept, varying between teams and contexts.
 Recognize that high-quality code is essential for software reliability, security, and safety, especially in critical systems.
 - [x] Good code is clean, stands the test of time, and does what it's supposed to.
 - [x] Good code follows a consistent style, making it easy to read and understand.
 - [x] Ensure good code is well-documented and can be tested effectively.
 - [x] Acknowledge that manual code reviews and testing are essential but may not catch all errors.
 - [x] Understand that individual programmers may be less than 50% efficient at finding bugs in their own software, and most testing methods are only 35% efficient.
 - [x] Recognize that low-quality code introduces safety and security risks.
 - [x] Understand the potential catastrophic consequences of software failure due to code quality issues.
 - [x] Embrace the idea that achieving high code quality is a shared responsibility involving developers, testers, and managers.
 - [x] Acknowledge that there is no one-size-fits-all method for measuring code quality.
 - [x] Understand that key code quality aspects include reliability, maintainability, testability, portability, and reusability.
 - [x] Consider metrics such as defect counts, defect severity, cyclomatic complexity, and Halstead complexity for assessing code quality.
 - [x] Use a coding standard to ensure code consistency and readability.
 - [x] Analyze code before code reviews to catch quality issues early.
 - [x] Follow code review best practices for improved software quality.
 - [x] When necessary, refactor legacy code to reduce complexity and improve quality.
 - [x] Recognize the importance of early code quality analysis.
 - [x] Understand that introducing quality early can reduce long-term maintenance costs and technical debt.
 - [x] Consider using code quality tools like static analyzers (e.g., Helix QAC and Klocwork) to enforce coding standards and monitor quality metrics.

### 2.[Clean Code in PHP: Best Practices and Principles](https://medium.com/@teal33t/clean-code-in-php-best-practices-and-principles-8ccf2f1673a7)

 #### Checklist Summary

 ##### 1. Code should be easy to read

 - [x] Use meaningful variable and function names.
- [x]  Follow proper indentation and formatting for readability.
Example:

Bad Practice:

``` php
function x($a){$b=0;for($i=0;$i<count($a);$i++){$b+=$a[$i];}return $b;}
```
Good Practice:

``` php
function sumArray($numbers) {
    $total = 0;
    for ($i = 0; $i < count($numbers); $i++) {
        $total += $numbers[$i];
    }
    return $total;
}
```
##### 2. Code should be DRY (Don't Repeat Yourself)

 - [x] Avoid redundant code by refactoring it into reusable functions or classes.
Example:

Bad Practice:

``` php
function getFullName($firstName, $lastName) {
    echo $firstName . ' ' . $lastName;
}
```
``` php
function getUserName($firstName, $lastName) {
    echo substr($firstName, 0, 1) . $lastName;
}
```
Good Practice:

``` php
function getFullName($firstName, $lastName) {
    return $firstName . ' ' . $lastName;
}
```
``` php
function getUserName($firstName, $lastName) {
    return substr($firstName, 0, 1) . $lastName;
}
```
##### 3. Code should be modular

 - [x] Break code into smaller, reusable modules or functions with a single responsibility.
Example:

Bad Practice:

``` php
function userRegistration($firstName, $lastName, $email, $password) {
    // ...
}
```
Good Practice:

``` php
function validateInput($firstName, $lastName, $email, $password) {
    // ...
}
```
``` php
function createUser($firstName, $lastName, $email, $password) {
    // ...
}
```
``` php
function sendWelcomeEmail($email) {
    // ...
}
```
``` php
function userRegistration($firstName, $lastName, $email, $password) {
    // ...
}
```
##### 4. Code should be efficient

 - [x] Consider performance and resource utilization when writing code.
Example:

Bad Practice:

``` php

function findElement($array, $element) {
    for ($i = 0; $i < count($array); $i++) {
        if ($array[$i] === $element) {
            return true;
        }
    }
    return false;
}
```
Good Practice:

``` php

function findElement($array, $element) {
    return in_array($element, $array);
}
```
##### 5. Code should be robust and handle errors gracefully

 - [x] Validate inputs and handle exceptions properly to prevent crashes or unpredictable behavior.
Example:

Bad Practice:

``` php

function divide($num1, $num2) {
    return $num1 / $num2;
}
```
Good Practice:

``` php

function divide($num1, $num2) {
    if ($num2 == 0) {
        throw new InvalidArgumentException("Cannot divide by zero.");
    }
    return $num1 / $num2;
}
```
##### 6. Code should be testable

 - [x] Design code to be easily testable using unit tests, with clear inputs and outputs.
Example:

Bad Practice:

``` php

class Order {
    // ...
}
```
Good Practice:

``` php

class Order {
    // ...
}
```
##### 7. Code should follow a coding standard

 - [x] Adhere to a coding standard or style guide to maintain consistency and readability.
Example:

Bad Practice:

``` php
class myClass {
    // ...
}
```
Good Practice:

``` php

class MyClass {
    // ...
}
```
##### 8. Code should be well-documented

 - [x] Use comments and PHPDoc blocks to explain complex logic and provide structured documentation.
Example:

Bad Practice:

``` php
// Adds 1 to the number
function addOne($num) {
    return $num + 1;
}
```
Good Practice:

``` php

/**
 * Increments the given number by one.
 *
 * @param int $num The number to increment.
 * @return int The incremented number.
 */
function increment($num) {
    return $num + 1;
}
```
This checklist summarizes the key principles and examples for writing clean code in PHP, promoting readability, maintainability, and code quality.

### 3. [Code Quality: What It Is and How To Measure It (With Tips)](https://www.indeed.com/career-advice/career-development/what-is-code-quality)

#### Code Quality Measurement Checklist Summary

##### 1. Code Quality Definition

 - [x] Code quality is a measurement of how high or low the value of a specific set of code, program, or software is.
 - [x] High-quality code possesses characteristics such as being functional, consistent, easy to understand, meeting client needs, testable, reusable, bug-free, secure, and well-documented.

##### 2. Importance of Code Quality

- [x]  Enhances the end user's experience.
- [x]  Demonstrates safety and reliability of the software.
- [x]  Low-quality code can lead to security issues, code errors, and functionality problems.
- [x]  Code quality improves readability, program sustainability, transferability, and reduces costs related to software maintenance.
##### 3. How to Measure Code Quality

- [x]  Measure the code's reliability by testing its ability to function without failures over time.
- [x]  Use static analyzers to identify defects and faults in the code.
- [x]  Determine the code's complexity level using metrics like cyclomatic complexity.
- [x]  Test the code's portability on different platforms, devices, and browsers.
- [x]  Assess the code's reusability by examining interdependencies.
- [x]  Measure the code's testability by running tests to identify errors.
- [x]  Use code-checking tools to automatically scan and suggest improvements.
##### 4. Tips for Improving Code Quality

- [x]  Follow coding best practices, including adhering to coding standards and guidelines.
- [x]  Periodically improve old code to align with best practices.
- [x]  Simplify complex code to enhance readability and maintainability.
- [x]  Ensure that the code is easy to read and interpret by both humans and machines.
- [x]  Document the code effectively to provide context and understanding.
- [x]  Emphasize simplicity in code design to facilitate future modifications.
- [x]  This checklist summarizes the key aspects of understanding, measuring, and improving code quality, which is crucial for creating reliable and maintainable software or programs.




