# Matlab Basic

## User Input

Use the built-in input function. Datatype input are just like the once in C programming
```matlab
input("Sentences : ", "datatype input (%s - string, and etc)")
```

Example
```matlab
name = input("What's your name : ", "%s");
```

To output string or char
```matlab
fprintf(name)   % fancy print
```

To output a value
```matlab
vec = [1 2 3]
disp(vec)
```

## Variables / Data Types

- Variables start with a letter and then numbers
- Data types are classes which also have associated 
methods for working with that data
    - Types include ```int8```, ```int16```, ```int32```, ```int64```, ```char```, ```logical``` (boolean), ```double```, ```single``` (generic int) and unsigned ```uint8```, ...

Declaring variable is like Python (no need to put datatypes in front)
```matlab
var = 'String'
```

class function display the data type
```matlab
var = 'String'
class(var)  % 'string' - char and "string" - string
```

Boolean map true as 1 and false as 0
```matlab
5 > 2
b1 = true
```

Show max and min value

```matlab
intmin('int8')
intmax('int8')
```

Find largest double
```matlab
realmax
```

Find largest integer
```matlab
realmax('single')
```

You can continue the expressions into newline using ```...```

```matlab
v1 = 1 + 2 + 3 ...
+ 4
```


## Casting

Everything defaults to double
```matlab
v2 = 8
class(v2)
>>> ans = 
        'double'
```

Cast to int8
```matlab
v3 = int8(v2)
class(v3)
>>> ans = 
        'int8'
```

Convert char to double
```matlab
v4 = double('A')    % v4 = 65
```

Convert to Char
```matlab
v5 = char(64)   % v5 = '@'
```

## Math Opertors & Sprintf

```sprintf``` formats a string


- ```%d``` - Integers
- ```%f``` - Floats 
- ```%e``` - exponential notation 
- ```%c``` - Characters
- ```%s``` - Strings

Example
```matlab
fprintf('5 + 4 = %d\n', 5 + 4)  % 5 + 4 = 9
fprintf('5 - 4 = %d\n', 5 - 4)  % 5 - 4 = 1
fprintf('5 * 4 = %d\n', 5 * 4)  % 5 * 4 = 20
```

Define your value want only 2 decimals
```matlab 
fprintf('5 / 4 = %0.2f\n', 5 / 4)
```

Exponentiation
```matlab 
fprintf('5^4 = %d\n', 5^4) 
```

Modulus (Escape % by doubling)
```matlab 
fprintf('5 %% 4 = %d\n', mod(5,4))
```

Generate a random value between 10 & 20
```matlab 
randi([10,20])
```
Precision is accurate to 15 digits by default
```matlab 
bF = 1.1111111111111111
bF2 = bF + 0.1111111111111111
fprintf("bF2 = %0.16f\n", bF2)
```


## Math Functions
- Absolute value -  ```abs(x)```
- Floor estimation - ```floor(x)```
- Ceiling estimation - ```ceil(x)```
- Rounding values - ```round(x)```
- Exponential (e<sup>x</sup>) - ```exp(x)```
- Logorithm - ```log(x)```
- log base 10 (log<sub>10</sub> x) - ```log10(x)```
- log base 2 (log<sub>2</sub> x) - ```log2(x)```
- Square root - ```sqrt(x)```
- Degrees to radian - ```deg2rad(x)```


```matlab
fprintf('abs(-1) = %d\n', abs(-1))   
fprintf('floor(2.45) = %d\n', floor(2.45)) 
fprintf('ceil(2.45) = %d\n', ceil(2.45))
fprintf('round(2.45) = %d\n', round(2.45))
fprintf('exp(1) = %f\n', exp(1)) % e^x
fprintf('log(100) = %f\n', log(100))
fprintf('log10(100) = %f\n', log10(100))
fprintf('log2(100) = %f\n', log2(100))
fprintf('sqrt(100) = %f\n', sqrt(100))
fprintf('90 Deg to Radians = %f\n', deg2rad(90))
```

## Conditionals

Relational Operators: ```>```, ```<```, ```>=```, ```==```, and ```~=```(Not equal)

Logical Operators: ```||``` (or), ```&&``` (and), ```~``` (not)

```matlab
age = 12

if age >= 5 && age <= 6
    disp("You're in Kindergarten")
elseif age >= 7 && age <= 13
    disp("You're in Middle School")
elseif age >= 14 && age <= 18
    disp("You're in High School")
else
    disp("Stay Home")
end

true || false % 1 (true)
~true   % false
```

Switch is used when you have a limited number of options

```matlab
switch age
    case 5
        disp("Go to Kindergarten")
    case num2cell(6:13)
        disp("Go to Middle School")
    case {14,15,16,17,18}
        disp("Go to High School")
    otherwise
        disp("Stay Home")
end
```

## Vectors

Vectors are either row or column vectors or 1 dimensional arrays
```matlab
vt1 = [5 3 2 1]
```

Length of the  vector
```matlab
vL =  length(vt1)
```

Sort in ascending order
```matlab
vt1 = sort(vt1)
```

Sort in descending order
```matlab
vt1 = sort(vt1, 'descend')
```

Create a range
```matlab
vt2 = 5:10
```

Create a range with a step
```matlab
vt3 = 2:2:10
```

Concatenate vectors
```matlab
vt4 = [vt1 vt2]
```

Get a value with an index starting at 1
```matlab 
vt4(1)
```

Get the last value
```matlab 
vtEnd = vt4(end)
```

Change a value
```matlab 
vt4(1) = 12
```

Add to the end (0 is added to indexes between)
```matlab 
vt4(11) = 33
```

Get 1st 3 values
```matlab 
vt4(1:3)
```

Get 2, 4th and 6th
```matlab 
vt4([2 4 6])
```

Create a column vector
```matlab 
vt5 = [2;3;4]
% And another row
vt6 = [1 2 3]
```

### Vector multiplication
 
We need a column and row vector
 
Multiply ```vt6(1,1)``` by each row in ```vt5(1,:)```
```matlab
vtMult = vt5 * vt6
```
Dot Product
 
```(1*4) + (5*2) + (3*6) = 32```
```matlab 
vt7 = [4 5 6]
```

Tranposes the vector
```matlab 
vtDotP = vt6 * vt7'
% or
vtDotP2 = dot(vt6, vt7)
```
 
Cross Product
```
[a1, a2, a3] [b1, b2, b3]
(1,1) = (a2*b3) - (a3*b2)
(1,1) = (2*6) - (3*5) = -3
(2,1) = (a3*b1) - (a1*b3)
(3,1) = (a1*b2) - (a2*b1)
vtCross = cross(vt6, vt7)
```
Create linearly spaced vector with for elements between 1 and 20
```matlab
vt8 = linspace(1,20,4)
```

Logarithmically spaced vector 10<sup>1</sup>, 10<sup>2</sup>, 10<sup>3</sup>
```matlab
vt9 = logspace(1,3,3)
```


## Matrices

Matrices have rows and columns
```matlab
m1 = [2 3 4; 4 6 8]
```

Number of values in a row
```matlab
mNRV = length(m1)
```

Total number of values
```matlab
mNV = numel(m1)
``` 

Get row and column size
```matlab
mS = size(m1)
```

Store rows and columns in different variables
```matlab
[nRows, nCols] = size(m1)
```

Generate random matrix with 2 rows between 10 & 20
```matlab
m2 = randi([10,20], 2)
```

Use row then column to get a value
```matlab
m2(1,2)
```

Change a value
``matlab
m2(1,2) = 22
```

Change all row values
```matlab
m2(1,:) = 25
```

Change all column values
```matlab
m2(:,1) = 36
```

Get 1st value in the last row
```matlab
mR1Last = m2(end,1)
```

Get the 2nd value in last column
```matlab
MR2Last = m2(2,end)
```

Delete the 2nd column
```matlab
m2(:,2)
```

## Looping

For loop
```matlab
for i = 1:10
    disp(i)
end
```

Decrement and stepping
```matlab
for i = 10:-1:0
    disp(i)
end
```

Specify values
```matlab
for i = [2 3 4]
    disp(i)
end
```

Cycle through a matrix
```matlab
m4 = [2 3 4; 4 6 8]
for i = 1:2
    for j = 1:3
        disp(m4(i,j))
    end
end
```

Cycle through a vector
```matlab
lVect = [6 7 8]
for i = 1:length(lVect)
    disp(lVect(i))
end
```

While loop
```matlab
i = 1
 
% Print out only evens
while i < 20
    if (mod(i,2)) == 0
        disp(i)
        
        % MatLab doesn't have ++, +=
        i = i + 1;
        
        % Skip back to the top of the loop
        continue 
    end
 
    i = i + 1;
 
    if i >= 10
        
        % Leave the loop
        break 
    end
end
```

## Matrix Functions

sample matrix
```matlab
m3 = [2 3 4; 4 6 8; 8 12 16; 16 24 32]
```

You can added, subtract, etc. matrice
```matlab 
m4 = [1:3; 4:6]
m5 = [2:4; 5:7]
 
m4 + m5
m4 .* m5
```

Functions perform operations on each value
```matlab 
sqrt(m3)
m3 = m3 * 2
```

Sum adds all the columns
```matlab 
sum(m3)
```
 
### Matrix Multiplication
 
Columns of m6 must equal rows in m7
```matlab 
m6 = [1 2 3;
    4 5 6]
 
m7 = [1 1 1 1;
    2 2 2 2;
    3 3 3 3]
 
% m8(1,1) = (1*1) + (2*2) + (3*3) = 14
 
m8 = m6 * m7
```

Check how many values are greater then 3
```matlab 
gT3M = m4 > 3
sum(gT3M, 'all')
```

Check for equality
```matlab 
isequal(m4, m5)
```

Find matching value indexes
```matlab 
find(m3 > 24)
```

Multiply column values
```matlab 
prod(m3)
```

1st row stays the same and each after is a sum of the proceeding and current row cumsum(m3, 'reverse') starts in opposite order
```matlab 
cumsum(m3)
```

Like cumsum, but with multiplication
```matlab 
cumprod(m3)
```

Flip 1st column to last
```matlab 
fliplr(m3)
```

Flip rows
```matlab 
flipud(m3)
```

Rotate 90 degrees
```matlab 
rot90(m3)
```

Rotate 180 degrees
```matlab 
rot90(m3,2)
```

Convert into a 2 x 6 matrix
```matlab 
reshape(m3, 2, 6) 
```

Duplicate matrix into new matrix 2 rows by 1 column
```matlab 
repmat(m3, 2, 1)
```

Duplicates elements into new matrix 2 rows for each value
```matlab 
repelem(m3, 2, 1)
```

## Cell Arrays

Stores values of different types
```matlab 
cA1 = {'Doug Smith', 34, [25 8 19]}
```

Define the number of spaces to set aside
```matlab 
cA2 = cell(5)
```

Get by index
```matlab 
cA1{1}
cA1{3}(2)
```

Add more data
```matlab 
cA1{4} = 'Patty Smith'
```

Get size
```matlab 
length(cA1)
```

Delete a value
```matlab 
cA1(4) = []
```

Output
```matlab 
for i = 1:length(cA1)
    disp(cA1{i})
end
```

Cell Array to char matrix
```matlab 
cA3 = {'Doug' 'Patty'}
nameMat = char(cA3)
```

Char array to cell array
```matlab 
cA4 = cellstr(nameMat)
```

## Strings


Strings are vectors of characters 
```matlab 
str1 = 'I am a string'
```

Get length
```matlab 
length(str1)
```

Character at index
```matlab 
str1(1)
```

Get substring
```matlab 
str1(3:4)
```

Join strings (Escape ' with '')
```matlab 
str2 = strcat(str1, ' that''s longer')
```

Find all index matches for a string
```matlab 
strfind(str2, 'a')
```

Replace any matches
```matlab 
strrep(str2, 'longer', 'bigger')
```

Split string using delimiter ```' '```
```matlab 
strArray = strsplit(str1, ' ')
class(strArray)
strArray(1)
```

Convert cell array into a string
```matlab 
cA5 = {'I' 'like' 'chickens'}
str3 = strjoin(cA5)
```

Integer to string
```matlab 
nStr = int2str(99)
```

Float to str
```matlab 
fStr = num2str(3.14)
```

Compare for equality
```matlab 
strcmp(str1, str2)
```

Check if is a character
```matlab 
isletter('num 2')
```

Check if all are letters ('alphanum' letters or numbers)
```matlab 
isstrprop('word2', 'alpha')
```

Is it a string
```matlab 
ischar('Some words 2')
```

Sort ascending (, 'descend')
```matlab 
sort(str3)
```

Delete whitespace
```matlab 
strtrim(str1)
```

Uppercase & lowercase
```matlab 
lower(str1)
upper(str1)
```

## Structures

Custom data type that stores related data in fields
```matlab 
dougSmith = struct('name', 'Doug Smith', ...
    'age', 34, 'purchases', [12 23])
```

Access data
```matlab 
disp(dougSmith.age)
```

Add a field
```matlab 
dougSmith.wife = 'Patty Smith'
```

Remove a field
```matlab 
dougSmith = rmfield(dougSmith, 'wife')
```

Check for a field
```matlab 
isfield(dougSmith, 'wife')
```

Get fields
```matlab 
fieldnames(dougSmith)
```

Store structs in a vector
```matlab 
customers(1) = dougSmith
sallySmith = struct('name', 'Sally Smith', ...
    'age', 34, 'purchases', [18])
customers(2) = sallySmith
```

Get data
```matlab 
disp(customers(2).name)
```

## Tables
Tables are labeled rows of data in a table format

```matlab 
name = {'Jim'; 'Pam'; 'Dwight'};
age = [28; 27; 31];
salary = [35000; 26000; 75000];
id = {'1', '2', '3'};
```

RowNames defines the name used for each row
```matlab 
employees = table(name, age, salary, 'RowName', id)
```

Get avg salary
```matlab 
meanSalary = mean(employees.salary)
```

Add column of data
```matlab 
employees.vDays = [10; 14; 16]
```

Show just 2 by id
```matlab 
employees({'1', '2'},:)
```

Get by name
```matlab 
employees(ismember(employees.name,{'Jim' 'Dwight'}), :)
```

## File I/O

Generate a random 8x8 matrix between 10 & 50
```matlab 
randM = randi([10,50], 8)
```

Save the file as a text file and overwrite
```matlab  
save sampdata.dat randM -ascii
```

Read the data into a matrix with the same name as the data file
```matlab  
load sampdata.dat
disp(sampdata)
```

Display file data
```matlab  
type sampdata.dat
```

Saving variables to a file, save yourfile (saves every variable)
```matlab  
save myData
```

Read file
```matlab  
load myData
who
```

Append data
```matlab  
v4 = 123
save -append myData v4
```

## Functions

Get cylinder volume
 
tic toc is used to calculate how long it took
 
for code to execute

```matlab 
tic 
cylinderVol(20, 30)
toc
```
 
Try to change a variable value in a function
```matlab  
changeMe = 5
changeVal()
disp(changeMe)
```

Function with no arguments
```matlab  
getRandomNum
```

Return more then 1 value
```matlab  
[coneV, cylVol] = getVols(10,20)
```

Eval will execute code saved as a string
```matlab 
toExecute = sprintf("total = %d + %d", 5, 4)
eval(toExecute)
```

Except a variable number of arguments
```matlab  
theSum = getSum(1, 2, 3, 4)
```

Return a variable number of values
```matlab  
listOfNums = getNumbers(10)
```

Create a function that finds the volume of a cylinder

```matlab 
% Format 
function returnVar = funcName(arguments)
 
% Example
function vol = cylinderVol(radius, height)
vol = pi * radius^2 * height
end
```

Try to change a variable value in a function
 
If you return nothing leave it out
```matlab  
function changeVal()
% This is a local or variable specific to the function
 
changeMe = 10
class(changeMe)
end
```

Return a random value
```matlab  
function randNum = getRandomNum
randNum = randi([1,100])
end
```

Return multiple volumes
```matlab  
function [coneVol, cylinVol] = getVols(radius, height)
cylinVol = pi * radius^2 * height
coneVol = 1/3 * cylinVol
end
```

Variable arguments stored in varargin
```matlab  
function sum = getSum(varargin)
sum = 0;

% Cycle through contents while adding

for k = 1:length(varargin)
    sum = sum + varargin{k}(1);
end
end
```
 
Returns a variable number of values
```matlab  
function [varargout] = getNumbers(howMany)
for k = 1:howMany
    varargout{1}(k) = k;
end
end
```

Receives a function
```matlab  
function sol = doMath(func, num)
sol = func(num);
end
```
 
Return a function
```matlab  
function func = doMath2(num)
func = @(x) x * num;
end
```

Every recursive function must reach a point where it no longer makes a function call
```matlab 
function val = factorial(num)
 
if num == 1
    val = 1;
else
    val = num * factorial(num - 1);
end
end
```

## Anonymous Functions

Anonymous functions are one line functions

```matlab
% Format
nameOfFunc = @ (attr) functionBody;

% Example
cubeVol = @ (l, w, h) l * w * h;
cV = cubeVol(2,2,2)
```
 
Pass function to function
```matlab
mult3 = @ (x) x * 3;
sol = doMath(mult3, 4)
```

Return a function
```matlab
mult4 = doMath2(4);
sol2 = mult4(5)
```

## Recursive Functions

Recursive functions call themselves
 
Calculate factorial
 
```1st : result = 4 * factorial(3) = 4 * 6 = 24```
 
```2nd : result = 3 * factorial(2) = 3 * 2 = 6```
 
```3rd : result = 2 * factorial(1) = 2 * 1 = 2```
 
```matlab 
fact4 = factorial(4)
```

## Object Oriented Programming (OOP)

Real world objects have attributes (height, weight) & capabilities (run, eat). Classes model real world objects by storing attributes as properties and model capabilities using methods
 
A class as a blueprint then creates objects
 
Classes must be created in their own file with class name == file name
 
```matlab 
a1 = Shape(10, 20);
disp(a1)
Shape.setGetNumShapes
a1.getArea
 
a2 = Shape(5, 10)
disp(a2)
Shape.setGetNumShapes
 
a1 > a2
 
a3 = Trapezoid(10, 4, 6);
disp(a3)
a3.getArea
```

## Plotting

Define x & y values

```matlab 
xVals = 1:5
yVals = [2 4 8 5 9]
yVals2 = [1 5 7 6 8]
```

Creates window labeled figure 1 with plot
```matlab 
figure(1)
```

- Colors : blue(b), black(k), cyan(c), green(g), 
 
- magenta(m), red(r), yellow(y), white(w)
 
- Plot Symbols : . o x + * s d v ^ < > p h
 
- Line Types : -, :, -., - -
 
 
Green dotted line with + at points 2 line width
```matlab 
plot(xVals, yVals, 'g+:','LineWidth',2)
```
Draw over previous plot
```matlab 
hold on
```

Draw black stars on points
```matlab 
plot(xVals, yVals2, 'k*')
```

Defines look of each plot
```matlab 
legend('yVals', 'yVals2')
```

Show grid
```matlab 
grid on
```

Define x & y lables & Title
```matlab 
xlabel('Days')
ylabel('Money')
title('Money made Today')
```

Creates window labeled figure 2 with bar chart
```matlab 
figure(2)
bar(xVals, yVals, 'r')
```