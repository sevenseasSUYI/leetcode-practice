问题:
=====
给定一个由整数组成的非空数组所表示的非负整数，在该数的基础上加一。<br>
最高位数字存放在数组的首位， 数组中每个元素只存储单个数字。<br>
你可以假设除了整数 0 之外，这个整数不会以零开头。<br>
示例 1:<br>
输入: [1,2,3]<br>
输出: [1,2,4]<br>
解释: 输入数组表示数字 123。<br>
示例 2:<br>
输入: [4,3,2,1]<br>
输出: [4,3,2,2]<br>
解释: 输入数组表示数字 4321。<br>

思路:
======
数组最后一个数加一,判断该数是否>=10,如果是则进位.

解决:
======
```
   int* plusOne(int* digits, int digitsSize, int* returnSize){
        for(int i = digitsSize - 1; i >= 0; --i)
    {
        digits[i] = (digits[i] + 1) % 10;
        if(digits[i] != 0)   
        break;
    }
    *returnSize = digitsSize;
    if(digits[0] == 0)
    {
        int *result = (int*)malloc(sizeof(int)*(digitsSize+1));
        result[0] = 1;
        for(int j = 1; j < digitsSize + 1; ++j)
            result[j] = 0;
        *returnSize = digitsSize + 1;
        return result;
    }
    else
        return digits;
}
```
