Software testing:
- A process to validate a software application
- Observing, recording and comparing the behaviour (output) of the software with the intended behaviour and output
- Main purpose of testing is to try to find errors


- Testing should be done early and often
- No need to wait until all operations of a software component are fully implemented
- Even a smallest change on a piece of code may invalidate the entire system
	- Testing should be done whenever changed are made


Test Data:
- Should test the software to its limits and test business rules
- Should include:
	- Extreme values (out of bound)
	- Borderline values (-1, 0.999)
	- Invalid combinations (age=3, marital status=married)
	- Nonsensical values (negative order line quantities)
	- Heavy loads (are performance requirements met)


- Test scripts should be build and executed by specialist test teams who have access to software
- Testing should be done by business and systems analysts
- in eXtreme Programming (XP), programmers are expected to write test harnesses:
	- software framework that imitates missing infrastructure allowing automated testing
- Intended users of the system should test against requirements, a.k.a user acceptance testing


Black Box testing:
- Seeks to establish whether the end-product  does what it's meant to do
	- Checking FR and usually done by system analysts

White Box testing:
- Seeks to establish whether the end-product delivers a good solution, not just a solution to the problem
	- Checking FR/NFR, and is usually done by the developers



Types of testing:
- Unit Testing:
	- Ensures that individual classes work 

- Interface testing:
	- Validates the functions exposed by components

- Integration testing:
	- Establishes whether all components in the system work correctly together

- Subsystem testing:
	- Checks if each subsystem works correctly and delivers the required functionality

- System testing:
	- Checks if the WHOLE system works seamlessly 

- Acceptance testing:
	- Checks if the system works as required by the users and according to the specification

- Usability testing:
	- Tests if the intended users are satisfied with the software application in addressing its intended purpose

- Regression testing:
	- Ensures that changes made to the source code have not introduced defects in the existing source code

- Installation testing:
	- Checks how well the software application works on the required platform

- Robustness testing:
	- Establish the ability of the software application in handling anomalies (being trustworthy)

- Mutation testing:
	- Introduce statement/value/decision "mutants" in purpose, to see how the system reacts

- Performance testing:
	- Check if the system is fast enough and it used acceptable amount of memory (e.g. is under stress)



Levels of testing:
- Level 1:
	- Testing components (i.e. classes), then program (i.e. use cases), then suites (i.e. application)
- Level 2:
	- (Alpha Testing or Verification)
	- Execute programs in a simulated environment and test inputs and outputs
- Level 3:
	- (Beta Testing or Validation)
	- Test in a live use environment and test for response times, performance under load and recovery from failure, etc.

![[Pasted image 20241031135120.png]]

- Regression testing:
	- Process in which the software is retested so as to ensure that its behaviour has not been compromised by the addition of new, or change to existing code
	- Facilitates faster development:
		- Reduces risk of changes
		- Unexpected effects can be found quickly
		- Ability to run thousands of tests in one click
	- Important but can be very time and cost consuming:
		- Requires capturing of data, analysis, reporting, etc.
	- ![[Pasted image 20241031135422.png]]
	- If C1 depends on C2 then yes
	- If C1 does not depend on C2 then no
	- If unsure, yes


Test plans:
- Written before the tests are carried out
- Written, in fact, before the code is written
- Contain test cases

Test cases:
- Specified with the following information:
1. Test data
2. Expected outcomes
3. Description of the test
4. Test environment and configuration

Test Results:
- Used for analysis, recorded in a spreadsheet, database or a specialist package (e.g., Jira)
- Record when tests are failed or passed
- Include statistics, e.g., percentage of passed/failed
- Ideally should be linked to requirements (traceability)
- Error results should be recorded in a fault reporting package, with enough details for developers to reproduce them with a view to fixing the bugs


Test Planning - Steps:
1. Define what is meant by a "testing unit".
2. Determine the types of testing to be performed
3. Determine the extent of the testing (i.e., prioritise the tests)
4. Determine how to document the testing procedures
5. Determine input sources
6. Decide who will perform which tests
7. Estimate resources
8. Identify metrics to be collected

Determine the extent of testing:
- Software should be thoroughly tested before release, but when should testing stop?
- There is no "one size fits all" scheme, in software testing.
- Testing team should establish a set of stopping criteria
	- A tester is unable to find another defect in n minutes of testing 
	- When all nominal, boundary and out-of-bounds test data show no defect
	- When testing runs out of its scheduled time (DANGEROUS)


Unit testing:
- Performed to test parts (classes and their methods) of an application in isolation
- Black box unit testing:
	- Equivalence partitioning: 
		- divide input values into equivalent groups
	- Boundary value analysis:
		- test at boundary conditions
- White box unit testing:
	- Code coverage:
		- Test cases cause every line of code (statement), all conditions (branch) and all possible flows (path), from entry to exit, to be executed

Assertions:
- statements in java which ensure the correctness of assumptions
- allow us to enforce business rules and catch any mistakes
- allow us to check for parameter and return values
- generally, allow us to check for something that should never happen


Junit:
- A framework for unit testing which facilitates the writing of repeatable tests.
- Usually import:
	- `org.junit.jupiter.api.Assertions`
	- `org.junit.jupiter.api.Test`
- Annotates a test method with @Test
- Uses assert- methods, i.e., `assertFalse, assertTrue, assertEquals, assertThrows` etc.

- Fixtures allow you to set up a testing environment:
	- prepare the baseline of your tests
	- Usually have the following lifecycle:
		1. `@BeforeAll`
		2. `@BeforeEach`
		3. `@Test`
		4. `@AfterEach`
		5. `@AfterAll`
	
	- Before annotations for the preparation of test data
	- After annotations for house keeping


Test-Driven Development:
- Different approach to writing software
- Development of the application is driven by the test cases solely
- Writing test cases before writing any source code
- Code that does not address the issues in the test cases will not be written

![[Pasted image 20241031141845.png]]

- Advantages:
	- Test cases ensure a good statement coverage
	- Only code required to address the requirements is written; no redundancy 
	- Rapid feedback on the written code
	- Test suite available for further testing purposes, e.g., regression testing