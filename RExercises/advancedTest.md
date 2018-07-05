## Advanced Test
### A Mystical Rite of Passage
1. Write a function that returns the phrase "Hello, World."
	* HelloWorld <- function(){
	* return("Hello, World.")
	* }
	* semicolon for new line

### Problem Set
1. Load the iris dataset we used in the earlier tests. Write a function that takes iris as its argument, and returns three subsets of the data.frame split by the three different types of species (saved as a single object).
	* Iris <- function(iris) {
	* Setosa <- iris[which(iris["Species"] == "setosa"),]
	* Versicolor <- iris[which(iris["Species"] == "versicolor"),]
	* Virginica <- iris[which(iris["Species"] == "virginica"),]
	* return(list(Setosa,Versicolor,Virginica))
	* }
2. Write a function that takes iris as its argument. The function should, for each row, add Sepal.Length and Petal.Length if Sepal.Width is > 3.1. It should substract Petal.Length from Sepal.Length if Sepal.Width is <3.1. The answer should be returned as a vector.
	* Add2Cols <- function(x){
Answer <- iris[x,"Sepal.Length"] + iris[x,"Petal.Length"]
return(Answer)
}

	* Sub2Cols <- function(x){
Answer <- iris[x,"Sepal.Length"] - iris[x,"Petal.Length"]
return(Answer)
}

	* Count<-vector(length = nrow(iris))

	* IrisFun <- function(iris){
for(i in 1:nrow(iris)){
if(iris[i,"Sepal.Width"] > 3.1){
Count[i] <- Add2Cols(i)
}
if(iris[i,"Sepal.Width"] < 3.1){
Count[i] <- Sub2Cols(i)
}
}
return(Count)
}
3. Load the mtcars dataset we used in the earlier tests. Write a function that takes a number of cylinders as its argument. Have the function return the average miles per gallon (column mpg) for all cars with that many cylinder (column cyl).
	* NewFunction <- function(cyl){return(sum(mtcars[which(mtcars$cyl == cyl), "mpg"]))}
4. Write a function that simulates 1,000,000 powerball drawings. A powerball drawing takes a random sample of 5 numbers (without replacement) from 1 through 69, plus one powerball number ranging from 1 through 26. The function should return a single object recording all of your draws.
	* Powerball <- function(numDrawings){
draw <- matrix(nrow = numDrawings, ncol = 6)
for( i in 1:numDrawings){
draw[i, 1:5] <- sample(1:69, 5, replace = FALSE)
draw[i, 6] <- sample(1:26, 1, replace = FALSE)
}
return(draw)
}
5. Write a function that take a single set of lottery numbers (as a vector) as its argument. As before, write a function that simulates 1,000,000 powerball drawings. Have the function return a TRUE or FALSE value if you won any of the drawings.
	* Win <- function(lottonum){any(apply(Powerball(1000000), 1, sum) == sum(lottonum))}