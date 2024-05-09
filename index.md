
1: A failure-inducing input for the buggy program, as a JUnit test and any associated code (write it as a code block in Markdown).

Buggy Program:
`  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }`
A failure-inducing input:
`	@Test 
	public void testReverseInPlace() {
    int[] input1 = { 1,2,3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3,2,1 }, input1);
	}`
An input that doesn't induce a failure:
` 	@Test 
	public void testReverseInPlace2() {
    int[] input1 = { 1, 1 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 1,1 }, input1);
	}`






`static void reverseInPlace(int[] arr) {
  int num = 0;
  for(int i = 0; i < arr.length/2; i += 1) {
    num = arr[i];
    arr[i] = arr[arr.length - i - 1];
    arr[arr.length - i - 1] = num;
  }
}`
