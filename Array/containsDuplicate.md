# 存在重复元素
> 输入: [1,2,3,1], 输出: true
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
