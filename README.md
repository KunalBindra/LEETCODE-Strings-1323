# LEETCODE-Strings-1323
We’ll take your example **num = 9996**.

---

### Code Recap:

```java
class Solution {
    public int maximum69Number (int num) {
        StringBuilder s1 = new StringBuilder(String.valueOf(num));
        for(int i = 0; i < s1.length(); i++) {
            if(s1.charAt(i) == '6') {
                s1.setCharAt(i, '9');
                break;
            }
        }
        return Integer.parseInt(s1.toString());
    }
}
```

---

### Dry Run with `num = 9996`

1. **Input:** `num = 9996`

2. Line 3:

   ```java
   StringBuilder s1 = new StringBuilder(String.valueOf(num));
   ```

   * `String.valueOf(num)` → `"9996"`
   * `s1 = "9996"`

3. Start the loop:

   ```java
   for (int i = 0; i < s1.length(); i++)
   ```

   * `s1.length()` = 4
   * i = 0 → `s1.charAt(0) = '9'` → not '6' → continue
   * i = 1 → `s1.charAt(1) = '9'` → not '6' → continue
   * i = 2 → `s1.charAt(2) = '9'` → not '6' → continue
   * i = 3 → `s1.charAt(3) = '6'` → condition true

4. Inside `if`:

   ```java
   s1.setCharAt(3, '9');
   break;
   ```

   * Changes `"9996"` → `"9999"`
   * `break` stops the loop immediately.

5. Exit loop.

6. Return:

   ```java
   return Integer.parseInt(s1.toString());
   ```

   * `s1.toString()` = `"9999"`
   * `Integer.parseInt("9999")` = `9999`

---

### ✅ Final Output:

```
9999
```

---

⚡ This code will **always flip the first 6 from the left into 9** and stop.
That’s why it guarantees the maximum number.
