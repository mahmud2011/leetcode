**Query 1:** return indices or numbers (- sort possible)?

**Query 2:** exactly one solution?

**Query 3:** sorted (- two pointer)?

**Query 4:** minimum input size?

**Query 5:** integer range?

### Solution 1
**Complexity:** O(n^2), O(1)

```kotlin
class Solution {
    fun twoSum(nums: IntArray, target: Int): IntArray {
        for (i in 0 until nums.size - 1) {
            for (j in i+1 until nums.size) {
                if (nums[i] + nums[j] == target) {
                    return intArrayOf(i, j)
                }
            }
        }

        return IntArray(2)
    }
}
```

### Solution 2
**Complexity:** O(n), O(n)

```kotlin
class Solution {
    fun twoSum(nums: IntArray, target: Int): IntArray {
        val cache = HashMap<Int, Int>()

        for (i in nums.indices) {
            val diff = target - nums[i]
            if (diff in cache) {
                return intArrayOf(cache[diff]!!, i)
            }

            cache[nums[i]] = i
        }

        return intArrayOf()
    }
}
```
