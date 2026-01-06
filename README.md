# 30-essential-Data-Structures-and-Algorithms-problems-solved-in-C
his repository contains 30 essential Data Structures and Algorithms problems implemented in the C programming language. It is intended for practice, concept revision, and technical interview preparation, with simple problem names and clean, easy-to-understand solutions suitable for students and beginners.
1. Reverse Array
   
        void reverseArray(int arr[], int n) {
        int l = 0, r = n - 1, temp;
        while (l < r) {
        temp = arr[l];
        arr[l] = arr[r];
        arr[r] = temp;
        l++; r--;
        }
    }    

2. Find Maximum
   
        int findMax(int arr[], int n) {
            int max = arr[0];
            for (int i = 1; i < n; i++)
                if (arr[i] > max) max = arr[i];
            return max;
        }

3. Linear Search
   
       int linearSearch(int arr[], int n, int key) {
        for (int i = 0; i < n; i++)
            if (arr[i] == key) return i;
        return -1;
        }

4. Binary Search

        int binarySearch(int arr[], int n, int key) {
            int l = 0, r = n - 1;
            while (l <= r) {
            int mid = (l + r) / 2;
            if (arr[mid] == key) return mid;
            else if (arr[mid] < key) l = mid + 1;
            else r = mid - 1;
        }
            return -1;
        }    

5. Palindrome String

        int isPalindrome(char s[]) {
            int l = 0, r = strlen(s) - 1;
            while (l < r) {
            if (s[l] != s[r]) return 0;
                l++; r--;
                }
            return 1;
        }

6. Factorial
    
        int factorial(int n) {
            if (n <= 1) return 1;
            return n * factorial(n - 1);
        }

7. Fibonacci

        int fibonacci(int n) {
            int a = 0, b = 1, c;
         if (n == 0) return 0;
            for (int i = 2; i <= n; i++) {
            c = a + b;
            a = b;
            b = c;
        }
            return b;
        }

8. Prime Check


        int isPrime(int n) {
            if (n <= 1) return 0;
            for (int i = 2; i * i <= n; i++)
                if (n % i == 0) return 0;
            return 1;
        }

9. Count Digits

        int countDigits(int n) {
            int c = 0;
            while (n) {
                c++; n /= 10;
            }
            return c;
        }
        
10. Sum of Digits
        
        int sumDigits(int n) {
            int s = 0;
            while (n) {
                s += n % 10;
                n /= 10;
            }
            return s;
        }
        
11. GCD

        int gcd(int a, int b) {
            if (b == 0) return a;
            return gcd(b, a % b);
        }

12. Remove Duplicates
        
        int removeDuplicates(int arr[], int n) {
            int j = 0;
            for (int i = 1; i < n; i++)
                if (arr[i] != arr[j])
                    arr[++j] = arr[i];
            return j + 1;
        }
        
13. Bubble Sort
        
        void bubbleSort(int arr[], int n) {
            int temp;
            for (int i = 0; i < n - 1; i++)
                for (int j = 0; j < n - i - 1; j++)
                    if (arr[j] > arr[j + 1]) {
                        temp = arr[j];
                        arr[j] = arr[j + 1];
                        arr[j + 1] = temp;
                    }
        }
        
14. Selection Sort
        
        void selectionSort(int arr[], int n) {
            int min, temp;
            for (int i = 0; i < n; i++) {
                min = i;
                for (int j = i + 1; j < n; j++)
                    if (arr[j] < arr[min]) min = j;
                temp = arr[i];
                arr[i] = arr[min];
                arr[min] = temp;
            }
        }

15. Insertion Sort

        void insertionSort(int arr[], int n) {
            for (int i = 1; i < n; i++) {
                int key = arr[i], j = i - 1;
                while (j >= 0 && arr[j] > key) {
                    arr[j + 1] = arr[j];
                    j--;
                }
                arr[j + 1] = key;
            }
        }

60. Sorted Array Check

        int isSorted(int arr[], int n) {
            for (int i = 1; i < n; i++)
                if (arr[i] < arr[i - 1]) return 0;
            return 1;
        }

17. Power of Two

        int isPowerOfTwo(int n) {
            return n > 0 && (n & (n - 1)) == 0;
        }

18. Count Set Bits

        int countSetBits(int n) {
            int c = 0;
            while (n) {
            c += n & 1;
            n >>= 1;
            }
            return c;
        }

19. Maximum Subarray

        int maxSubArray(int arr[], int n) {
            int max = arr[0], cur = arr[0];
            for (int i = 1; i < n; i++) {
            cur = (cur + arr[i] > arr[i]) ? cur + arr[i] : arr[i];
            if (cur > max) max = cur;
            }
            return max;
        }

20. Longest Subarray with Given Sum (Positive Numbers)

        int longestSubarray(int arr[], int n, int k) {
        int sum = 0, maxLen = 0;
        int start = 0;

        for (int end = 0; end < n; end++) {
        sum += arr[end];

        while (sum > k && start <= end) {
            sum -= arr[start];
            start++;
        }

        if (sum == k) {
            int len = end - start + 1;
            if (len > maxLen)
                maxLen = len;
        }
        }
            return maxLen;
        }
21. Missing Number
    
        int missingNumber(int arr[], int n) {
            int sum = n * (n + 1) / 2;
            for (int i = 0; i < n - 1; i++)
                sum -= arr[i];
            return sum;
        }

22. Reverse Linked List

        struct Node {
            int data;
            struct Node* next;
        };
        
        struct Node* reverseList(struct Node* head) {
            struct Node *prev = NULL, *cur = head, *next;
            while (cur) {
                next = cur->next;
                cur->next = prev;
                prev = cur;
                cur = next;
            }
            return prev;
        }

23. Linked List Length

        int length(struct Node* head) {
        int c = 0;
        while (head) {
        c++;
            head = head->next;
        }
        return c;
        }

24. Stack Push

            int stack[100], top = -1;
            void push(int x) {
                stack[++top] = x;
            }

25. Stack Pop
    
        void pop() {
            if (top >= 0) top--;
        }

26. Queue Enqueue
    
        int q[100], front = 0, rear = 0;
        void enqueue(int x) {
            q[rear++] = x;
        }

27. Queue Dequeue
        
        void dequeue() {
            front++;
        }

28. Left Rotate Array

        void rotateLeft(int arr[], int n) {
            int temp = arr[0];
            for (int i = 0; i < n - 1; i++)
                arr[i] = arr[i + 1];
            arr[n - 1] = temp;
        }

29. Merge Sorted Arrays

        void merge(int a[], int b[], int n, int m, int res[]) {
            int i = 0, j = 0, k = 0;
            while (i < n && j < m)
                res[k++] = (a[i] < b[j]) ? a[i++] : b[j++];
            while (i < n) res[k++] = a[i++];
            while (j < m) res[k++] = b[j++];
        }

30. Balanced Parentheses

        int isBalanced(char s[]) {
        char st[100];
        int top = -1;
        for (int i = 0; s[i]; i++) {
            if (s[i] == '(') st[++top] = '(';
            else {
                if (top == -1) return 0;
                top--;
        }
            }
            return top == -1;
        }

