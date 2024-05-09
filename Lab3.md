
# Lab Report 3

## Part 1


The bug I'm using for this report comes from the reverseInPlace method which seeks to reverse the array in place.

**Buggy Implementation of reverseInPlace::**


<img width="376" alt="Screen Shot 2024-05-08 at 5 35 34 PM" src="https://github.com/JakeTranUCSD/cse15l-lab-reports/assets/147591070/daab818a-3e72-4832-a2c2-07c62f693d71">


**1. Failure Input:**


```
	@Test 
	public void testReverseInPlace() {
          int[] input1 = {1, 2, 3, 4, 5};
          ArrayExamples.reverseInPlace(input1);
          assertArrayEquals(new int[]{5, 4, 3, 2, 1}, input1);
	}
```

**2. Non-failure Input:**

```
  @Test 
	public void testReverseInPlace() {
          int[] input1 = { 3 };
          ArrayExamples.reverseInPlace(input1);
          assertArrayEquals(new int[]{ 3 }, input1);
	}
```



**3. Symptoms:**
<img width="826" alt="Screen Shot 2024-05-08 at 5 56 33 PM" src="https://github.com/JakeTranUCSD/cse15l-lab-reports/assets/147591070/ea26d770-d073-4488-bb0b-95024aa9c949">


**4. Before:**
```
  // Changes the input array to be in reversed order
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```

**4. After:**

```
  // Changes the input array to be in reversed order
  static void reverseInPlace(int[] arr) {
    int i0 = arr[0];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
    arr[arr.length - 1] = i0;
  }
```

**5. Explaination:**
In the original implementation, the array was not reversed correctly because the elements are being overwritten before they can be used for reversal. A simple fix for this would be to save the original array in a variable beforehand such that it isn't overwritten for the swap on the otherside of the array. Example: {1,2,3,4,5}, when on 2, it will be set to 4, and 4 in the original array will be set to 2. 

## Part 2
`grep` command: the `grep` command prints lines that have specified patterns.

Example Usage:

Input File (example.txt):

one 
ONE
two
three


<img width="517" alt="Screen Shot 2024-05-08 at 11 21 52 PM" src="https://github.com/JakeTranUCSD/cse15l-lab-reports/assets/147591070/6d4088b4-52dc-41e5-8666-5363382eda11">




**Thanks for reading, have a great day!**
