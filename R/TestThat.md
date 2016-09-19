# Code snipet to use testthat for unit testing R code

     context('Title of the test set')
     source('R_file_to_test.R')

     # Some code to prepare/to be used in the test

    test_that('Description of the tested action 1 ',{
    test<- # result of computed test or function to test
    result<- #expected result

    expect_equal(test,result, tolerance=1e-4) # for float tolerence is require for equal to work properly
    expect_true(test)
    expect_false(test)
    expect_is(x, y)
    expect_equal(x, y)
    expect_equivalent(x, y)
    expect_identical(x, y)
    expect_matches(test, '^Hello .*') #matches  a  character  vector  against a  regular  expression
    expect_output(test(x), 1:2)
    expect_message(test(x), 'Hello world')
    expect_warning(test(x), 'have NA')
    expect_error(test(x), 'invalid state')

    })

    test_that('Description of the tested action 2 ',{
    })

    # etc ...


run one test file

    test_file('file_name.R')


run all the test file (starting with test) in a folder

    test_dir()


each test_* result is a '.' (or error num) in the test output
