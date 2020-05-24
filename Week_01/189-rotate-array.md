#题目：
给定一个数组，将数组中的元素向右移动 k 个位置，其中 k 是非负数。

#解题思路
大概想到了如下几种方法：
1.暴力法，重复k次
2.下标法，需要额外数组


#解题
```javascript
//方法1 暴力法
/**
 * @param {number[]} nums
 * @param {number} k
 * @return {void} Do not return anything, modify nums in-place instead.
 */
var rotate = function(nums, k) {
    if(!nums||nums.length==1){
        return;
    }
    for(var i = 0;i<k;i++){
        var temp;
        for(var j=0;j<nums.length-1;j++){
            temp = nums[j+1]; 
            nums[j+1] = nums[j];
        }
        nums[0] = temp;
    }
};

//方法2 下标法
var rotate = function(nums, k) {
    if(!nums||nums.length==1){
        return;
    }
    var m = k%nums.length;
    if(m===0){
        return;
    }
    var result = [];
    for(var i=nums.length-m;i<nums.length;i++){
        result.push(nums[i]);
    }
    for(var j = 0;j<nums.length-m;j++){
        result.push(nums[j]);
    }
    for(var n=0;n<result.length;n++){
            nums[n] = result[n];
    }
};
```