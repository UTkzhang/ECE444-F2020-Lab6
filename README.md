# ECE444-F2020-Lab6
flaskr-tdd: https://safe-river-51243.herokuapp.com/

# Part 2

# Part 3 (What are the pros and cons of TDD?)
Since this lab was about test-driven development, I will begin by sharing some positives. I will present some points from lecture as well as mix in my own opinions.
1. Close to 100% test coverage, which minimizes errors during runtime <br/>
This is something that a lot of production software aspires to achieve, with the industry standard being 70-80 coverage. Having good test coverage (assuming that the test pipeline is integrated into development and deployment) means that you code is constantly being checked for errors. Every time you make a push, a merge, or a deployment, there is an automated process that picks up errors which human reviewers may have missed. Through TDD, it is "impossible" to slack off from achieving a very high test coverage, because the tests are written first before development even begins. This also helps with refactoring code later on, because the more test coverage you have, the less likely you are to break something during a refactor assuming that the tests pass. Having the high test coverage is definitely a positive. 

2. It enforces a clear contract ("blackbox" requirements) to encapsulate features and functions <br/>
I believe this is one of the biggest benefits of TDD, the fact that developers are forced to establish a common interface for all the ins and outs of a software feature before the feature development starts. One specific example of this is during API testing, we need to know exactly what the endpoint is expecting in terms of the HTTP method (i.e. GET/POST/etc) and the params, and also what the endpoint returns. Writing the test is a huge amount of work during API testing because a lot of the logic is focused on the I/O of the API. In order to pass the tests you've written, during feature development, your functions must respect the I/O that the tests have defined.

3. Your code works just because you have followed TDD
If TDD was followed, and we take the tests that are written as the "ground truth", i.e. if you program passes your tests then it is correct, then developers can only ever merge code that works by definition. 

Now, some cons.

1. Slower development process
2. Lots of mocking may be required
3. Assumes test is correct, i.e. the "ground truth"
