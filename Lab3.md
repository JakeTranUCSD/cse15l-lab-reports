
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

**5. Explanation:**
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


**Usage in ./technical:**


**grep -i examples:**

Input: `grep -i "conclusion" biomed/1471-2202-3-8.txt`
Output:


<img width="562" alt="Screen Shot 2024-05-08 at 11 24 54 PM" src="https://github.com/JakeTranUCSD/cse15l-lab-reports/assets/147591070/318972d0-f66c-476a-ac2e-e1d7076da129">


Input: `grep -i "hbas" plos/pmed.0020150.txt`
Output:


<img width="730" alt="Screen Shot 2024-05-08 at 11 26 26 PM" src="https://github.com/JakeTranUCSD/cse15l-lab-reports/assets/147591070/3575dc90-a0e2-4076-8f95-b46555dd1da9">


**grep -n examples:**


Input: `grep -n "med" plos/pmed.0020149.txt`
Output:


<img width="734" alt="Screen Shot 2024-05-08 at 11 26 55 PM" src="https://github.com/JakeTranUCSD/cse15l-lab-reports/assets/147591070/c6fb52f8-c375-46de-8869-c0574a975cf4">


Input: `grep -n "you" government/Media/Justice_for_all.txt`
Output:


<img width="581" alt="Screen Shot 2024-05-08 at 11 27 47 PM" src="https://github.com/JakeTranUCSD/cse15l-lab-reports/assets/147591070/0cfa18cd-d5fb-47ec-9c91-e7595bd9d89c">


**grep -r examples:**


Input: `grep -r "you" government`
Output:


<img width="866" alt="Screen Shot 2024-05-08 at 11 28 42 PM" src="https://github.com/JakeTranUCSD/cse15l-lab-reports/assets/147591070/fdf803e2-0d21-43dc-bda0-eef8f0459dd5">



Input: `grep -r "you" biomed`
Output:


<img width="728" alt="Screen Shot 2024-05-08 at 11 29 21 PM" src="https://github.com/JakeTranUCSD/cse15l-lab-reports/assets/147591070/d71ceefc-fecf-4cfd-9d93-7c1aef6feabd">


**grep -v examples:**


Input: `grep -v "s" plos/journal.pbio.0030137.txt`
Output:


<img width="712" alt="Screen Shot 2024-05-08 at 11 29 48 PM" src="https://github.com/JakeTranUCSD/cse15l-lab-reports/assets/147591070/a83bbc6d-359e-456d-a897-2514c00ca5b6">



Input: `grep -v "s" 911report/chapter-10.txt`
Output:


<img width="699" alt="Screen Shot 2024-05-08 at 11 30 37 PM" src="https://github.com/JakeTranUCSD/cse15l-lab-reports/assets/147591070/fd7283c2-fa2d-45cb-b5ab-ec08261e979a">




**Thanks for reading, have a great day!**
