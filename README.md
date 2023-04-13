# Lab-7_202001125

## Section A: 

Consider a program for determining the previous date. Its input is triple of day, month and year with the following ranges 1 <= month <= 12, 1 <= day <= 31, 1900 <= year <= 2015.The possible output dates would be previous date or invalid date. Design the equivalence class test cases?
Write a set of test cases (i.e., test suite) – specific set of data – to properly test the programs. Your test suite should include both correct and incorrect inputs.
1. Enlist which set of test cases have been identified using Equivalence Partitioning and Boundary Value. Analysis separately.
2. Modify your programs such that it runs on eclipse IDE, and then execute your test suites on the program. While executing your input data in a program, check whether the identified expected outcome (mentioned by you) is correct or not.


The equivalent classes are:

| Partition | Test Case | Status |
| --- | --- | --- |
| EC1 | Date >=1 && Date <= 31 | Valid |
| EC2 | Date < 1 | Invavalid |
| EC3 | Date > 31 | Invalid | 
| EC4 | Month >= 1 && Month <= 12 | Valid |
| EC5 | Month < 1 | Invalid | 
| EC6 | Month > 12 | Invalid |
| EC7 | Year >= 1900 && Year <= 2015 | Valid |
| EC8 | Year < 1900 | Invalid |
| EC9 | Year > 2015 | Invalid |


The equivalence test cases for the same are:

| Partition | Date | Month | Year | Output |
| --- | --- | --- | --- | --- |
| EC1 | 3 | 1 | 2000 | 02/01/2000 |
| EC2 | 0 | 1 | 2000 | Invalid |
| EC3 | 32 | 1 | 2000 | Invalid |
| EC4 | 1 | 1 | 1980 | 31/12/1979 |
| EC5 | 3 | -3 | 2000 | Invalid |
| EC6 | 3 | 15 | 2000 | Invalid |
| EC7 | 3 | 1 | 2000 | 02/01/2000 |
| EC8 | 3 | 1 | 1000 | Invalid |
| EC9 | 3 | 1 | 3000 | Invalid |


Equivalence Partitioning  

Valid dates
- 14-12-2011: Output - 13-12-2011
- 1-1-2014: Output - 31-12-2013

Invalid dates 
- 31-4-2016
- 14-45-1899

Out of range dates
- 15-4-1899
- 15-5-2022


Boundary Value Analysis

- Earliest date - 1-1-1900
- Last date - 31-12-2015
- Leap years
- Invalid leap year date - 29-2-2001
- Previous of earliest date
- Date after latest date - 1-1-2016



### Programs:

#### P1
The function linearSearch searches for a value v in an array of integers a. If v appears in the array a, then the function returns the first index i, such that a[i] == v; otherwise, -1 is returned.

![image](https://user-images.githubusercontent.com/75677179/231825318-4f7f057e-3a31-4c2f-b86c-3c6e63f2b149.png)


Equivalence Partitioning 

- If v is present in a ------------> return index of v
- If v is not present -------------> return -1

Boundary Value Analysis

- Empty array -----> return -1
- Not present -----> return -1
- Present at i=0 ---> return 0

Test Cases
- v = 3; a[] = {1,2,3}; expected = 2: Test Case Passed
- v = 3; a[] = {1,2,4,5}; expected = 2: Test Case Failed

#### P2. 

The function countItem returns the number of times a value v appears in an array of integers a.

![image](https://user-images.githubusercontent.com/75677179/231825460-3798ab23-5f1a-4de0-847d-272284139f16.png)

Equivalence Partitioning 

- if v is present in a ------------> return number of times v appears
- if v is not present -------------> return 0

Boundary Value Analysis

- empty array -----> return 0
- not present -----> return 0
- present at i=0 ---> return 1
- present multiple times ----> return count

Test cases
- v = 3; a[] = {1,2,3,3,3}; expected = 3: Test Case Passed
- v = 10; a[] = {10, 20, 10}; expected = 1: Test Case Failed


#### P3
The function binarySearch searches for a value v in an ordered array of integers a. If v appears in the array a, then the function returns an index i, such that a[i] == v; otherwise, -1 is returned.
Assumption: the elements in the array a are sorted in non-decreasing order.
int binarySearch(int v, int a[])

![image](https://user-images.githubusercontent.com/75677179/231826220-335c2cc6-01a2-4004-955f-1fc5669800c0.png)

Equivalence Partitioning 

- if v is present in a ------------> return index of v
- if v is not present -------------> return -1

Boundary Value Analysis

- empty array -----> return -1
- not present -----> return -1
- present at i=0 ---. return 0

Test Cases
- v = 3; a[] = {1,2,3,4,5}; expected = 2: Test Case Passed
- v = 3; a[] = {1,2,3,4,5}; expected = 3: Test Case Failed


#### P4
The following problem has been adapted from The Art of Software Testing, by G. Myers (1979). The function triangle takes three integer parameters that are interpreted as the lengths of the sides of a triangle. It returns whether the triangle is equilateral (three lengths equal), isosceles (two lengths equal), scalene (no lengths equal), or invalid (impossible lengths).

![image](https://user-images.githubusercontent.com/75677179/231826664-537d5806-cfa3-4584-bdd2-109760b04ea5.png)

Equivalence Partitioning

- a + b <= c -----------> INVALID
- a = b = c ------------> Equilateral Triangle
- a = b < c ------------> Isosceles Triangle
- a < b < c ------------> Scalene Triangle

Boundary Value Analysis

- a + b <= c ------> Invalid
- b + c <= a ------> Invalid
- c + a <= b ------> Invalid
- a = b = c -------> Equilateral
- a = b < c -------> Isosceles
- b = c < a -------> Isosceles
- c = a < b -------> Isosceles
- a < b < c -------> Scalene

Test cases
- a = 3; b=3; c = 3; expected = 0: Test Case Passed
- a = 1, b= 2, c= 3; expected = 0: Test case failed!



#### P5 
The function prefix (String s1, String s2) returns whether or not the string s1 is a prefix of string s2 (you may assume that neither s1 nor s2 is null).
public static boolean prefix(String s1, String s2)
![image](https://user-images.githubusercontent.com/75677179/231827491-46238997-8ac2-4bb7-946b-7a961e6fcdf4.png)

Equivalence Partitioning

- empty s1 and s2 -----> true
- empty s1 ------> true
- s1 prefix of s2 ---> true
- s1 not prefix of s2 ---> false
- s1 longer than s2 ----> false

Boundary value analysis

- empty s1 and s2 -----> true
- empty s1 ------> true
- s1 prefix of s2 ---> true
- s1 longer than s2 ----> false

Test cases
- String s1 = "abc", s2 = "abcd"; expected = true: Test c\Case Passed
- String s1 = "abc", s2 = "ab"; expected = true: Test Case Failed



#### P6
Consider again the triangle classification program (P4) with a slightly different specification: The program reads floating values from the standard input. The three values A, B, and C are interpreted as representing the lengths of the sides of a triangle. The program then prints a message to the standard output that states whether the triangle, if it can be formed, is scalene, isosceles, equilateral, or right angled.
Determine the following for the above program:

a) Identify the equivalence classes for the system
Equivalence Classes will contain:

- All sides are positive, real numbers.
- One or more sides are negative or zero.
- The sum of the lengths of any two sides is less than or equal to the length of the remaining side.
- The sum of the lengths of any two sides is greater than the length of the remaining side.
- Examples
  - E1 : a+b<=c (point 3)
  - E2 : a+c<=b (point 3)
  - E3 : b+c<=a (point 3)
  - E4 : a=b, b=c, c=a
  - E5 : a=b, a!=c 
  - E6 : a=c, a!=b
  - E7 : b=c, b!=a 
  - E8 : a!=b ,b!=c, c!=a
  - E9 : a^2 + b^2 = c^2 
  - E10: b^2 + c^2 = a^2
  - E11: a^2 + c^2 = b^2
  - E12 : a+b>=c (point 4)
  - E13 : a+c>=b (point 4)
  - E14 : b+c>=a (point 4)

b) Identify test cases to cover the identified equivalence classes. Also, explicitly mention which test case would cover which equivalence class.
- Test cases
  - Right angled triangle (point 1 of (a)) - A = 5, B = 12, C = 13
  - Equilateral triangle (point 1 of (a)) - A = 3, B = 3, C = 3
  - Scalene triangle (point 1 of (a)) - A = 3, B = 4, C = 3
  - Isosceles triangle (point 1 of (a)) - A = 3, B = 2, C =3
  - Invalid Input - A = 1, B = 2, C = 3
  - Invalid Input - A = 0, B = 4, C = -1

c) For the boundary condition A + B > C case (scalene triangle), identify test cases to verify the boundary.
- Test cases
  - A = 5, B = 4, C =3
  - A = 5, B = 1, C = 6
  - A = 2, B = 3, C = 6

d) For the boundary condition A = C case (isosceles triangle), identify test cases to verify the boundary.
- Test cases
  - A = 4, B = 3, C = 4
  - A = 4, B = 3, C = 3.9
  - A = 4, B = 3, C = 4.1

e) For the boundary condition A = B = C case (equilateral triangle), identify test cases to verify the boundary.
- Test cases
  - A = 4, B = 3, C = 4
  - A = 4, B = 3, C = 3.9
  - A = 4, B = 3, C = 4.1

f) For the boundary condition A2 + B2 = C2 case (right-angle triangle), identify test cases to verify the boundary.
- Test cases
  - A = 3, B = 4, C = 5
  - A = 6, B = 8, C = 10

g) For the non-triangle case, identify test cases to explore the boundary.
- Test cases
  - A = 2, B = 2, C = 4
  - A = 2, B = 4, C = 2

h) For non-positive input, identify test points.
- Test cases
  - A = -3, B = 3, C = 4.5
  - A = 0, B = 4, C = 5




## Section B

The code below is part of a method in the ConvexHull class in the VMAP system. The following is a small fragment of a method in the ConvexHull class. For the purposes of this exercise you do not need to know the intended function of the method. The parameter p is a Vector of Point objects, p.size() is the size of the
vector p, (p.get(i)).x is the x component of the ith point appearing in p, similarly for (p.get(i)).y. This exercise is concerned with structural testing of code and so the focus is on creating test sets that satisfy some particular coverage criterion.

#### Control Flow Graph
![image](https://user-images.githubusercontent.com/75677179/231830674-f8142c1b-d16f-4cb0-8efe-425969337634.png)

#### Statement coverage test sets:

- Test cases
  - Empty vector
  - Vector with one point
  - Vector with two points having same y component
  - Vector with two points having different y components
  - Vector with three or more different points with different points with same y components
  - Vector with three or more different points with different points with different y components


#### Branch coverage test sets:

- Test cases
  - Empty vector
  - Vector with one point
  - Vector with two points having same y component
  - Vector with two points having different y components
  - Vector with three or more different points with different points with same y components and with same x components.
  - Vector with three or more different points with different points with different y components and with same x components.
  - Vector with three or more points with the same x and y components



c) Basic condition coverage test sets:

- Test cases
  - Empty vector
  - Vector with one point
  - Vector with two points having same y component
  - Vector with two points having different y components
  - Vector with three or more different points with different points with same y components and with same x components.
  - Vector with three or more different points with different points with different y components and with same x components.
  - Vector with three or more points with the same x and y components
  - Vector with some of them having same x component and all of them having same y component
