### Introduction

This second programming assignment will require you to write an R
function that is able to cache potentially time-consuming computations.
For example, taking the mean of a numeric vector is typically a fast
operation. However, for a very long vector, it may take too long to
compute the mean, especially if it has to be computed repeatedly (e.g.
in a loop). If the contents of a vector are not changing, it may make
sense to cache the value of the mean so that when we need it again, it
can be looked up in the cache rather than recomputed. In this
Programming Assignment you will take advantage of the scoping rules of
the R language and how they can be manipulated to preserve state inside
of an R object.



<!-- -->

    makeCacheMatrix <- function(x=matrix()) {
   inverse <- NULL
   set <- function(y){
        x <<- y
        inverse <<- NULL
   }
   get <- function() (x)
   setInverse <- function(inversecalculated) (inverse <<- inversecalculated)
   getInverse <- function() (inverse)
     list(set= set, get = get,
          setInverse = setInverse,
          getInverse = getInverse)
 }



   cacheSolve <- function(x, ...) 
   {
     inverse <- x$getinverse()
     if(!is.null(inv)) {
       message("getting cached data")
       return(inverse)
     }
     data <- x$get()
     inverse <- solve(data, ...)
     x$setinverse(inverse)
     inv
   }
   

