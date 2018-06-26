## Intermediate Test
### Section 1
1. What does the REPLACE= argument of the sample( ) function do? You may want to look at the help page using ?sample.
	* Replace dictates whether the sample function take a value from the vector and throw it away (FALSE) which means the value won't appear in the new matrix after its initial appearance or take a value from the vector and place it within the vector again (TRUE) allowing it to be used within the new matrix again.
2. Usingas(MyMatrix,"numeric") will not convert MyMatrix to numeric data! Can you think of a property of logicals that you can use to convert the logicals to 0's and 1's other than the as( ) function?
	* R will convert TRUE to 1 and FALSE to 0 if you try to perform basic mathematical operations on an array of logical data
	* yourMatrix <- myMatrix * 1 
		* converts myMatrix logicals to 1s and 0s
3. If you wanted to check if all of the elements in each row are true, how would you do this?
	* apply(myMatrix, 1, all)
	* FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE

### Section 2
1. How many times does the number 7 occur in MyMatrix?
	* 16, length(which(myMatrix==7)) 
2. How do you find the sum of each column?
	* apply(myMatrix, 2, sum)
	* 51 37 45 58 47 54 51 46 53 42 59 42
3. How do you find the product of each column?
	* apply(myMatrix, 2, prod)
	* 290304 46656 123480 3402000 340200 1080000 1975680 79380 987840 134400 4838400 72000
4. How would you change every instance of the number 10 to 12?
	* myMatrix[which(myMatrix == 10)]<-12
5. How many values in MyMatrix are greater than 3 and less than 8?
	* 33, length(which(myMatrix > 3 & myMatrix < 8))
6. How do you change the elements of column 12 into character data, while keeping columns 1- 11 as numeric data??
	* myMatrix <- as.data.frame(myMatrix)
	* myMatrix[,12] <- as.character(myMatrix[,12])
7. Find which rows of MyMatrix have a sum >70. Make a new version of MyMatrix where the 13th column is a set of TRUE and FALSE values denoting which rows have a sum >70. (Hint: What type of object allows you to store both logical and numeric data at once?)
	* 2 5 6 7 8, which(apply(myMatrix,1,sum) > 70)
	* myMatrix <- data.frame(myMatrix, apply(myMatrix,1,sum)>70)
