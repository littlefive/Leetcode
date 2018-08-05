# 存在重复元素
> 输入: [1,2,3,1], 输出: true； 2. 输入:[1,2,3,4], 输出：false 
#### 方法一
```javascript
/**
 * @param {number[]} nums
 * @return {boolean}
 */
 var containsDuplicate = function(nums) {
     var flag= false;
     for(var i=0; i<nums.length; i++){
         if(flag){break}
         for(var m=i+1;m<nums.length; m++){
             if(nums[i] == nums[m]) {
                 flag = true;
                 break;
             }
         }
     }
     return flag
 };
```
#### 方法二
> 新开辟了一个obj对象
```javascript
var containsDuplicate = function(nums) {
    var obj={};
    var flag = false;
    for(var i=0; i<nums.length; i++){
        if(!obj[nums[i]]){
            obj[nums[i]] = 1;
        } else {
            flag = true;
        }
        
    }
    return flag
};
```
#### 方法三
> 将数组去重，比较原数组的长度
``` javascript
var containsDuplicate = function(nums) {
    let arr = Array.from(new Set(nums));
    return nums.length > arr.length
};
```
