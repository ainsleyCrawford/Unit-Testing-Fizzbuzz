# Unit Testing Fizzbuzz
The aim of this project was to verify a fizzbuzz program through component testing.

## Test Basis: What is Fizzbuzz?
A fizzbuzz program counts upwards from 1, outputting whole numbers except multiples of 3, which are replaced by "Fizz", and multiples of 5, replaced by "Buzz". Common multiples output the hybrid "FizzBuzz". To demonstrate:  
<p align="center"><i>1, 2, "Fizz", 4, "Buzz", "Fizz", 7, 8, "Fizz", "Buzz", 11, "Fizz", 13, 14, "FizzBuzz", 16, ad infinitum.</i></p>

## Program Specification: How to Code FizzBuzz
A single if-else statement sufficiently filters every number to generate the correct sequence. The if-statement first vefifies the input (an integer) is a multiple of both 3 and 5. Two statements which may achieve this are `if (value % 3 == 0 & value % 5 == 0)` and, more simply, `if (value % 15 == 0)`. If this condition is not met then the input is verified as a multiple of 3 and 5 individually. If none of these conditions are met, then the input itself is returned as an output.

## Unit Test Planning: How to Test Fizzbuzz
As there are 4 general outputs to expect—Fizz, Buzz, FizzBuzz and the returned input—the minimum number of unit tests is four, assuming each unit test acts as a test case for a different test condition. Fizz is tested by inputting any multiple of three; Buzz, any multiple of five; and FizzBuzz, any multiple of 15.

There are various ways to create unit tests. This particular solution involves adding a reference to a C# unit test project. This project-type automatically generates a `[TestClass]` attribute above a class and similar metadata, `[TestMethod]`, above a method. After producing an object of `FizzBuzzClass` the expected outputs (eg. "Fizz") can be verified against given inputs (eg. 42) using `Assert.AreEqual`.

## Test Cases
**Project Name:** Fizzbuzz  
**Created By:** Ainsley  
**Creation Date:** 27/12/19  
**Test Condition ID:** A  
**Test Condition Description:** Verify that the fizzbuzz program returns "Fizz" when the input is divisible by three and not five.  
**High-Level Test Case:** Input is divisible by 3, but not by 5; thus "Fizz" is outputted.

|Test Case ID|Test Data|Expected Outcome|Actual Outcome|Status|
|:----------:|:-------:|:--------------:|:------------:|:----:|
|A-01        |3        |"Fizz"          |"Fizz"        |Passed|
|A-02        |-3       |"Fizz"          |"Fizz"        |Passed|
|A-03        |-6       |"Fizz"          |"Fizz"        |Passed|
|A-04        |42       |"Fizz"          |"Fizz"        |Passed|

**Test Condition ID:** B  
**Test Condition Description:** Verify that the fizzbuzz program returns "Buzz" when the input is divisible by five and not three.  
**High-Level Test Case:** Input is divisible by 5, but not 3; thus "Buzz" is outputted.

|Test Case ID|Test Data|Expected Outcome|Actual Outcome|Status|
|:----------:|:-------:|:--------------:|:------------:|:----:|
|B-01        |5        |"Buzz"          |"Buzz"        |Passed|
|B-02        |-10      |"Buzz"          |"Buzz"        |Passed|
|B-03        |20       |"Buzz"          |"Buzz"        |Passed|
|B-04        |605      |"Buzz"          |"Buzz"        |Passed|

**Test Condition ID:** C  
**Test Condition Description:** Verify that the fizzbuzz program returns "Fizzbuzz" when the input is divisible by fifteen.  
**High-Level Test Case:** Input is divisible by 15; thus "Fizzbuzz" is outputted.

|Test Case ID|Test Data|Expected Outcome|Actual Outcome|Status|
|:----------:|:-------:|:--------------:|:------------:|:----:|
|C-01        |15       |"FizzBuzz"      |"FizzBuzz"    |Passed|
|C-02        |-30      |"FizzBuzz"          |"FizzBuzz"        |Passed|
|C-03        |45       |"FizzBuzz"      |"FizzBuzz"    |Passed|
|C-04        |60       |"FizzBuzz"            |"FizzBuzz"          |Passed|

**Test Condition ID:** D  
**Test Condition Description:** Verify that the fizzbuzz program returns the inputted number when it is neither divisible by 3 nor 5.  
**High-Level Test Case:** Input is neither divisible by 3 nor 5; thus the input is outputted.

|Test Case ID|Test Data|Expected Outcome|Actual Outcome|Status|
|:----------:|:-------:|:--------------:|:------------:|:----:|
|D-01     |1       |"1"          |"1"        |Passed|
|D-02     |-4       |"-4"          |"-4"        |Passed|
|D-03     |7       |"7"      |"7"    |Passed|
|D-04     |11       |"11"            |"11"          |Passed|
