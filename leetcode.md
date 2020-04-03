<details>
  <summary>1. 无重复字符的最长子串</summary>

  ```javascript
    /*
      思路: 首先声明三个参数，一个是无重复最长长度，一个是当前的子串，一个是最终的最长子串
      判断当前子串是否包含字母，如果不包含，将它拼接起来，并且判断长度是否大于之前判断的长度，如果大于，则说明有更长的子串形成，需要更新len和longestSubstring;如果包含了，说明当前元素和之前的元素有重复了，在这里我们找到重复元素第一次出现的索引，然后从它的后一位开始剪切这个字符串，将剪切后的字符串赋值给当前curSub，我这里如果你想要返回长度，就return len，如果你想要最长的无重复字符串，就return longestSubstring
      如：abca这个子串，第一个a和最后一个a重复了，我们用indexOf拿到第一个a出现的索引，向后推一位即第二位开始剪切这个字符串，则剪切之后的为bca，此时可以拿着这个子串继续循环看是否后面元素有重复的。
    */
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
<details>
  <summary>2. 最长公共前缀</summary>

  ```javascript
    /*
      思路: 以第1个值为标准, 逐位比较, 比较全部通过时res增加当前字符，不通过时直接返回res
    */
    /**
    * @param {string[]} strs
    * @return {string}
    */
    let longestCommonPrefix = function(strs) {
      let res = ''
      if (!strs.length) return res
      for (let j = 0; j < strs[0].length; j ++) { // 第j位
        for (let i = 0; i < strs.length; i ++) { // 第j个
          if (strs[i][j] !== strs[0][j]) {
            return res
          }

        }
        res += strs[0][j]
      }
      return res
    }
  ```
</details>
