<details>
  <summary>1. 无重复字符的最长子串?</summary>

  ```javascript
    /**
    * @param {string} s
    * @return {number}
    */
    var lengthOfLongestSubstring = function(s) {
        // 两个指针 A . B
        // A 负责移动遍历整个字符串。B始终指向最近那个重复的字符
        let tempMaxLength = 0;
        let left = 0;
        let right = 0
        const map = new Map();
        for (; right < s.length; right++ ) {
            if (map.has(s[right]) && map.get(s[right]) >= left ) {
                tempMaxLength = Math.max(right - left , tempMaxLength);
                left = map.get(s[right]) + 1;
            } 
            map.set(s[right],right);
        }
        tempMaxLength = Math.max(right - left , tempMaxLength);
        return tempMaxLength;
    }
  ```
</details>
