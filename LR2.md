# Part 1
![Image](W24_LR3_2.png)
```
@Test
public void testReverseInPlace1(){
  int[] input1 = {5};
  ArrayExamples.reverseInPlace(input1);
  assertArrayEquals(new int[]{5}, input1);
}
```
* The input that doesn't induce a failure for the `reverseInPlace` method is shown in the code block above.

```
@Test
public void testReverseInPlace2(){
  int[] input1 = {1, 2, 3, 4, 5};
  ArrayExamples.reverseInPlace(input1);
  assertArrayEquals(new int[]{5, 4, 3, 2, 1}, input1);
}
```
* The failure-inducing input for `reverseInPlace` method is shown in the code block above.

![Image](W24_LR3_3.png)
* The symptom, as the output of running the tests, is shown in the screenshot above.

```
static void reverseInPlace(int[] arr) {
  for(int i = 0; i < arr.length; i += 1) {
    arr[i] = arr[arr.length - i - 1];
  }
}
```
* The code block above shows the buggy method before the code change.

```
static void reverseInPlace(int[] arr) {
  int[] temp = new int[arr.length];
  for(int x = 0; x < arr.length; i += 1) {
    temp[x] = arr[x];
  for(int i = 0; i < temp.length; i += 1) {
    arr[i] = temp[temp.length - i - 1];
  }
}
```
* The code block above shows the buggy method after the code change. When running the tests with this updated method, all of the tests pass and there are no failures.
* The previous issue with the code (before the code change) was that since the input and output both used the same array, the values would be overwritten. This causes the second half of the array to be incorrect. By making a temporary array to store the original array, the original values are not overwritten and the issue is fixed.

# Part 2

`grep -r`

```grep -r ".txt" technical/biomed```

```grep -r ".txt" technical/911report```

`grep -n`

`grep -i`

`grep -E`

# Citations
![Image](W24_LR3_4.png)
