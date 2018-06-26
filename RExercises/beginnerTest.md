## Beginner Test
1. What class of object is mtcars? What function did you use to find out?
	* data.frame, class()
2. Is precip defined as a 1-dimensional array or a vector? How did you find out?
	* vector, is(precip, "vector")
3. How would you convert the data.frame trees into a matrix?
	* as(trees, "matrix")
4. What is the name of the 14th city in the precip dataset?
	* Atlanta
5. What function would you use if you wanted to combine all three data sets into a single object?
	* SingleObject <- c(mtcars,precip,trees)
6. Does precip consist of numeric data? How did you find out?
	* yes, class(precip)
7. Code four different ways to subscript the 2nd row and 7th column of mtcars using bracket notation - i.e., 17.02.
	* mtcars[2,7]
	* mtcars["Mazda RX4 Wag", "qsec"]
	* mtcars[2, "qsec"]
	* mtcars["Mazda RX4 Wag", 7]
8. How would you change the precipitation values of "Juneau", "Phoenix", and "Sacramento" to 23, 46, and 12 in the precip dataset. (Hint: You will need to use subscripts and the <- operator).
	* precip[c(2,3,6)] <- c(23,46,12)
9. Are there any trees in the trees dataset with more girth than volume? How did you find out?
	* any(trees["Girth"] > trees["Volume"])
10. Take the sum of all elements in column height of the trees dataset, call this value A. Take the sum of all elements in row Valiant of the mtcars dataset, call this value B. Take the sum of the first 8 elements of the precip dataset, call this value C. Divide C by B and add A. What is your final answer?
	* A <- sum(trees["Height"])
	* B <- sum(mtcars["Valiant",])
	* C <- sum(precip[1:8])
	* (C/B)+A
	* 2356.628
	