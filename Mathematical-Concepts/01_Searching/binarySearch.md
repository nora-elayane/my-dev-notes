# Binary Search

> **Category:** Searching Algorithms  
> **Difficulty:** Intermediate  
> **Time Complexity:** O(log n)  
> **Space Complexity:** O(1)

## 1. Definition

**Binary Search** is a searching algorithm used to find an element in a **sorted array**.

Instead of checking every element, it divides the search area into two halves at each step.

It eliminates the half that cannot contain the target.

**Important:** The array must be sorted before using Binary Search.

## 2. How It Works

Binary Search uses three variables:

| Variable | Description  |
| -------- | ------------ |
| `start`  | First index  |
| `end`    | Last index   |
| `mid`    | Middle index |

The middle index is calculated using:

```java
int mid = start + (end - start) / 2;
```

There are three possible cases:

- If `array[mid] == target`: Element found.
- If `array[mid] < target`: Search the right half.
- If `array[mid] > target`: Search the left half.

## 3. Step-by-Step Example

We have the following sorted array:

```java
int[] numbers = {2, 5, 8, 12, 16, 23, 38};
int target = 16;
```

We want to find `16`.

**Step 1:**

```text
start = 0
end = 6
mid = (0 + 6) / 2 = 3

numbers[3] = 12
```

Since `16 > 12`, we search the right half.

```java
start = mid + 1;
```

**Step 2:**

```text
start = 4
end = 6
mid = (4 + 6) / 2 = 5

numbers[5] = 23
```

Since `16 < 23`, we search the left half.

```java
end = mid - 1;
```

**Step 3:**

```text
start = 4
end = 4
mid = (4 + 4) / 2 = 4

numbers[4] = 16
```

The target is found at index `4`.

### Execution Summary

| Step | Start | End | Mid | Value | Action |
| ---- | ----: | --: | --: | ----: | ------ |
| 1    |     0 |   6 |   3 |    12 | Right  |
| 2    |     4 |   6 |   5 |    23 | Left   |
| 3    |     4 |   4 |   4 |    16 | Found  |

## 4. Algorithm (Pseudocode)

```text
FUNCTION binarySearch(array, target)

    start = 0
    end = array.length - 1

    WHILE start <= end

        mid = (start + end) / 2

        IF array[mid] == target
            RETURN mid

        ELSE IF array[mid] < target
            start = mid + 1

        ELSE
            end = mid - 1

    RETURN -1
```

## 5. Java Implementation

```java
public static int binarySearch(int[] array, int target) {

    int start = 0;
    int end = array.length - 1;

    while (start <= end) {

        int mid = start + (end - start) / 2;

        if (array[mid] == target) {
            return mid;
        }
        else if (array[mid] < target) {
            start = mid + 1;
        }
        else {
            end = mid - 1;
        }
    }

    return -1;
}
```

**Example of use:**

```java
int[] numbers = {2, 5, 8, 12, 16, 23, 38};

int result = binarySearch(numbers, 16);

System.out.println(result);
```

Output:

```text
4
```

## 6. Understanding the Conditions

| Code              | Meaning                        |
| ----------------- | ------------------------------ |
| `start <= end`    | Continue while elements remain |
| `start = mid + 1` | Search the right half          |
| `end = mid - 1`   | Search the left half           |
| `return mid`      | Element found                  |
| `return -1`       | Element not found              |

**Why do we use `mid + 1` and `mid - 1`?**

Because we already checked the middle element. There is no need to check it again.

## 7. Time and Space Complexity

Binary Search removes half of the remaining elements at each step.

| Case             | Complexity |
| ---------------- | ---------- |
| Best Case        | O(1)       |
| Average Case     | O(log n)   |
| Worst Case       | O(log n)   |
| Space Complexity | O(1)       |

### Example

For an array of 1,000,000 elements, Binary Search needs approximately 20 comparisons in the worst case.

**Comparison with Linear Search:**

| Algorithm     | Time Complexity |
| ------------- | --------------- |
| Linear Search | O(n)            |
| Binary Search | O(log n)        |

## 8. Important Notes

- The array must be sorted.
- Binary Search returns the index, not the value.
- An empty array returns `-1`.
- If the element does not exist, the method returns `-1`.
- For duplicate values, standard Binary Search may return any matching index.
- The iterative implementation uses O(1) extra space.

## 9. Practice Exercises

**Exercise 1:** Find `25` in the following array:

```java
int[] numbers = {4, 9, 13, 18, 25, 31, 42};
```

**Exercise 2:** Search for `20`:

```java
int[] numbers = {3, 7, 11, 15, 19, 23, 27};
```

**Exercise 3:** Modify Binary Search to count the number of comparisons.

**Exercise 4:** Modify Binary Search to return the first occurrence of a duplicate value.

**Exercise 5:** Adapt Binary Search to work with a descending sorted array.

---

## 10. Key Takeaways

- Binary Search works on sorted arrays.
- It divides the search area into two halves.
- It uses `start`, `end`, and `mid`.
- It eliminates half of the remaining elements at each step.
- Its time complexity is O(log n).
- Its iterative space complexity is O(1).
