# 一、字节跳动算法
前端工程师吃饭的家伙，深度、广度一样都不能差。

## 挑战字符串
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
<details>
  <summary>3. 字符串的排列</summary>

  ```javascript

  ```
</details>
<details>
  <summary>4. 字符串相乘</summary>

  ```javascript

  ```
</details>
<details>
  <summary>5. 反转字符串的单词</summary>

  ```javascript

  ```
</details>
<details>
  <summary>6. 简化路径</summary>

  ```javascript

  ```
</details>
<details>
  <summary>7. 复原IP地址</summary>

  ```javascript

  ```
</details>

## 数组与排序
<details>
  <summary>1. 三数之和</summary>

  ```javascript
    /**
    * @param {number[]} nums
    * @return {number[][]}
    */
    var threeSum = function(nums) {
      let res = []
      let repeatSet = new Set()
      for (let i = 0; i < nums.length - 2; i ++) {
        for (let j = i + 1; j < nums.length - 1; j ++) {
          for (let k = j + 1; k < nums.length; k ++) {
            if (nums[i] + nums[j] + nums[k] === 0) {
              let temp = [nums[i], nums[j], nums[k]]
              let tempSortStr = String(temp.sort())
              if (!repeatSet.has(tempSortStr)) {
                res.push(temp)
                repeatSet.add(tempSortStr)
              }
            }
          }
        }
      }
      return res
    }
  ```
</details>
<details>
  <summary>2. 岛屿的最大面积</summary>

  ```javascript

  ```
</details>
<details>
  <summary>3. 搜索旋转排序数组</summary>

  ```javascript

  ```
</details>
<details>
  <summary>4. 最长连续递增序列</summary>

  ```javascript

  ```
</details>
<details>
  <summary>5. 数组中的第K个最大元素</summary>

  ```javascript

  ```
</details>
<details>
  <summary>6. 最长连续序列</summary>

  ```javascript

  ```
</details>
<details>
  <summary>7. 第k个排序</summary>

  ```javascript

  ```
</details>
<details>
  <summary>8. 朋友圈</summary>

  ```javascript

  ```
</details>
<details>
  <summary>9. 合并区间</summary>

  ```javascript

  ```
</details>
<details>
  <summary>10. 接雨水</summary>

  ```javascript

  ```
</details>

## 链表与数
<details>
  <summary>1. 合并两个有序链表</summary>

  ```javascript

  ```
</details>
<details>
  <summary>2. 反转链表</summary>

  ```javascript

  ```
</details>
<details>
  <summary>3. 两数相加</summary>

  ```javascript

  ```
</details>
<details>
  <summary>4. 排序链表</summary>

  ```javascript

  ```
</details>
<details>
  <summary>5. 环形链表 II</summary>

  ```javascript

  ```
</details>
<details>
  <summary>6. 相交链表</summary>

  ```javascript

  ```
</details>
<details>
  <summary>7. 合并K个排序链表</summary>

  ```javascript

  ```
</details>
<details>
  <summary>8. 二叉树的最近公共祖先</summary>

  ```javascript

  ```
</details>
<details>
  <summary>9. 二叉树的锯齿形层次遍历</summary>

  ```javascript

  ```
</details>

## 动态或贪心
<details>
  <summary>1. 买卖股票的最佳时机</summary>

  ```javascript

  ```
</details>
<details>
  <summary>2. 买卖股票的最佳时机 II</summary>

  ```javascript

  ```
</details>
<details>
  <summary>3. 最大正方形</summary>

  ```javascript

  ```
</details>
<details>
  <summary>4. 最大子序和</summary>

  ```javascript

  ```
</details>
<details>
  <summary>5. 三角形最小路径和</summary>

  ```javascript

  ```
</details>
<details>
  <summary>6. 俄罗斯套娃信封问题</summary>

  ```javascript

  ```
</details>

## 数据结构
<details>
  <summary>1. 最小栈</summary>

  ```javascript

  ```
</details>
<details>
  <summary>2. LRU缓存机制</summary>

  ```javascript

  ```
</details>
<details>
  <summary>3. 全O(1)的数据结构</summary>

  ```javascript

  ```
</details>

## 拓展练习
<details>
  <summary>1. x 的平方根</summary>

  ```javascript

  ```
</details><details>
  <summary>2. UTF-8编码验证</summary>

  ```javascript

  ```
</details><details>
  <summary>3. 第二高的薪水</summary>

  ```javascript

  ```
</details>
