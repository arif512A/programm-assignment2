makeCacheMatrix <- function(x = matrix()) {

inv <- NULL
set <- function(y){
x <<- y
inv <<- NULL

}
get <- function() x
setinverse <- function(mean) inv <<- mean
getinverse <- function() inv
list (set = set, get = get, 
setinverse = setinverse,
getinverse = getinverse)
}



cacheSolve <- function(x, ...) {
inv <- x$getsolve()
if(!is.null(inv)) {
message("getting cached data")
return(inv)
}
mat <- x$get()
inv <- inverse(data, ...)
x$setinverse(inv)
inv
}        

