<details>
  <summary>1. 无重复字符的最长子串</summary>

  ```javascript
    /**
    * @param {string} s
    * @return {number}
    */
    let lengthOfLongestSubstring = s => {
      let len = 0 // 无重复最长子串长度
      let curSub = '' // 当前子串
      let longestSubstring = '' // 无重复最长子串
      for (let item of s) {
        if (curSub.includes(item)) {
          curSub += item
          curSub = curSub.slice(curSub.indexOf(item) + 1)
        } else {
          curSub += item
          if (curSub.length > len) {
            len = curSub.length
            longestSubstring = curSub
          }
        }
      }
      return len
    }
  ```
</details>
