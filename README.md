# Package Template

## Setup Package

 - turn this repository into an R package: `devtools::create_description()`
 - rename the package by changing the name in the `DESCRIPTION` file
 
## Add function(s)
 
 - create an R Script (`.R`) file in the `R` folder and write a simple function, e.g.:
  - ```R
    #' Add together two numbers.
    #' 
    #' @param x A number
    #' @param y A number
    #' @return the The sum of \code{x} and \code{y}
    #' @examples
    #' add_numbers(1, 2) # add 1 + 2
    #' @export
    add_numbers <- function(x, y) {
      return(x+y)
    }
    ```
 - load the package directly into memory: `devtools::load_all()` (`Ctrl/Cmd` + `Shift` + `L`)
 - call your function from the console to test it, e.g. with `add_numbers(2, 5)`
 - NOTE: all package functions are available if loaded this way but only the ones that have `@export` in their documentation will be made available to your users via regular installation

## Add documentation

 - generate the documentation `devtools::document()` (`Ctrl/Cmd` + `Shift` + `D`)
 - test documentation of your function, e.g. with `?add_numbers()`
 - test the top-level documentation of your package, e.g. with `?packagename`
 - check your `NAMESPACE` to see what it contains

## Add testing

 - set up the testing environment: `devtools::use_testthat()`
 - create an R Script (`.R`) file in the `test/testthat` folder and write a simple test, e.g.:
 - ```R
    test_that("Math works", {
      expect_error(add_numbers())
      expect_equal(add_numbers(1, 1), 2)
    })
   ```
 - run all package tests: `devtools::test()` (`Ctrl/Cmd` + `Shift` + `T`)
 
## Check entire package

 - to check proper formatting, all examples, and all tests of the package: `devtools::check()` (`Ctrl/Cmd` + `Shift` + `E`)

## Build package

 - to build and formally install the package from within this project: `devtools::install()` (`Ctrl/Cmd` + `Shift` + `B`)
 - to install it from GitHub: `devtools::install_github('USER/REPO')`
 
