# BIG O

> 💡Cheat Sheet [https://zerotomastery.io/cheatsheets/big-o-cheat-sheet/?utm_source=udemy&utm_medium=coursecontent](https://zerotomastery.io/cheatsheets/big-o-cheat-sheet/?utm_source=udemy&utm_medium=coursecontent)

**What is good code?**

it is 2 things

1. Readable

1. Scalable (BIG O)

BIG O Notations are somethings that is going to help us measure code that can scale
Imagine a task where we want to bake a cake we have recipe, kitchen and bake a cake

Just like there are many ways to bake a cake and different kinds of ingredients. Naturally there are efficient ways and in-efficient ways. BIG O helps us to analyze the efficient way.

``` js
const nemo = ["n emo"];

function findNemo(array)
{
    for(let i = 0; i < array.length; i++)
    {
        if(array[i] === "nemo")
        {
            console.log("Found nemo");
        }
    }
}

findNemo(nemo);
```

The above function executes in milliseconds because there's only a single element in the array.

``` js
const large = new Array(10000).fill("nemo");

function findNemo(array)
{
    for(let i = 0; i < array.length; i++)
    {
        if(array[i] === "nemo")
        {
            console.log("Found nemo");
        }
    }
}

findNemo(large);
```

if you run the above function the more you increase the size of the array the more time it is going to take to execute the code. Depending on the hardware the speed of execution.
Using Big O you can determine which one better than other without depending on the hardware

---

BIG O Notations
![Alt Text](https://miro.medium.com/v2/resize:fit:1400/1*5kIxfN2goP8qfFWjZmUvMQ.jpeg)

- **Linear time -> Big O(n) / O(n)**
  - Linear time or  O(n) means as the input size increases the time to execute a piece of code also increases.
  - In the findNemo function this is what happens as you increase the size of the array the time to execute the code increases.
  - O(n) -> means the big o depends on the number of input. here n is 10000.

---

- **Constant Time -> Big O(1)**
    lets consider a function

    ``` js
    function compressFirstBox(boxes)
    {
        console.log(boxes[0]);
    }
    ```

  - Looking at the function all it does is compress the first box in the array of boxes
  - This operation is constant no matter the size of the array if the size of array is 1 then the first element is compressed. If the size of the array is 10000 just the first box is compressed this is called constant time.
  - In the above image O(n) is the dark green area. it is the most efficient Big O.

  ``` js
  function funChallenge(input) {
    let a = 10; //0(1)
    a = 50 + 3; //0(1)

    for (let i = 0; i < input. length; i++) { //0(n)
        anotherFunction(); //0(n)
        let stranger = true; //0(n)
        a++; //0(n)
    }
    return a; //0(1)
    }
    funChallenge()

    // 3 + n + n + n + n -> Big O (3 + 4n) -> O(n) based on rule Remove COnstants
  ```

*Other Complexities are*

- **Logarithmic O(log n)**
  - Usually Searching algorithms have log n time complexity if the given input is sorted for example binary search.

- **Logarithmic linear O(nlog n)**
  - Usually Sorting algorithms have *nlog n* time complexity.

- **Quadratic O(n^2)**
  - Every element in a collection needs to be compared to ever other element. Two
nested loops.

- **Exponential O(2^n)**
  - Recursive algorithms that solves a problem of size N

- **Factorial O(n!)**
  - You are adding a loop for every elemen

  ---

- Simplify Big O
  - There are 4 rules to follow that can simplify your big o calculation
        - *Worst case* -> you should always thing of the worst case.
        - *Remove Constants* -> always remove the constants. Big O does not care about the patterns
        - *Different terms for inputs* -> if there are 2 different inputs then you need to consider both the input sizes

    ``` js
    function compressBoxesTwice(boxes1, boxes2)
    {
        boxes1.foreach(box => {
            console.log(box);
        })
        boxes2.foreach(box => {
            console.log(box);
        })
    }
    // the big o will be O(boxes1 + boxes2) because both are different and the size can be different
    ```

    - *Drop non dominants* -> In the grand scheme of things you need to drop any non dominant value for example

    ``` js
    function printAllNumbersAndPairSums(numbers)
    {
        numbers.foreach(number => { // O(n)
            console.log(number);
        })

        numbers.foreach(number1 => { // O(n^2)
            numbers.foreach(number2 => {
                console.log(number1 + number2);
            });
        });
    }

    printAllNumbersAndPairSums([1,2,3,4,5,6]); // O(n + n^2) -> drop non dominant i.e., n -> this becomes O(n^2)
    ```

  There are 3 pillars of programming
  - Readable
  - Scalable
    - Speed ( Time complexity )
    - Memory Efficient ( Space Complexity )

What causes space complexity
    - variables
    - Data structures
    - Function Calls
    - Allocations
