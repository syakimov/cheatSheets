Stub and Mock => ways to go around the things you do not test

Stub
  description: has the same interface as the original object
  data input is not important:
    create a stub method ex.: `stub_picard`
    the returned value DOES NOT affect the test result
      ex. stubed mail client acts as if has sent the mail
      we don't care about what happens to third party lib
  control data input:
    use allow -> data is important
    stub passes data that determines the outcome of the test
      the returned value affects the test result
      ex. stubed database returnes non existing record

Mock
  description: test scenario

Subject
  description: same as the tested object in RSpec

describe:
  description: what you test
  ex. test interest calculation

context:
  description: gives info about the input data
  ex. with negative interest


-------------------------------------------------------------------------------
Mock
  do not mock things that return data, only actions
  we want to know the params with which the mock has been called
  when we test params we need more than one example
  do not restrict more than you need
    ex.: add `once` only if it is important
    tests are used as docs so be as specific as poss
      this way you see what is important for the test
  do we have expectation for the called function
  you can pass block to the mock, useful when called more than one
  you can order the expectations but don't be too specific


-------------------------------------------------------------------------------
Stub and Mock

tests should not test implementation
one example tests one test case

Stub and mock are also used combined in one test
  stub -> we want to stub `db.insert` to return error
  mock -> we want to be sure that no `db.update` is called


-------------------------------------------------------------------------------
aggregate failures -> pass a block of expectations
  the expectation list will be treated as one
  ex.: the cube (width, height, length) params
  documentation purposes
rspec matchers -> implement method that is more descriptive
  should be in support folder
receive_messages_chain => User.where().order().first()

rubocop rspec
-------------------------------------------------------------------------------
Literature

Growing object oriented software, guided by tests
Test anti pattern

-------------------------------------------------------------------------------
Links
https://www.youtube.com/watch?v=oW_R37hOrsg
https://www.youtube.com/watch?v=RIud0jVH36s
http://rspec.info/documentation/3.4/rspec-mocks/RSpec/Mocks/ArgumentMatchers.html
http://myronmars.to/n/dev-blog/2012/06/thoughts-on-mocking
