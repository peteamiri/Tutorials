# R Langauge

* [R Project](https://www.r-project.org/)
* [R Manual](https://cran.r-project.org/manuals.html)
* [R FAQ](https://cran.r-project.org/doc/FAQ/R-FAQ.html)
* [R Docummentation](https://www.r-project.org/other-docs.html)
* [R Sources](https://cran.r-project.org/other-docs.html)
* [Other Sources](https://cran.r-project.org/)

* [Wiki](https://en.wikipedia.org/wiki/R_(programming_language))
* [Quick Tutorial](https://cran.r-project.org/doc/contrib/usingR.pdf)
* [R Resources](https://www.r-bloggers.com/how-to-learn-r-2/)

* [Starting R](http://www.rexamples.com/)

## Sample R Syntext
* [Source](https://www.datamentor.io/r-programming/examples/)

Sample Print statement

```
# We can use the print() function
print("Hello World!")

# Quotes can be suppressed in the output
print("Hello World!", quote = FALSE)

# If there are more than 1 item, we can concatenate using paste()
print(paste("How","are","you?"))

```
Since, a vector must have elements of the same type, this function will try and coerce elements to the same type, if they are different.

Coercion is from lower to higher types from logical to integer to double to character.

```
# Assign value to Vector X
x <- c(1, 5, 4, 9, 0)

# Check the Variable type
typeof(x)

# Check the lenght of the variable
length(x)

# Print the value ssigned to the varaible
print(x)

```

Creating a vector using : operator
```
x <- 1:7; x
y <- 2:-2; y
```

Creating a vector using seq() function

```
seq(1, 3, by=0.2)          # specify step size
# [1] 1.0 1.2 1.4 1.6 1.8 2.0 2.2 2.4 2.6 2.8 3.0
seq(1, 5, length.out=4)    # specify length of the vector
# [1] 1.000000 2.333333 3.666667 5.000000
```

### How to access Elements of a Vector?
Elements of a vector can be accessed using vector indexing. The vector used for indexing can be logical, integer or character vector.

Using integer vector as index
Vector index in R starts from 1, unlike most programming languages where index start from 0.

We can use a vector of integers as index to access specific elements.

We can also use negative integers to return all elements except that those specified.

But we cannot mix positive and negative integers while indexing and real numbers, if used, are truncated to integers.

```
x
# [1]  0  2  4  6  8 10
x[3]           # access 3rd element
# [1] 4
x[c(2, 4)]     # access 2nd and 4th element
# [1] 2 6
x[-1]          # access all but 1st element
# [1]  2  4  6  8 10
x[c(2, -4)]    # cannot mix positive and negative integers
# Error in x[c(2, -4)] : only 0's may be mixed with negative subscripts
x[c(2.4, 3.54)]    # real numbers are truncated to integers
# [1] 2 4
```

### Using logical vector as index
When we use a logical vector for indexing, the position where the logical vector is TRUE is returned.

This useful feature helps us in filtering of vector as shown below.

```
x[c(TRUE, FALSE, FALSE, TRUE)]
# [1] -3  3
x[x < 0]  # filtering vectors based on conditions
# [1] -3 -1
x[x > 0]
# [1] 3
```

In the above example, the expression x>0 will yield a logical vector (FALSE, FALSE, FALSE, TRUE) which is then used for indexing.

Using character vector as index
This type of indexing is useful when dealing with named vectors. We can name each elements of a vector.

```
x <- c("first"=3, "second"=0, "third"=9)
names(x)
# [1] "first"  "second" "third"
x["second"]
# second
# 0
x[c("first", "third")]
# first third
# 3     9
```

### How to modify a vector in R?
We can modify a vector using the assignment operator.

We can use the techniques discussed above to access specific elements and modify them.

If we want to truncate the elements, we can use reassignments.

> x
[1] -3 -2 -1  0  1  2
> x[2] <- 0; x        # modify 2nd element
[1] -3  0 -1  0  1  2
> x[x<0] <- 5; x   # modify elements less than 0
[1] 5 0 5 0 1 2
> x <- x[1:4]; x      # truncate x to first 4 elements
[1] 5 0 5 0
How to delete a Vector?
We can delete a vector by simply assigning a NULL to it.

> x
[1] -3 -2 -1  0  1  2
> x <- NULL
> x
NULL
> x[4]
NULL

R Matrix
In this article, you will learn to work with matrix in R. You will learn to create and modify matrix, and access matrix elements.

Matrix is a two dimensional data structure in R programming.

Matrix is similar to vector but additionally contains the dimension attribute. All attributes of an object can be checked with the attributes() function (dimension can be checked directly with the dim() function).

We can check if a variable is a matrix or not with the class() function.

> a
[,1] [,2] [,3]
[1,]    1    4    7
[2,]    2    5    8
[3,]    3    6    9
> class(a)
[1] "matrix"
> attributes(a)
$dim
[1] 3 3
> dim(a)
[1] 3 3
How to create a matrix in R programming?
Matrix can be created using the matrix() function.

Dimension of the matrix can be defined by passing appropriate value for arguments nrow and ncol.

Providing value for both dimension is not necessary. If one of the dimension is provided, the other is inferred from length of the data.

> matrix(1:9, nrow = 3, ncol = 3)
[,1] [,2] [,3]
[1,]    1    4    7
[2,]    2    5    8
[3,]    3    6    9
> # same result is obtained by providing only one dimension
> matrix(1:9, nrow = 3)
[,1] [,2] [,3]
[1,]    1    4    7
[2,]    2    5    8
[3,]    3    6    9
We can see that the matrix is filled column-wise. This can be reversed to row-wise filling by passing TRUE to the argument byrow.

> matrix(1:9, nrow=3, byrow=TRUE)    # fill matrix row-wise
[,1] [,2] [,3]
[1,]    1    2    3
[2,]    4    5    6
[3,]    7    8    9
In all cases, however, a matrix is stored in column-major order internally as we will see in the subsequent sections.

It is possible to name the rows and columns of matrix during creation by passing a 2 element list to the argument dimnames.

> x <- matrix(1:9, nrow = 3, dimnames = list(c("X","Y","Z"), c("A","B","C")))
> x
A B C
X 1 4 7
Y 2 5 8
Z 3 6 9
These names can be accessed or changed with two helpful functions colnames() and rownames().

> colnames(x)
[1] "A" "B" "C"
> rownames(x)
[1] "X" "Y" "Z"
> # It is also possible to change names
> colnames(x) <- c("C1","C2","C3")
> rownames(x) <- c("R1","R2","R3")
> x
C1 C2 C3
R1  1  4  7
R2  2  5  8
R3  3  6  9
Another way of creating a matrix is by using functions cbind() and rbind() as in column bind and row bind.

> cbind(c(1,2,3),c(4,5,6))
[,1] [,2]
[1,]    1    4
[2,]    2    5
[3,]    3    6
> rbind(c(1,2,3),c(4,5,6))
[,1] [,2] [,3]
[1,]    1    2    3
[2,]    4    5    6
Finally, you can also create a matrix from a vector by setting its dimension using dim().

> x <- c(1,2,3,4,5,6)
> x
[1] 1 2 3 4 5 6
> class(x)
[1] "numeric"
> dim(x) <- c(2,3)
> x
[,1] [,2] [,3]
[1,]    1    3    5
[2,]    2    4    6
> class(x)
[1] "matrix"
How to access Elements of a matrix?
We can access elements of a matrix using the square bracket [ indexing method. Elements can be accessed as var[row, column]. Here rows and columns are vectors.

Using integer vector as index
We specify the row numbers and column numbers as vectors and use it for indexing.

If any field inside the bracket is left blank, it selects all.

We can use negative integers to specify rows or columns to be excluded.

> x
[,1] [,2] [,3]
[1,]    1    4    7
[2,]    2    5    8
[3,]    3    6    9
> x[c(1,2),c(2,3)]    # select rows 1 & 2 and columns 2 & 3
[,1] [,2]
[1,]    4    7
[2,]    5    8
> x[c(3,2),]    # leaving column field blank will select entire columns
[,1] [,2] [,3]
[1,]    3    6    9
[2,]    2    5    8
> x[,]    # leaving row as well as column field blank will select entire matrix
[,1] [,2] [,3]
[1,]    1    4    7
[2,]    2    5    8
[3,]    3    6    9
> x[-1,]    # select all rows except first
[,1] [,2] [,3]
[1,]    2    5    8
[2,]    3    6    9
One thing to notice here is that, if the matrix returned after indexing is a row matrix or column matrix, the result is given as a vector.

> x[1,]
[1] 1 4 7
> class(x[1,])
[1] "integer"
This behavior can be avoided by using the argument drop = FALSE while indexing.

> x[1,,drop=FALSE]  # now the result is a 1X3 matrix rather than a vector
[,1] [,2] [,3]
[1,]    1    4    7
> class(x[1,,drop=FALSE])
[1] "matrix"
It is possible to index a matrix with a single vector.

While indexing in such a way, it acts like a vector formed by stacking columns of the matrix one after another. The result is returned as a vector.

> x
[,1] [,2] [,3]
[1,]    4    8    3
[2,]    6    0    7
[3,]    1    2    9
> x[1:4]
[1] 4 6 1 8
> x[c(3,5,7)]
[1] 1 0 3
Using logical vector as index
Two logical vectors can be used to index a matrix. In such situation, rows and columns where the value is TRUE is returned. These indexing vectors are recycled if necessary and can be mixed with integer vectors.

> x
[,1] [,2] [,3]
[1,]    4    8    3
[2,]    6    0    7
[3,]    1    2    9
> x[c(TRUE,FALSE,TRUE),c(TRUE,TRUE,FALSE)]
[,1] [,2]
[1,]    4    8
[2,]    1    2
> x[c(TRUE,FALSE),c(2,3)]    # the 2 element logical vector is recycled to 3 element vector
[,1] [,2]
[1,]    8    3
[2,]    2    9
It is also possible to index using a single logical vector where recycling takes place if necessary.

> x[c(TRUE, FALSE)]
[1] 4 1 0 3 9
In the above example, the matrix x is treated as vector formed by stacking columns of the matrix one after another, i.e., (4,6,1,8,0,2,3,7,9).

The indexing logical vector is also recycled and thus alternating elements are selected. This property is utilized for filtering of matrix elements as shown below.

> x[x>5]    # select elements greater than 5
[1] 6 8 7 9
> x[x%%2 == 0]    # select even elements
[1] 4 6 8 0 2
Using character vector as index
Indexing with character vector is possible for matrix with named row or column. This can be mixed with integer or logical indexing.

> x
A B C
[1,] 4 8 3
[2,] 6 0 7
[3,] 1 2 9
> x[,"A"]
[1] 4 6 1
> x[TRUE,c("A","C")]
A C
[1,] 4 3
[2,] 6 7
[3,] 1 9
> x[2:3,c("A","C")]
A C
[1,] 6 7
[2,] 1 9
How to modify a matrix in R?
We can combine assignment operator with the above learned methods for accessing elements of a matrix to modify it.

> x
[,1] [,2] [,3]
[1,]    1    4    7
[2,]    2    5    8
[3,]    3    6    9
> x[2,2] <- 10; x    # modify a single element
[,1] [,2] [,3]
[1,]    1    4    7
[2,]    2   10    8
[3,]    3    6    9
> x[x<5] <- 0; x    # modify elements less than 5
[,1] [,2] [,3]
[1,]    0    0    7
[2,]    0   10    8
[3,]    0    6    9
A common operation with matrix is to transpose it. This can be done with the function t().

> t(x)    # transpose a matrix
[,1] [,2] [,3]
[1,]    0    0    0
[2,]    0   10    6
[3,]    7    8    9
We can add row or column using rbind() and cbind() function respectively. Similarly, it can be removed through reassignment.

> cbind(x, c(1, 2, 3))    # add column
[,1] [,2] [,3] [,4]
[1,]    0    0    7    1
[2,]    0   10    8    2
[3,]    0    6    9    3
> rbind(x,c(1,2,3))    # add row
[,1] [,2] [,3]
[1,]    0    0    7
[2,]    0   10    8
[3,]    0    6    9
[4,]    1    2    3
> x <- x[1:2,]; x    # remove last row
[,1] [,2] [,3]
[1,]    0    0    7
[2,]    0   10    8
Dimension of matrix can be modified as well, using the dim() function.

> x
[,1] [,2] [,3]
[1,]    1    3    5
[2,]    2    4    6
> dim(x) <- c(3,2); x    # change to 3X2 matrix
[,1] [,2]
[1,]    1    4
[2,]    2    5
[3,]    3    6
> dim(x) <- c(1,6); x    # change to 1X6 matrix
[,1] [,2] [,3] [,4] [,5] [,6]
[1,]    1    2    3    4    5    6

R Lists
In this article, you will learn to work with lists in R programming. You will learn to create, access, modify and delete list components.

List is a data structure having components of mixed data types.

A vector having all elements of the same type is called atomic vector but a vector having elements of different type is called list.

We can check if it’s a list with typeof() function and find its length using length(). Here is an example of a list having three components each of different data type.

> x
$a
[1] 2.5
$b
[1] TRUE
$c
[1] 1 2 3
> typeof(x)
[1] "list"
> length(x)
[1] 3
How to create a list in R programming?
List can be created using the list() function.

> x <- list("a" = 2.5, "b" = TRUE, "c" = 1:3)
Here, we create a list x, of three components with data types double, logical and integer vector respectively.

Its structure can be examined with the str() function.

> str(x)
List of 3
$ a: num 2.5
$ b: logi TRUE
$ c: int [1:3] 1 2 3
In this example, a, b and c are called tags which makes it easier to reference the components of the list.

However, tags are optional. We can create the same list without the tags as follows. In such scenario, numeric indices are used by default.

> x <- list(2.5,TRUE,1:3)
> x
[[1]]
[1] 2.5
[[2]]
[1] TRUE
[[3]]
[1] 1 2 3
How to access components of a list?
Lists can be accessed in similar fashion to vectors. Integer, logical or character vectors can be used for indexing. Let us consider a list as follows.

> x
$name
[1] "John"
$age
[1] 19
$speaks
[1] "English" "French"
> x[c(1:2)]    # index using integer vector
$name
[1] "John"
$age
[1] 19
> x[-2]        # using negative integer to exclude second component
$name
[1] "John"
$speaks
[1] "English" "French"
> x[c(T,F,F)]  # index using logical vector
$name
[1] "John"
> x[c("age","speaks")]    # index using character vector
$age
[1] 19
$speaks
[1] "English" "French"
Indexing with [ as shown above will give us sublist not the content inside the component. To retrieve the content, we need to use [[.

However, this approach will allow us to access only a single component at a time.

> x["age"]
$age
[1] 19
> typeof(x["age"])    # single [ returns a list
[1] "list"
> x[["age"]]    # double [[ returns the content
[1] 19
> typeof(x[["age"]])
[1] "double"
An alternative to [[, which is used often while accessing content of a list is the $ operator. They are both the same except that $ can do partial matching on tags.

> x$name    # same as x[["name"]]
[1] "John"
> x$a                  # partial matching, same as x$ag or x$age
[1] 19
> x[["a"]]             # cannot do partial match with [[
NULL
> # indexing can be done recursively
> x$speaks[1]
[1] "English"
> x[["speaks"]][2]
[1] "French"
How to modify a list in R?
We can change components of a list through reassignment. We can choose any of the component accessing techniques discussed above to modify it.

Notice below that modification causes reordering of components.

> x[["name"]] <- "Clair"; x
$age
[1] 19
$speaks
[1] "English" "French"
$name
[1] "Clair"
How to add components to a list?
Adding new components is easy. We simply assign values using new tags and it will pop into action.

> x[["married"]] <- FALSE
> x
$age
[1] 19
$speaks
[1] "English" "French"
$name
[1] "Clair"
$married
[1] FALSE
How to delete components from a list?
We can delete a component by assigning NULL to it.

> x[["age"]] <- NULL
> str(x)
List of 3
$ speaks : chr [1:2] "English" "French"
$ name   : chr "Clair"
$ married: logi FALSE
> x$married <- NULL
> str(x)
List of 2
$ speaks: chr [1:2] "English" "French"
$ name  : chr "Clair"

R Data Frame
In this article, you’ll learn about data frames in R; how to create them, access their elements and modify them in your program.

Data frame is a two dimensional data structure in R. It is a special case of a list which has each component of equal length.

Each component form the column and contents of the component form the rows.

Check if a variable is a data frame or not
We can check if a variable is a data frame or not using the class() function.

> x
SN Age Name
1  1  21 John
2  2  15 Dora
> typeof(x)    # data frame is a special case of  list
[1] "list"
> class(x)
[1] "data.frame"
In this example, x can be considered as a list of 3 components with each component having a two element vector. Some useful functions to know more about a data frame are given below.

Functions of data frame
> names(x)
[1] "SN"   "Age"  "Name"
> ncol(x)
[1] 3
> nrow(x)
[1] 2
> length(x)    # returns length of the list, same as ncol()
[1] 3
How to create a Data Frame in R?
We can create a data frame using the data.frame() function.

For example, the above shown data frame can be created as follows.

> x <- data.frame("SN" = 1:2, "Age" = c(21,15), "Name" = c("John","Dora"))
> str(x)    # structure of x
'data.frame':   2 obs. of  3 variables:
$ SN  : int  1 2
$ Age : num  21 15
$ Name: Factor w/ 2 levels "Dora","John": 2 1
Notice above that the third column, Name is of type factor, instead of a character vector.

By default, data.frame() function converts character vector into factor.

To suppress this behavior, we can pass the argument stringsAsFactors=FALSE.

> x <- data.frame("SN" = 1:2, "Age" = c(21,15), "Name" = c("John", "Dora"), stringsAsFactors = FALSE)
> str(x)    # now the third column is a character vector
'data.frame':   2 obs. of  3 variables:
$ SN  : int  1 2
$ Age : num  21 15
$ Name: chr  "John" "Dora"
Many data input functions of R like, read.table(), read.csv(), read.delim(), read.fwf() also read data into a data frame.

How to access Components of a Data Frame?
Components of data frame can be accessed like a list or like a matrix.

Accessing like a list
We can use either [, [[ or $ operator to access columns of data frame.

> x["Name"]
Name
1 John
2 Dora
> x$Name
[1] "John" "Dora"
> x[["Name"]]
[1] "John" "Dora"
> x[[3]]
[1] "John" "Dora"
Accessing with [[ or $ is similar. However, it differs for [ in that, indexing with [ will return us a data frame but the other two will reduce it into a vector.

Accessing like a matrix
Data frames can be accessed like a matrix by providing index for row and column.

To illustrate this, we use datasets already available in R. Datasets that are available can be listed with the command library(help = "datasets").

We will use the trees dataset which contains Girth, Height and Volume for Black Cherry Trees.

A data frame can be examined using functions like str() and head().

> str(trees)
'data.frame':   31 obs. of 3 variables:
$ Girth : num  8.3 8.6 8.8 10.5 10.7 10.8 11 11 11.1 11.2 ...
$ Height: num  70 65 63 72 81 83 66 75 80 75 ...
$ Volume: num  10.3 10.3 10.2 16.4 18.8 19.7 15.6 18.2 22.6 19.9 ...
> head(trees,n=3)
Girth Height Volume
1   8.3     70   10.3
2   8.6     65   10.3
3   8.8     63   10.2
We can see that trees is a data frame with 31 rows and 3 columns. We also display the first 3 rows of the data frame.

Now we proceed to access the data frame like a matrix.

> trees[2:3,]    # select 2nd and 3rd row
Girth Height Volume
2   8.6     65   10.3
3   8.8     63   10.2
> trees[trees$Height > 82,]    # selects rows with Height greater than 82
Girth Height Volume
6   10.8     83   19.7
17  12.9     85   33.8
18  13.3     86   27.4
31  20.6     87   77.0
> trees[10:12,2]
[1] 75 79 76
We can see in the last case that the returned type is a vector since we extracted data from a single column.

This behavior can be avoided by passing the argument drop=FALSE as follows.

> trees[10:12,2, drop = FALSE]
Height
10     75
11     79
12     76
How to modify a Data Frame in R?
Data frames can be modified like we modified matrices through reassignment.

> x
SN Age Name
1  1  21 John
2  2  15 Dora
> x[1,"Age"] <- 20; x
SN Age Name
1  1  20 John
2  2  15 Dora
Adding Components
Rows can be added to a data frame using the rbind() function.

> rbind(x,list(1,16,"Paul"))
SN Age Name
1  1  20 John
2  2  15 Dora
3  1  16 Paul
Similarly, we can add columns using cbind().

> cbind(x,State=c("NY","FL"))
SN Age Name State
1  1  20 John    NY
2  2  15 Dora    FL
Since data frames are implemented as list, we can also add new columns through simple list-like assignments.

> x
SN Age Name
1  1  20 John
2  2  15 Dora
> x$State <- c("NY","FL"); x
SN Age Name State
1  1  20 John    NY
2  2  15 Dora    FL
Deleting Component
Data frame columns can be deleted by assigning NULL to it.

> x$State <- NULL
> x
SN Age Name
1  1  20 John
2  2  15 Dora
Similarly, rows can be deleted through reassignments.

> x <- x[-1,]
> x
SN Age Name
2  2  15 Dora


> x
[1] single  married married single
Levels: single married divorced
> x[2] <- "divorced"    # modify second element;  x
[1] single   divorced married  single
Levels: single married divorced
> x[3] <- "widowed"    # cannot assign values outside levels
Warning message:
In `[<-.factor`(`*tmp*`, 3, value = "widowed") :
invalid factor level, NA generated
> x
[1] single   divorced <NA>     single
Levels: single married divorced
A workaround to this is to add the value to the level first.

> levels(x) <- c(levels(x), "widowed")    # add new level
> x[3] <- "widowed"
> x
[1] single   divorced widowed  single
Levels: single married divorced widowed

R Classes and Objects
R has 3 classes. In this article, you’ll be introduced to all three classes (S3, S4 and reference class) in R programming.

We can do object oriented programming in R. In fact, everything in R is an object.

An object is a data structure having some attributes and methods which act on its attributes.

Class is a blueprint for the object. We can think of class like a sketch (prototype) of a house. It contains all the details about the floors, doors, windows etc. Based on these descriptions we build the house.

House is the object. As, many houses can be made from a description, we can create many objects from a class. An object is also called an instance of a class and the process of creating this object is called instantiation.

While most programming languages have a single class system, R has three class systems. Namely, S3, S4 and more recently Reference class systems.

They have their own features and peculiarities and choosing one over the other is a matter of preference. Below, we give a brief introduction to them.

S3 Class
S3 class is somewhat primitive in nature. It lacks a formal definition and object of this class can be created simply by adding a class attribute to it.

This simplicity accounts for the fact that it is widely used in R programming language. In fact most of the R built-in classes are of this type.

See R programming S3 Class section for further details.

Example 1: S3 class
> # create a list with required components
> s <- list(name = "John", age = 21, GPA = 3.5)
> # name the class appropriately
> class(s) <- "student"
Above example creates a S3 class with the given list.

S4 Class
S4 class are an improvement over the S3 class. They have a formally defined structure which helps in making object of the same class look more or less similar.

Class components are properly defined using the setClass() function and objects are created using the new() function.

See R programming S4 Class section for further details.

Example 2: S4 class
< setClass("student", slots=list(name="character", age="numeric", GPA="numeric"))
Reference Class
Reference class were introduced later, compared to the other two. It is more similar to the object oriented programming we are used to seeing in other major programming languages.

Reference classes are basically S4 classed with an environment added to it.

See R programming Reference Class section for further details.

Example 3: Reference class
< setRefClass("student")
Comparision between S3 vs S4 vs Reference Class
S3 Class	S4 Class	Referene Class
Lacks formal definition	Class defined using setClass()	Class defined using setRefClass()
Objects are created by setting the class attribute	Objects are created using new()	Objects are created using generator functions
Attributes are accessed using $	Attributes are accessed using @	Attributes are accessed using $
Methods belong to generic function	Methods belong to generic function	Methods belong to the class
Follows copy-on-modify semantics	Follows copy-on-modify semantics	Does not follow copy-on-modify semantics

R S3 Class
In this article, you will learn to work with S3 classes (one of the three class systems in R programming).

S3 class is the most popular and prevalent class in R programming language.

Most of the classes that come predefined in R are of this type. The fact that it is simple and easy to implement is the reason behind this.

How to define S3 class and create S3 objects?
S3 class has no formal, predefined definition.

Basically, a list with its class attribute set to some class name, is an S3 object. The components of the list become the member variables of the object.

Following is a simple example of how an S3 object of class student can be created.

> # create a list with required components
> s <- list(name = "John", age = 21, GPA = 3.5)
> # name the class appropriately
> class(s) <- "student"
> # That's it! we now have an object of class "student"
> s
$name
[1] "John"
$age
[1] 21
$GPA
[1] 3.5
attr(,"class")
[1] "student"
This might look awkward for programmers coming from C++, Python etc. where there are formal class definitions and objects have properly defined attributes and methods.

In R S3 system, it's pretty ad hoc. You can convert an object's class according to your will with objects of the same class looking completely different. It's all up to you.

How to use constructors to create objects?
It is a good practice to use a function with the same name as class (not a necessity) to create objects.

This will bring some uniformity in the creation of objects and make them look similar.

We can also add some integrity check on the member attributes. Here is an example. Note that in this example we use the attr() function to set the class attribute of the object.

# a constructor function for the "student" class
student <- function(n,a,g) {
# we can add our own integrity checks
if(g>4 || g<0)  stop("GPA must be between 0 and 4")
value <- list(name = n, age = a, GPA = g)
# class can be set using class() or attr() function
attr(value, "class") <- "student"
value
}
Here is a sample run where we create objects using this constructor.

> s <- student("Paul", 26, 3.7)
> s
$name
[1] "Paul"
$age
[1] 26
$GPA
[1] 3.7
attr(,"class")
[1] "student"
> class(s)
[1] "student"
> s <- student("Paul", 26, 5)
Error in student("Paul", 26, 5) : GPA must be between 0 and 4
> # these integrity check only work while creating the object using constructor
> s <- student("Paul", 26, 2.5)
> # it's up to us to maintain it or not
> s$GPA <- 5
Methods and Generic Functions
In the above example, when we simply write the name of the object, its internals get printed.

In interactive mode, writing the name alone will print it using the print() function.

> s
$name
[1] "Paul"
$age
[1] 26
$GPA
[1] 3.7
attr(,"class")
[1] "student"
Furthermore, we can use print() with vectors, matrix, data frames, factors etc. and they get printed differently according to the class they belong to.

How does print() know how to print these variety of dissimilar looking object?

The answer is, print() is a generic function. Actually, it has a collection of a number of methods. You can check all these methods with methods(print).

> methods(print)
[1] print.acf*
[2] print.anova*
...
[181] print.xngettext*
[182] print.xtabs*
Non-visible functions are asterisked
We can see methods like print.data.frame and print.factor in the above list.

When we call print() on a data frame, it is dispatched to print.data.frame().

If we had done the same with a factor, the call would dispatch to print.factor(). Here, we can observe that the method names are in the form generic_name.class_name(). This is how R is able to figure out which method to call depending on the class.

Printing our object of class "student" looks for a method of the form print.student(), but there is no method of this form.

So, which method did our object of class "student" call?

It called print.default(). This is the fallback method which is called if no other match is found. Generic functions have a default method.

There are plenty of generic functions like print(). You can list them all with methods(class="default").

> methods(class="default")
[1] add1.default*            aggregate.default*
[3] AIC.default*             all.equal.default
...
How to write your own method?
Now let us implement a method print.student() ourself.

print.student <- function(obj) {
cat(obj$name, "\n")
cat(obj$age, "years old\n")
cat("GPA:", obj$GPA, "\n")
}
Now this method will be called whenever we print() an object of class "student".

In S3 system, methods do not belong to object or class, they belong to generic functions. This will work as long as the class of the object is set.

> # our above implemented method is called
> s
Paul
26 years old
GPA: 3.7
> # removing the class attribute will restore as previous
> unclass(s)
$name
[1] "Paul"
$age
[1] 26
$GPA
[1] 3.7
Writing Your Own Generic Function
It is possible to make our own generic function like print() or plot(). Let us first look at how these functions are implemented.

> print
function (x, ...)
UseMethod("print")
<bytecode: 0x0674e230>
<environment: namespace:base>
> plot
function (x, y, ...)
UseMethod("plot")
<bytecode: 0x04fe6574>
<environment: namespace:graphics>
We can see that they have a single call to UseMethod() with the name of the generic function passed to it. This is the dispatcher function which will handle all the background details. It is this simple to implement a generic function.

For the sake of example, we make a new generic function called grade.

grade <- function(obj) {
UseMethod("grade")
}
A generic function is useless without any method. Let us implement the default method.

grade.default <- function(obj) {
cat("This is a generic function\n")
}
Now let us make method for our class "student".

grade.student <- function(obj) {
cat("Your grade is", obj$GPA, "\n")
}
A sample run.

> grade(s)
Your grade is 3.7
In this way, we implemented a generic function called grade and later a method for our class.

R S4 Class
In this article, you’ll learn everything about S4 classes in R; how to define them, create them, access their slots, and use them efficiently in your program.


Unlike S3 classes and objects which lacks formal definition, we look at S4 class which is stricter in the sense that it has a formal definition and a uniform way to create objects.
This adds safety to our code and prevents us from accidentally making naive mistakes.

How to define S4 Class?
S4 class is defined using the setClass() function.

In R terminology, member variables are called slots. While defining a class, we need to set the name and the slots (along with class of the slot) it is going to have.

Example 1: Definition of S4 class
setClass("student", slots=list(name="character", age="numeric", GPA="numeric"))
In the above example, we defined a new class called student along with three slots it’s going to have name, age and GPA.

There are other optional arguments of setClass() which you can explore in the help section with ?setClass.

How to create S4 objects?
S4 objects are created using the new() function.

Example 2: Creation of S4 object
> # create an object using new()
> # provide the class name and value for slots
> s <- new("student",name="John", age=21, GPA=3.5)
> s
An object of class "student"
Slot "name":
[1] "John"
Slot "age":
[1] 21
Slot "GPA":
[1] 3.5
We can check if an object is an S4 object through the function isS4().

> isS4(s)
[1] TRUE
The function setClass() returns a generator function.

This generator function (usually having same name as the class) can be used to create new objects. It acts as a constructor.

> student <- setClass("student", slots=list(name="character", age="numeric", GPA="numeric"))
> student
class generator function for class “student” from package ‘.GlobalEnv’
function (...)
new("student", ...)
Now we can use this constructor function to create new objects.

Note above that our constructor in turn uses the new() function to create objects. It is just a wrap around.

Example 3: Creation of S4 objects using generator function
> student(name="John", age=21, GPA=3.5)
An object of class "student"
Slot "name":
[1] "John"
Slot "age":
[1] 21
Slot "GPA":
[1] 3.5
How to access and modify slot?
Just as components of a list are accessed using $, slot of an object are accessed using @.

Accessing slot
> s@name
[1] "John"
> s@GPA
[1] 3.5
> s@age
[1] 21
Modifying slot directly
A slot can be modified through reassignment.

> # modify GPA
> s@GPA <- 3.7
> s
An object of class "student"
Slot "name":
[1] "John"
Slot "age":
[1] 21
Slot "GPA":
[1] 3.7
Modifying slots using slot() function
Similarly, slots can be access or modified using the slot() function.

> slot(s,"name")
[1] "John"
> slot(s,"name") <- "Paul"
> s
An object of class "student"
Slot "name":
[1] "Paul"
Slot "age":
[1] 21
Slot "GPA":
[1] 3.7
Methods and Generic Functions
As in the case of S3 class, methods for S4 class also belong to generic functions rather than the class itself. Working with S4 generics is pretty much similar to S3 generics.

You can list all the S4 generic functions and methods available, using the function showMethods().

Example 4: List all generic functions
> showMethods()
Function: - (package base)
Function: != (package base)
...
Function: trigamma (package base)
Function: trunc (package base)
Writing the name of the object in interactive mode prints it. This is done using the S4 generic function show().

You can see this function in the above list. This function is the S4 analogy of the S3 print() function.

Example 5: Check if a function is a generic function
> isS4(print)
[1] FALSE
> isS4(show)
[1] TRUE
We can list all the methods of show generic function using showMethods(show).

Example 6: List all methods of a generic function
> showMethods(show)
Function: show (package methods)
object="ANY"
object="classGeneratorFunction"
...
object="standardGeneric"
(inherited from: object="genericFunction")
object="traceable"
How to write your own method?
We can write our own method using setMethod() helper function.

For example, we can implement our class method for the show() generic as follows.

setMethod("show",
"student",
function(object) {
cat(object@name, "\n")
cat(object@age, "years old\n")
cat("GPA:", object@GPA, "\n")
}
)
Now, if we write out the name of the object in interactive mode as before, the above code is executed.

> s <- new("student",name="John", age=21, GPA=3.5)
> s    # this is same as show(s)
John
21 years old
GPA: 3.5
In this way we can write our own S4 class methods for generic functions.


Field "age":
[1] 21
Field "GPA":
[1] 3.5
Reference Methods
Methods are defined for a reference class and do not belong to generic functions as in S3 and S4 classes.

All reference class have some methods predefined because they all are inherited from the superclass envRefClass.

> student
Generator for class "student":
Class fields:
Name:       name       age       GPA
Class: character   numeric   numeric
Class Methods:
"callSuper", "copy", "export", "field", "getClass", "getRefClass",
"import", "initFields", "show", "trace", "untrace", "usingMethods"
Reference Superclasses:
"envRefClass"
We can see class methods like copy(), field() and show() in the above list. We can create our own methods for the class.

This can be done during the class definition by passing a list of function definitions to methods argument of setRefClass().

student <- setRefClass("student",
fields = list(name = "character", age = "numeric", GPA = "numeric"),
methods = list(
inc_age = function(x) {
age <<- age + x
},
dec_age = function(x) {
age <<- age - x
}
)
)
In the above section of our code, we defined two methods called inc_age() and dec_age(). These two method modify the field age.

Note that we have to use the non-local assignment operator <<- since age isn’t in the method’s local environment. This is important.

Using the simple assignment operator <- would have created a local variable called age, which is not what we want. R will issue a warning in such case.

Here is a sample run where we use the above defined methods.

> s <- student(name = "John", age = 21, GPA = 3.5)
> s$inc_age(5)
> s$age
[1] 26
> s$dec_age(10)
> s$age
[1] 16

R Inheritance
In this article, you’ll learn everything about inheritance in R. More specifically, how to create inheritance in S3, S4 and Reference classes, and use them efficiently in your program.


Inheritance is one of the key features of object-oriented programming which allows us to define a new class out of existing classes.
This is to say, we can derive new classes from existing base classes and adding new features. We don’t have to write from scratch. Hence, inheritance provides reusability of code.

Inheritance forms a hierarchy of class just like a family tree. Important thing to note is that the attributes define for a base class will automatically be present in the derived class.

Moreover, the methods for the base class will work for the derived.

Inheritance in R Programming

Below, we discuss how inheritance is carried out for the three different class systems in R programming language.

Inheritance in S3 Class
S3 classes do not have any fixed definition. Hence attributes of S3 objects can be arbitrary.

Derived class, however, inherit the methods defined for base class. Let us suppose we have a function that creates new objects of class student as follows.

student <- function(n,a,g) {
value <- list(name=n, age=a, GPA=g)
attr(value, "class") <- "student"
value
}
Furthermore, we have a method defined for generic function print() as follows.

print.student <- function(obj) {
cat(obj$name, "\n")
cat(obj$age, "years old\n")
cat("GPA:", obj$GPA, "\n")
}
Now we want to create an object of class InternationalStudent which inherits from student.

This is be done by assigning a character vector of class names like class(obj) <- c(child, parent).

> # create a list
> s <- list(name="John", age=21, GPA=3.5, country="France")
> # make it of the class InternationalStudent which is derived from the class student
> class(s) <- c("InternationalStudent","student")
> # print it out
> s
John
21 years old
GPA: 3.5
We can see above that, since we haven’t defined any method of the form print.InternationalStudent(), the method print.student() got called. This method of class student was inherited.

Now let us define print.InternationalStudent().

print.InternationalStudent <- function(obj) {
cat(obj$name, "is from", obj$country, "\n")
}
This will overwrite the method defined for class student as shown below.

> s
John is from France
We can check for inheritance with functions like inherits() or is().

> inherits(s,"student")
[1] TRUE
> is(s,"student")
[1] TRUE
Inheritance in S4 Class
Since S4 classes have proper definition, derived classes will inherit both attributes and methods of the parent class.

Let us define a class student with a method for the generic function show().

# define a class called student
setClass("student",
slots=list(name="character", age="numeric", GPA="numeric")
)
# define class method for the show() generic function
setMethod("show",
"student",
function(object) {
cat(object@name, "\n")
cat(object@age, "years old\n")
cat("GPA:", object@GPA, "\n")
}
)
Inheritance is done during the derived class definition with the argument contains as shown below.

# inherit from student
setClass("InternationalStudent",
slots=list(country="character"),
contains="student"
)
Here we have added an attribute country, rest will be inherited from the parent.

> s <- new("InternationalStudent",name="John", age=21, GPA=3.5, country="France")
> show(s)
John
21 years old
GPA: 3.5
We see that method define for class student got called when we did show(s).

We can define methods for the derived class which will overwrite methods of the base class, like in the case of S3 systems.

Inheritance in Reference Class
Inheritance in reference class is very much similar to that of the S4 class. We define in the contains argument, from which base class to derive from.

Here is an example of student reference class with two methods inc_age() and dec_age().

student <- setRefClass("student",
fields=list(name="character", age="numeric", GPA="numeric"),
methods=list(
inc_age = function(x) {
age <<- age + x
},
dec_age = function(x) {
age <<- age - x
}
)
)
Now we will inherit from this class. We also overwrite dec_age() method to add an integrity check to make sure age is never negative.

InternationalStudent <- setRefClass("InternationalStudent",
fields=list(country="character"),
contains="student",
methods=list(
dec_age = function(x) {
if((age - x)<0)  stop("Age cannot be negative")
age <<- age - x
}
)
)
Let us put it to test.

> s <- InternationalStudent(name="John", age=21, GPA=3.5, country="France")
> s$dec_age(5)
> s$age
[1] 16
> s$dec_age(20)
Error in s$dec_age(20) : Age cannot be negative
> s$age
[1] 16
In this way, we are able to inherit from the parent class.








```
for(i in 1:5) print(1:i)
for(n in c(2,5,10,20,50)) {
   x <- stats::rnorm(n)
   cat(n, ": ", sum(x^2), "\n", sep = "")
}
f <- factor(sample(letters[1:5], 10, replace = TRUE))
for(i in unique(f)) print(i)
```


Example two

```
x <- c(6:-4)
sqrt(x)  #- gives warning
sqrt(ifelse(x >= 0, x, NA))  # no warning

## Note: the following also gives the warning !
ifelse(x >= 0, sqrt(x), NA)


## ifelse() strips attributes
## This is important when working with Dates and factors
x <- seq(as.Date("2000-02-29"), as.Date("2004-10-04"), by = "1 month")
## has many "yyyy-mm-29", but a few "yyyy-03-01" in the non-leap years
y <- ifelse(as.POSIXlt(x)$mday == 29, x, NA)
head(y) # not what you expected ... ==> need restore the class attribute:
class(y) <- class(x)
y
## ==> Again a case where it is better *not* to use ifelse(), but
## both more efficient and clear:
y2 <- x
y2[as.POSIXlt(x)$mday != 29] <- NA
stopifnot(identical(y2, y))


## example of different return modes:
yes <- 1:3
no <- pi^(0:3)
typeof(ifelse(NA,    yes, no)) # logical
typeof(ifelse(TRUE,  yes, no)) # integer
typeof(ifelse(FALSE, yes, no)) # double
```

Eample three

```
help.search("linear models")    # In case you forgot how to fit linear
                                # models
help.search("non-existent topic")

??utils::help  # All the topics matching "help" in the utils package


help.search("print")            # All help pages with topics or title
                                # matching 'print'
help.search(apropos = "print")  # The same

help.search(keyword = "hplot")  # All help pages documenting high-level
                                # plots.
file.show(file.path(R.home("doc"), "KEYWORDS"))  # show all keywords

## Help pages with documented topics starting with 'try'.
help.search("\\btry", fields = "alias")
```


Example four

```
db <- hsearch_db()
## Total numbers of documentation objects, aliases, keywords and
## concepts (using the current format):
sapply(db, NROW)
## Can also be obtained from print method:
db
## 10 most frequent concepts:
head(hsearch_db_concepts(), 10)
## 10 most frequent keywords:
head(hsearch_db_keywords(), 10)

```
