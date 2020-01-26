问题：
======
给定一个数组 nums，编写一个函数将所有 0 移动到数组的末尾，同时保持非零元素的相对顺序。<br>

示例:<br>

输入: [0,1,0,3,12]<br>
输出: [1,3,12,0,0]<br>

说明:<br>

    必须在原数组上操作，不能拷贝额外的数组。<br>
    尽量减少操作次数。<br>

思路：
======
先将非零数字移动到数组前面并记录其个数n，后将数组中第n个数之后的数字变为0.

解决：
=======
···
void moveZeroes(int* nums, int numsSize){
    int n = 0;
    for(int i = 0; i < numsSize; i++)
    {
        if(nums[i] != 0)
        {
            nums[n++] = nums[i];
        }
    }
    for(int i = n; i < numsSize; i++)
    {
        nums[i] = 0;
    }
}
···
