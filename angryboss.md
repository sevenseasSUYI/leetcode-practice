问题：
======
今天，书店老板有一家店打算试营业 customers.length 分钟。每分钟都有一些顾客（customers[i]）会进入书店，所有这些顾客都会在那一分钟结束后离开。<br>

在某些时候，书店老板会生气。 如果书店老板在第 i 分钟生气，那么 grumpy[i] = 1，否则 grumpy[i] = 0。 当书店老板生气时，那一分钟的顾客就会不满意，不生气则他们是满意的。<br>

书店老板知道一个秘密技巧，能抑制自己的情绪，可以让自己连续 X 分钟不生气，但却只能使用一次。<br>

请你返回这一天营业下来，最多有多少客户能够感到满意的数量。<br>
 

示例：<br>

输入：customers = [1,0,1,2,1,1,7,5], grumpy = [0,1,0,1,0,1,0,1], X = 3<br>
输出：16<br>
解释：<br>
书店老板在最后 3 分钟保持冷静。<br>
感到满意的最大客户数量 = 1 + 1 + 1 + 1 + 7 + 5 = 16.<br>

 

提示：<br>

    1 <= X <= customers.length == grumpy.length <= 20000<br>
    0 <= customers[i] <= 1000<br>
    0 <= grumpy[i] <= 1<br>
    
思路：
======

解决：
======
```
int maxSatisfied(int* customers, int customersSize, int* grumpy, int grumpySize, int X){
    int sum = 0, temp, i, j;
	for(i = 0; i < customersSize; i++)
    {
		if(grumpy[i] == 0)
        sum+=customers[i];
	}
	temp = sum;
    int temp1 = sum;
	for(i = 0; i < (customersSize - X + 1); i++)
    {
        temp = temp1;
		for(j = 0; j < X; j++)
        {
			if(grumpy[i+j] == 1)
            temp+=customers[i+j];
		}
		if(sum < temp)
        sum = temp;
	}
	return sum;
}
```
