# What are we doing today?

-   Data structures and algorithms in C++
-   Branching and merging in Git
-   Using light sensor to count grey squares


# What is an object?

-   a module of reusable code
    -   maintains some sort of state
        -   variables
    -   have behaviors
        -   methods
-   can have multiple instances of the same object


# Arrays

-   an object that can contain a set number of other objects
-   the size of the array cannot change

```C++
// creates an array of integers with size 3
#include <array>

array<int, 3> name = {1, 2, 3};
```


<a id="org60b3a3d"></a>

# Array methods

| `at`    | returns the value at a specific index |
| `front` | returns the first item                |
| `back`  | returns the last item                 |
| `size`  | returns the number of elements        |


# Vectors

<div class="NOTES">
initializer lists require c++11 for vectors.

</div>

-   an object that can contain a variable number of other objects
-   you can keep adding elements to the vector
-   order of insertion is maintained

```C++
#include <vector>

vector<int> name = {1, 2, 3};
```


# Vector methods

<div class="NOTES">
Vectors can grow as items are added, whereas arrays are static.

</div>

-   Everything from the [arrays slide](#org60b3a3d), and&#x2026;

| `clear`     | removes all items                   |
| `insert`    | inserts an item at a specific index |
| `push_back` | adds a given element to the end     |
| `pop_back`  | removes the last element            |


# Iterators

-   An object that lets you access and modify objects in a container
-   Depending on their type, they will let you read or write data in the container, and move forwards, backwards, or both
-   The containers library includes the most common ones you'll need, but you can also write your own


# Iterator methods

<div class="NOTES">
picture upcoming. mention that the method should be called on the containing object

</div>

| `*`      | gets the value at the current index                                   |
| `begin`  | starts at the **first** item and moves **forwards** when incremented  |
| `end`    | starts at the **last** item and moves **forwards** when incremented   |
| `rbegin` | starts at the **last** item and moves **backwards** when incremented  |
| `rend`   | starts at the **first** item and moves **backwards** when incremented |


# Moving iterators

<div class="NOTES">
picture upcoming

</div>

-   `++` increments the iterator forwards
-   `--` decrements the iterator backwards


# Iterator practice

<div class="NOTES">
requires c++ 11.

</div>

```C++
vector<int> vec = {66,89,0,60,17,90,8};
vector<int>::iterator it = vec.begin();
```

![img](https://i.imgur.com/MTaVFFM.png)

```C++
vector<int> vec = {66,89,0,60,17,90,8};
vector<int>::iterator it = vec.begin();
it++;
```

![img](https://i.imgur.com/gOXGy4i.png)

```C++
vector<int> vec = {66,89,0,60,17,90,8};
vector<int>::iterator it = vec.begin();
it++;
it--;
```

![img](https://i.imgur.com/394eVwQ.png)

<div class="NOTES">
ask what is the result of this code. Call someone up to show where it will end up

</div>

```C++
vector<int> vec = {66,89,0,60,17,90,8};
vector<int>::reverse_iterator it = vec.rbegin();
it += 3;
```

![img](https://i.imgur.com/wrsXiAZ.png)

<div class="NOTES">
write some for loops using iterators and printing out the numbers

</div>

```C++
vector<int> vec = {66,89,0,60,17,90,8};
vector<int>::reverse_iterator it = vec.rbegin();
it += 3;
```

![img](https://i.imgur.com/BMO9nL9.png)


# Algorithms

-   algorithms is a header that includes useful operators that can be used on vectors, arrays and other containers
-   uses iterators to interact with these containers
-   three cateorgies of algorithm methods
    -   does not modify the container
    -   modifies the container
    -   modifies a destination container


# Does not modify the container

| `count`      | counts the number of items in a container that match a given item  |
| `find`       | returns an iterator to the first element that matches a given item |
| `accumulate` | sums all elements in a container                                   |


# Modifies the container

| `sort`      | sorts a container                                     |
| `fill`      | fills a container with copies of a given element      |
| `iota`      | fills a container with sequentially increasing values |
| `transform` | manipulates each element using a function             |


# Modifies destination container

|       |                                              |
|------ |--------------------------------------------- |
| `copy` | copies elements from one container to another |