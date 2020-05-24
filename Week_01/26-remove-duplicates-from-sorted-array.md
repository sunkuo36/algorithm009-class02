#题目：
给定一个排序数组，你需要在 原地 ~~删除重复出现的元素~~，使得每个元素只出现一次，返回移除后数组的新长度。

不要使用额外的数组空间，你必须在 原地 修改输入数组 并在使用 O(1) 额外空间的条件下完成。

>来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/remove-duplicates-from-sorted-array
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。

#解题思路
常见的双指针，主要注意：
* 1.有序数组
* 2.需要变更非重复元素到数组左侧
* 3.返回非重复元素个数
* 4.不适用额外数组空间

#解题(javascript)：
```javascript
/**
 * @param {number[]} nums
 * @return {number}
 */
var removeDuplicates = function(nums) {
    if(!nums||nums.length<1){
        return 0;
    }
    var i = 0;
    for(var j =1;j<nums.length;j++){
        if(nums[i]!=nums[j]){
            i++;
            nums[i] = nums[j];
        }
    }
    return i+1;
};
```
