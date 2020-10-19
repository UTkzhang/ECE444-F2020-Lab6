# ECE444-F2020-Lab6
flaskr-tdd: https://safe-river-51243.herokuapp.com/

# Part 2
https://github.com/ECE444-2020Fall/project1-plateup-group5-pyromaniacs/blob/master/PlateUp-flask/tests/run_test.py#L1-L61

# Part 3 (What are the pros and cons of TDD?)
Since this lab was about test-driven development, I will begin by sharing some positives. I will present some points from lecture as well as mix in my own opinions.<br/>

1. Close to 100% test coverage, which minimizes errors during runtime <br/>
This is something that a lot of production software aspires to achieve, with the industry standard being 70-80 coverage. Having good test coverage (assuming that the test pipeline is integrated into development and deployment) means that you code is constantly being checked for errors. Every time you make a push, a merge, or a deployment, there is an automated process that picks up errors which human reviewers may have missed. Through TDD, it is "impossible" to slack off from achieving a very high test coverage, because the tests are written first before development even begins. This also helps with refactoring code later on, because the more test coverage you have, the less likely you are to break something during a refactor assuming that the tests pass. Having the high test coverage is definitely a positive. 

2. It enforces a clear contract ("blackbox" requirements) to encapsulate features and functions <br/>
I believe this is one of the biggest benefits of TDD, the fact that developers are forced to establish a common interface for all the ins and outs of a software feature before the feature development starts. One specific example of this is during API testing, we need to know exactly what the endpoint is expecting in terms of the HTTP method (i.e. GET/POST/etc) and the params, and also what the endpoint returns. Writing the test is a huge amount of work during API testing because a lot of the logic is focused on the I/O of the API. In order to pass the tests you've written, during feature development, your functions must respect the I/O that the tests have defined.

3. Your code works just because you have followed TDD
If TDD was followed, and we take the tests that are written as the "ground truth", i.e. if you program passes your tests then it is correct, then developers can only ever merge code that works by definition. Therefore, just by following TDD, your code will always been correct. Every new feature/function you contribute will be a postive non-breaking contribution to the codebase, and this is a good thing for collaborative development especially. 

Now, some cons.<br/>

1. Slower development process
Developers are usually not as familiar with TDD since it isn't practiced as often in the industry. One of the reasons is that TDD may be slower than conventional feature-first test-second development, directly due to point 2 in the "pros" section. In super-agile development, developers simply do not know what the specific requirements are, they'd rather have something that works on some arbitrary test-data, and then thinking about how best to adjust inputs/outputs. Also, through TDD, due to the code coverage, there will usually be a lot more tests written. This takes extra time that could otherwise be spent on features.

2. Lots of mocking may be required
Alot of TDD and unit testing specfically is reliant on mocking things. In complex code environments like large scale production software, setting up these mocked data structures and function calls are non-trivial. During my experience in the industry, I found that especially with large object oriented programs (OOPs), mocking is an nightmare as each object you mock has deeper parent objects that need to be mocked. So, setting up a mocking infrastructure is a big initial investment for most programs, and this contributes to point 1. 

3. Assumes test is correct, i.e. the "ground truth", which is usually not the case
In the "pros" section, point 3 is really only valid if this assumption holds. A lot of times, the tests that are written are determined to be infeasible later on, and then a back-en-forth process is required to fix the test, and fix the code, etc. We can think about it this way, in TDD the "tests" you are written really becomes your "feature" (since you're writing them first), and its difficult to eleminate all the bugs in these tests. Do you need tests for your tests? This point also contributes to point 1.
