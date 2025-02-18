````


11. Palindrome or Not(Digit)12.  Happy Number
13. Pyramid Pattern
14. Double Right Arrow(Butterfly Pattern)
15.Hollow Square Pattern
16.  Second Largest Element in the Array
17. Majority Element
18. Sum of Right side elements
19. Left Rotation
20. Swap those position values in the array
21. Remove Duplicates
22.Kth Largest element in the array
23. Monotonic Array
24. Array Odd Even Seggregation
25. SLL reverse()
26. DLL Search_Delete()
27. SLL sort_unsorted()
28. DLL Palindrome
29. DLL SortedInsert()
30. SLL reverse()
31.Stock Buy and Sell – Max one Transaction Allowed
32.Remove All Occurrences of an Element in an Array
33.Remove duplicates from Sorted Array
34.Minimum Swaps required to group all 1’s together
35.Implement two Stacks in an Array                                                                                                                                36. How to efficiently implement k stacks in a single array?
37.Implement Stack using Queues
38.Inverted Right-Angle Triangle Pattern
39.Pyramid Pattern
40.Array Right Rotation
````

### 1.Perfect,Abudant, Deficient Number

In Java, Perfect, Abundant, and Deficient Numbers are classified based on the sum of their proper divisors:
Perfect Number: The sum of its proper divisors is equal to the number itself.
Example: 6 → (1 + 2 + 3 = 6)
Abundant Number: The sum of its proper divisors is greater than the number.
Example: 12 → (1 + 2 + 3 + 4 + 6 = 16 > 12)
Deficient Number: The sum of its proper divisors is less than the number.
Example: 8 → (1 + 2 + 4 = 7 < 8)

````java[]
import java.util.*;
public class Main
{
	public static void main(String[] args) {
	    Scanner s=new Scanner(System.in);
	    int n=s.nextInt();
	    int sum=0;
	    for(int i=1;i<n;i++){
	        if(n%i==0){
	        sum+=i;
	    }
	    }
	    if(sum==n){
		System.out.println("PERFECT");
	}
	else if(sum>n){
	    System.out.println("ABUNDANT");
	}
	else{
	System.out.println("DEFICIENT");
}
}
}
````

### 2. GCD, LCM


````java[]
import java.util.*;
public class Main
{
	public static void main(String[] args) {
	    Scanner s=new Scanner(System.in);
	    int n1=s.nextInt();
	    int n2=s.nextInt();
	    int a=n1;
	    int b=n2;
	    while(n1!=n2){
	        if(n1>n2){
	            n1-=n2;
	        }
	        else{
	            n2-=n1;
	        }
	    }
	  int gcd=n1;
	  System.out.println(gcd);
	    int lcm=(a*b)/gcd;
	    System.out.println(lcm);
}
}

````java[]
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        int n1 = s.nextInt();
        int n2 = s.nextInt();
        s.close();
        
        int a = n1, b = n2; // Store original values for LCM calculation

        // Find GCD using Euclidean Algorithm (Modulo Method)
        while (n2 != 0) {
            int temp = n2;
            n2 = n1 % n2;
            n1 = temp;
        }

        int gcd = n1; // GCD is stored in n1 after loop ends
        int lcm = (a * b) / gcd; // Correct formula for LCM

        System.out.println("GCD: " + gcd);
        System.out.println("LCM: " + lcm);
    }
}
````

### 3.Ampicable Pair


What is an Amicable Pair?
Two numbers (a, b) are called amicable numbers if the sum of proper divisors of a equals b, and the sum of proper divisors of b equals a.

````java[]
import java.util.*;
public class Main
{
    public static int SumofDiv(int n){
        int sum=0;
        for(int i=1;i<n;i++){
            if(n%i==0){
                sum+=i;
            }
        }
            return sum;
        
    }
	public static void main(String[] args) {
	    Scanner s=new Scanner(System.in);
	    int n1=s.nextInt();
	    int n2=s.nextInt();
	    
	    int sum1=SumofDiv(n1);
	    int sum2=SumofDiv(n2);
	    
	    if(sum1==n2 && sum2==n1){
	        System.out.println("Amicable Pair");
	    }
	    else{
	        System.out.println("Not Amicable Pair");
	    }
	   
	
}
}

````

### 4. Betrothed Pair
What is a Betrothed Pair?
Two numbers (a, b) are called a betrothed pair if:
sum of proper divisors of a=b+1
sum of proper divisors of b=a+1

````java[]
import java.util.*;
public class Main
{
    public static int SumofDiv(int n){
        int sum=0;
        for(int i=1;i<n;i++){
            if(n%i==0){
                sum+=i;
            }
        }
            return sum;
        
    }
	public static void main(String[] args) {
	    Scanner s=new Scanner(System.in);
	    int n1=s.nextInt();
	    int n2=s.nextInt();
	    
	    int sum1=SumofDiv(n1);
	    int sum2=SumofDiv(n2);
	    
	    if(sum1==n2+1 && sum2==n1+1){
	        System.out.println("Betrothed Pair");
	    }
	    else{
	        System.out.println("Not Betrothed Pair");
	    }
	   
	
}
}

### 5. Square-Free Number


````java[]
import java.util.Scanner;

public class Main {
    public static boolean isSquareFree(int num) {
        for (int i = 2; i * i <= num; i++) {
            if (num % (i * i) == 0) { // Checking for square factor
                return false;
            }
        }
        return true;
    }

    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        int n = s.nextInt();
        s.close();

        if (isSquareFree(n)) {
            System.out.println("Square free number");
        } else {
            System.out.println("Not a square free number");
        }
    }
}

````

### 6. Ugly Number

```java[]
import java.util.Scanner;

public class Main {
    static boolean isUgly(int n) {
        if (n <= 0) return false;
        while (n % 2 == 0) n /= 2;
        while (n % 3 == 0) n /= 3;
        while (n % 5 == 0) n /= 5;
        return n == 1;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        System.out.println(isUgly(n) ? "Ugly Number" : "Not an Ugly Number");
        sc.close();
    }
}
```


### 7. Kaprekar Number  

```java[]
import java.util.Scanner;

public class Main {
    static boolean isKaprekar(int n) {
        if (n == 1) return true;
        int sq = n * n, temp = n, d = 0;
        while (temp > 0) {
            d++;
            temp /= 10;
        }
        int div = (int) Math.pow(10, d);
        int left = sq / div, right = sq % div;
        return left + right == n;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        System.out.println(isKaprekar(n) ? "Kaprekar Number" : "Not a Kaprekar Number");
        sc.close();
    }
}
```



### 8. Armstrong Number 

```java[]
import java.util.Scanner;

public class Main {
    static boolean isArmstrong(int n) {
        int sum = 0, temp = n, digits = (int) Math.log10(n) + 1;
        while (temp > 0) {
            sum += Math.pow(temp % 10, digits);
            temp /= 10;
        }
        return sum == n;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        System.out.println(isArmstrong(n) ? "Armstrong Number" : "Not an Armstrong Number");
        sc.close();
    }
}
```



### 9. Adam Number  

```java[]
import java.util.Scanner;

public class Main {
    static int reverse(int n) {
        int rev = 0;
        while (n > 0) {
            rev = rev * 10 + n % 10;
            n /= 10;
        }
        return rev;
    }

    static boolean isAdam(int n) {
        int sq1 = n * n;
        int sq2 = reverse(n) * reverse(n);
        return sq1 == reverse(sq2);
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        System.out.println(isAdam(n) ? "Adam Number" : "Not an Adam Number");
        sc.close();
    }
}
```



### 10. Digit Odd-Even Segregate 

```java[]
import java.util.Scanner;

public class Main {
    static void segregateOddEvenDigits(int n) {
        StringBuilder odd = new StringBuilder();
        StringBuilder even = new StringBuilder();
        
        while (n > 0) {
            int digit = n % 10;
            if (digit % 2 == 0) even.insert(0, digit);
            else odd.insert(0, digit);
            n /= 10;
        }
        
        System.out.println("Even Digits: " + even);
        System.out.println("Odd Digits: " + odd);
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        segregateOddEvenDigits(n);
        sc.close();
    }
}
```

11. Palindrome or Not (Digit)

````java[]
import java.util.Scanner;

public class Main {
    static boolean isPalindrome(int n) {
        int rev = 0, temp = n;
        while (temp > 0) {
            rev = rev * 10 + temp % 10;
            temp /= 10;
        }
        return rev == n;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        System.out.println(isPalindrome(n) ? "Palindrome" : "Not a Palindrome");
        sc.close();
    }
}

````
### 12. Happy Number

````java[]
import java.util.Scanner;

public class Main {
    static int sumOfSquares(int n) {
        int sum = 0;
        while (n > 0) {
            int digit = n % 10;
            sum += digit * digit;
            n /= 10;
        }
        return sum;
    }

    static boolean isHappy(int n) {
        int slow = n, fast = n;
        do {
            slow = sumOfSquares(slow);
            fast = sumOfSquares(sumOfSquares(fast));
        } while (slow != fast && fast != 1);
        return fast == 1;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        System.out.println(isHappy(n) ? "Happy Number" : "Not a Happy Number");
        sc.close();
    }
}

````
### 13. Pyramid Pattern

````java[]
import java.util.Scanner;

public class Main {
    static void printPyramid(int n) {
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= n - i; j++) System.out.print(" ");
            for (int j = 1; j <= 2 * i - 1; j++) System.out.print("*");
            System.out.println();
        }
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        printPyramid(n);
        sc.close();
    }
}
````

## 14. Double Right Arrow (Butterfly Pattern)

``````java[]

import java.util.Scanner;

public class Main {
    static void printButterfly(int n) {
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= i; j++) System.out.print("*");
            for (int j = 1; j <= 2 * (n - i); j++) System.out.print(" ");
            for (int j = 1; j <= i; j++) System.out.print("*");
            System.out.println();
        }
        for (int i = n; i >= 1; i--) {
            for (int j = 1; j <= i; j++) System.out.print("*");
            for (int j = 1; j <= 2 * (n - i); j++) System.out.print(" ");
            for (int j = 1; j <= i; j++) System.out.print("*");
            System.out.println();
        }
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        printButterfly(n);
        sc.close();
    }
}

``````

### 18. Sum of Right Side Elements
Find sum of all elements to the right of each index.

```java[]
public class RightSideSum {
    public static int sumRight(int[] arr, int index) {
        int sum = 0;
        for (int i = index + 1; i < arr.length; i++) {
            sum += arr[i];
        }
        return sum;
    }

    public static void main(String[] args) {
        int[] arr = {4, 2, 1, 6, 3};
        System.out.println(sumRight(arr, 1)); // Output: 10
    }
}
```

---

### 19. Left Rotation

```java[]
import java.util.Arrays;

public class LeftRotate {
    public static void leftRotate(int[] arr, int d) {
        int n = arr.length;
        d = d % n; // Handle d > n
        int[] temp = new int[d];

        System.arraycopy(arr, 0, temp, 0, d);
        System.arraycopy(arr, d, arr, 0, n - d);
        System.arraycopy(temp, 0, arr, n - d, d);
    }

    public static void main(String[] args) {
        int[] arr = {1, 2, 3, 4, 5};
        leftRotate(arr, 2);
        System.out.println(Arrays.toString(arr)); // Output: [3, 4, 5, 1, 2]
    }
}
```


### 20. Swap Two Positions in Array
```java[]
import java.util.Arrays;

public class SwapPositions {
    public static void swap(int[] arr, int i, int j) {
        int temp = arr[i];
        arr[i] = arr[j];
        arr[j] = temp;
    }

    public static void main(String[] args) {
        int[] arr = {10, 20, 30, 40};
        swap(arr, 1, 3);
        System.out.println(Arrays.toString(arr)); // Output: [10, 40, 30, 20]
    }
}
```



### 21. Remove Duplicates from Unsorted Array

```java[]
import java.util.HashSet;
import java.util.Arrays;

public class RemoveDuplicates {
    public static int[] removeDuplicates(int[] arr) {
        HashSet<Integer> set = new HashSet<>();
        int index = 0;
        for (int num : arr) {
            if (set.add(num)) {
                arr[index++] = num;
            }
        }
        return Arrays.copyOf(arr, index);
    }

    public static void main(String[] args) {
        int[] arr = {1, 2, 3, 1, 4, 2, 5};
        System.out.println(Arrays.toString(removeDuplicates(arr))); // Output: [1, 2, 3, 4, 5]
    }
}
```


### 22. Kth Largest Element[]
Using a Min Heap (Priority Queue)

```java
import java.util.PriorityQueue;

public class KthLargest {
    public static int findKthLargest(int[] arr, int k) {
        PriorityQueue<Integer> minHeap = new PriorityQueue<>();
        for (int num : arr) {
            minHeap.add(num);
            if (minHeap.size() > k) {
                minHeap.poll();
            }
        }
        return minHeap.poll();
    }

    public static void main(String[] args) {
        int[] arr = {3, 2, 1, 5, 6, 4};
        System.out.println(findKthLargest(arr, 2)); // Output: 5
    }
}
```

### 23. Monotonic Array

```java[]
public class MonotonicArray {
    public static boolean isMonotonic(int[] arr) {
        boolean increasing = true, decreasing = true;
        for (int i = 1; i < arr.length; i++) {
            if (arr[i] > arr[i - 1]) decreasing = false;
            if (arr[i] < arr[i - 1]) increasing = false;
        }
        return increasing || decreasing;
    }

    public static void main(String[] args) {
        int[] arr = {1, 2, 2, 3};
        System.out.println(isMonotonic(arr)); // Output: true
    }
}
```


### 24. Odd-Even Segregation

```java[]
import java.util.Arrays;

public class OddEvenSegregation {
    public static void segregateOddEven(int[] arr) {
        int left = 0, right = arr.length - 1;
        while (left < right) {
            while (arr[left] % 2 == 0 && left < right) left++;
            while (arr[right] % 2 == 1 && left < right) right--;
            if (left < right) {
                int temp = arr[left];
                arr[left] = arr[right];
                arr[right] = temp;
            }
        }
    }

    public static void main(String[] args) {
        int[] arr = {12, 34, 45, 9, 8, 90, 3};
        segregateOddEven(arr);
        System.out.println(Arrays.toString(arr));
    }
}
```

### 25. Reverse Singly Linked List

```java[]
class ListNode {
    int data;
    ListNode next;
    ListNode(int data) { this.data = data; }
}

public class ReverseSLL {
    public static ListNode reverse(ListNode head) {
        ListNode prev = null, curr = head;
        while (curr != null) {
            ListNode nextNode = curr.next;
            curr.next = prev;
            prev = curr;
            curr = nextNode;
        }
        return prev;
    }
}
```


### 26. Search & Delete in Doubly Linked List

```java[]
class DNode {
    int data;
    DNode prev, next;
    DNode(int data) { this.data = data; }
}

public class DLLSearchDelete {
    public static DNode deleteNode(DNode head, int key) {
        DNode temp = head;
        while (temp != null && temp.data != key) temp = temp.next;
        if (temp == null) return head; // Key not found

        if (temp.prev != null) temp.prev.next = temp.next;
        if (temp.next != null) temp.next.prev = temp.prev;
        return (temp == head) ? temp.next : head;
    }
}
```


### 17. Majority Element

````java[]
class Solution {
    public int majorityElement(int[] nums) {
        Arrays.sort(nums);
        int n = nums.length;
        return nums[n/2];
    }}
````



### 27. Sort Unsorted Singly Linked List

Using **Merge Sort** for efficient sorting.

```java[]
class ListNode {
    int data;
    ListNode next;
    ListNode(int data) { this.data = data; }
}

public class SLLSort {
    public static ListNode mergeSort(ListNode head) {
        if (head == null || head.next == null) return head;

        ListNode mid = getMiddle(head);
        ListNode nextToMid = mid.next;
        mid.next = null;

        ListNode left = mergeSort(head);
        ListNode right = mergeSort(nextToMid);

        return merge(left, right);
    }

    private static ListNode getMiddle(ListNode head) {
        ListNode slow = head, fast = head;
        while (fast.next != null && fast.next.next != null) {
            slow = slow.next;
            fast = fast.next.next;
        }
        return slow;
    }

    private static ListNode merge(ListNode left, ListNode right) {
        if (left == null) return right;
        if (right == null) return left;

        if (left.data < right.data) {
            left.next = merge(left.next, right);
            return left;
        } else {
            right.next = merge(left, right.next);
            return right;
        }
    }
}
```


### 28. Check if Doubly Linked List is a Palindrome
```java[]
class DNode {
    int data;
    DNode prev, next;
    DNode(int data) { this.data = data; }
}

public class DLLPalindrome {
    public static boolean isPalindrome(DNode head) {
        if (head == null) return true;

        DNode left = head, right = head;
        while (right.next != null) right = right.next;

        while (left != right && left.prev != right) {
            if (left.data != right.data) return false;
            left = left.next;
            right = right.prev;
        }
        return true;
    }
}
```


### 29. Insert in Sorted Doubly Linked List
```java[]
public class DLLSortedInsert {
    public static DNode sortedInsert(DNode head, int data) {
        DNode newNode = new DNode(data);
        if (head == null) return newNode;

        if (data < head.data) {
            newNode.next = head;
            head.prev = newNode;
            return newNode;
        }

        DNode temp = head;
        while (temp.next != null && temp.next.data < data) temp = temp.next;

        newNode.next = temp.next;
        newNode.prev = temp;
        if (temp.next != null) temp.next.prev = newNode;
        temp.next = newNode;

        return head;
    }
}
```

### 30. Reverse Singly Linked List (Again)
(Same as Question 25)

---

### **31. Stock Buy and Sell – Max One Transaction Allowed**
```java
public class StockBuySell {
    public static int maxProfit(int[] prices) {
        int minPrice = Integer.MAX_VALUE, maxProfit = 0;
        for (int price : prices) {
            minPrice = Math.min(minPrice, price);
            maxProfit = Math.max(maxProfit, price - minPrice);
        }
        return maxProfit;
    }
}
```

### **32. Remove All Occurrences of an Element in an Array**

```java
import java.util.Arrays;

public class RemoveElement {
    public static int[] removeAllOccurrences(int[] arr, int value) {
        return Arrays.stream(arr).filter(num -> num != value).toArray();
    }
}
```


### 33. Remove Duplicates from Sorted Array

```java[]
public class RemoveSortedDuplicates {
    public static int removeDuplicates(int[] arr) {
        int j = 0;
        for (int i = 1; i < arr.length; i++)
            if (arr[i] != arr[j]) arr[++j] = arr[i];

        return j + 1;
    }
}
```



### 34. Minimum Swaps to Group All 1’s Together
```java[]
public class MinSwapsForOnes {
    public static int minSwaps(int[] arr) {
        int ones = 0, maxOnes = 0, swaps = 0;
        for (int num : arr) if (num == 1) ones++;

        for (int i = 0, countOnes = 0; i < arr.length; i++) {
            if (i >= ones && arr[i - ones] == 1) countOnes--;
            if (arr[i] == 1) countOnes++;
            maxOnes = Math.max(maxOnes, countOnes);
        }
        return ones - maxOnes;
    }
}
```


### 35. Implement Two Stacks in an Array
```java[]
class TwoStacks {
    int[] arr;
    int top1, top2, size;

    TwoStacks(int n) {
        size = n;
        arr = new int[n];
        top1 = -1;
        top2 = n;
    }

    void push1(int val) {
        if (top1 < top2 - 1) arr[++top1] = val;
    }

    void push2(int val) {
        if (top1 < top2 - 1) arr[--top2] = val;
    }

    int pop1() { return (top1 >= 0) ? arr[top1--] : -1; }

    int pop2() { return (top2 < size) ? arr[top2++] : -1; }
}
```



### 36. Implement k Stacks in a Single Array
```java[]
class KStacks {
    int[] arr, top, next;
    int freeTop, k;

    KStacks(int k, int n) {
        this.k = k;
        arr = new int[n];
        top = new int[k];
        next = new int[n];
        freeTop = 0;
        for (int i = 0; i < k; i++) top[i] = -1;
        for (int i = 0; i < n - 1; i++) next[i] = i + 1;
        next[n - 1] = -1;
    }

    void push(int stackNum, int val) {
        if (freeTop == -1) return;
        int index = freeTop;
        freeTop = next[index];
        arr[index] = val;
        next[index] = top[stackNum];
        top[stackNum] = index;
    }

    int pop(int stackNum) {
        if (top[stackNum] == -1) return -1;
        int index = top[stackNum];
        top[stackNum] = next[index];
        next[index] = freeTop;
        freeTop = index;
        return arr[index];
    }
}
```


### 37. Implement Stack using Queues
```java[]
import java.util.LinkedList;
import java.util.Queue;

class StackUsingQueue {
    Queue<Integer> q = new LinkedList<>();

    void push(int val) {
        q.add(val);
        for (int i = 0; i < q.size() - 1; i++)
            q.add(q.remove());
    }

    int pop() { return q.isEmpty() ? -1 : q.remove(); }
}
```

### 38. Inverted Right-Angle Triangle Pattern
```java[]
public class InvertedTriangle {
    public static void printPattern(int n) {
        for (int i = n; i > 0; i--) {
            for (int j = 0; j < i; j++) System.out.print("* ");
            System.out.println();
        }
    }
}
```

### 39. Pyramid Pattern
```java
public class PyramidPattern {
    public static void printPyramid(int n) {
        for (int i = 1; i <= n; i++) {
            for (int j = 0; j < n - i; j++) System.out.print(" ");
            for (int j = 0; j < 2 * i - 1; j++) System.out.print("*");
            System.out.println();
        }
    }
}
```


### 40. Right Rotation of an Array
```java[]
import java.util.Arrays;

public class RightRotate {
    public static void rightRotate(int[] arr, int d) {
        int n = arr.length;
        d = d % n;
        reverse(arr, 0, n - 1);
        reverse(arr, 0, d - 1);
        reverse(arr, d, n - 1);
    }

    private static void reverse(int[] arr, int left, int right) {
        while (left < right) {
            int temp = arr[left];
            arr[left++] = arr[right];
            arr[right--] = temp;
        }
    }
}
```


