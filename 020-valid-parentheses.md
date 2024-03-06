### Solution 1
**Complexity:** O(n), O(n)

```kotlin
class Solution {
    fun isValid(s: String): Boolean {
        val stack = ArrayDeque<Char>()

        for (i in s.indices) {
            if (s[i] in "({[") {
                stack.add(s[i])
            } else {
                if (stack.isEmpty() ||
                    s[i] == ')' && stack.last() != '(' ||
                    s[i] == '}' && stack.last() != '{' ||
                    s[i] == ']' && stack.last() != '[') {
                    return false
                }

                stack.removeLast()
            }
        }

        return stack.size == 0
    }
}
```
