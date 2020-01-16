# Testing

### Automated Testing
Before talking about deploying your code, I need to first talk about testing your code.
Deploying code that you are not confident will work is dangerous. You need to be able
to run a variety of tests against your code, everything from the lowly unit test that covers
individual functions to acceptance tests that ensure a whole system is functioning.
Tests should be as easy to run as executing a command within the working directory
of your project. This will make it easy both for humans and for automated testing software
to run tests.

### Unit Tests
Unit tests are the most basic level of testing you can use in a project. These tests run
individual functions within your codebase, passing in different parameters to ensure each
branch of code in the function runs.
This is also the level where developers are usually checking code coverage. All
popular modern languages have tools for testing code coverage as unit tests run. As a rule
of thumb, the closer you approach 100 percent code coverage, the closer you approach
100 percent confidence in your code.
In your project, set up a threshold for code coverage. New pull requests that add
features but do not test features will lower the overall coverage level and cause a failure.
This makes for an excellent reason to deny a contribution.

### Smoke Tests
Smoke tests are used as a sanity check in the testing process before running other types
of tests. In particular, they are useful for talking to services outside of your own to ensure
those services are functioning as expected.
If the smoke tests fail, you know that you shouldn’t bother running your tests that
talk to other services. If you don’t use smoke tests, then you can assume that failed tests
are because of faulty code when it may in fact be because of someone else’s project.

### Integration Tests
Integration tests are useful for checking how larger parts of the system work together.
While a unit test may ensure that the input and output of a single function is correct, an
integration test will ensure that the output of a function is compatible with the input of
another function.
You may even check that your service functions properly with other services. This could
include making connections to databases, caching services, or making outbound requests to
other services within the organization. These types of tests usually end up being the “flakiest”
because real-world network and data issues can affect the outcome of the tests.

### Acceptance Tests
Acceptance tests check that the particular needs of the business are being fulfilled by the
application. An individual acceptance test can be as complex as a user story or as simple
as a single interaction. For example, if a service has a parameter that sorts results, then
a relevant acceptance test would be to make a request with the parameter and ensure
results are sorted properly.
If a service has a web interface, it’s not uncommon to create a headless browser
instance, make a request to a web page, click elements, and ensure that the expected data
comes back. This may require the service to communicate with other services, such as an
integration test, or instead make use of mock data.

### Performance Tests
It’s a good idea to keep track of performance data with each test run. Perhaps you have a
certain set of requests that are frequently made in groups such as the flow of a user signing
up and authenticating and making a purchase. By benchmarking these requests and then
running them hundreds of times in a row, you can see whether new commits are slowing
you down. Set a threshold and fail a contribution if it makes the service too slow.
Regression Tests
Regression testing is used to ensure that code that used to work will still work after
changes have been made. This could mean running all the other tests every single time
you make changes. It could also mean running any subset of those tests. Many large
organizations will find themselves with teams of quality assurance (QA) experts who may
even write their own tests and run them against your software over and over.
