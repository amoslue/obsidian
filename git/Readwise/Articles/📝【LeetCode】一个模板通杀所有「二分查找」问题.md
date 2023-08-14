# 📝【LeetCode】一个模板通杀所有「二分查找」问题

![rw-book-cover](https://readwise-assets.s3.amazonaws.com/static/images/article4.6bc1851654a0.png)

## Metadata
- Author: [[Images。]]
- Full Title: 📝【LeetCode】一个模板通杀所有「二分查找」问题
- Category: #articles
- URL: https://imageslr.com/2020/03/15/binary-search.html#%E9%97%AE%E9%A2%98%E5%AE%9A%E4%B9%89

## Highlights
- left, right := 0, len(nums)-1 for left <= right ([View Highlight](https://read.readwise.io/read/01gzjzsk827pnk1ewt3d14gmmj))
- if nums[mid] >= target { // 这里的比较运算符与题目要求一致 right = mid - 1 } else { left = mid + 1 } ([View Highlight](https://read.readwise.io/read/01gzjzsgjma3gg8s2zn4kh5txn))
- 然后将下界的下标减一，就是我们要找的上界：
  // 查找满足 x ≤ target 的上界的下标
  func UpperBound(nums []int, target int) int {
  return LowerBound(nums, target)-1
  } ([View Highlight](https://read.readwise.io/read/01gzjzqar52j24m7cczwj1tqng))
- 查找指定值第一次出现的位置 ([View Highlight](https://read.readwise.io/read/01gzjzrqq1h62yd3598xytax74))
