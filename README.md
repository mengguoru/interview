# interview
收集的一点笔试题、面试题。包括一些个人理解。附上源链接。原链接中高手的评论内容很有干货，让人看了收获颇大。他们给出的方案值得一读。我不能够望其项背。

# [滴滴出行2016研发工程师笔试题(亮灯问题)](http://group.jobbole.com/13805/)
1. 问题抽象：
    序号从1到N的N盏灯，一开始全部熄灭。把1的倍数的序号的灯全部按一遍，再把2的倍数的序号的灯全部按一遍...直到最后把N的倍数的序号偶的灯全部按一遍。问最后有多少亮的灯？
此问题中N为2015
2. 我的理解：求最后亮着的灯的数目，那么满足什么条件的灯会亮？当x的因数开始按灯时，x会被按下。所以一个灯最后亮着，它需要被按奇数次，只有平方数，如9的因数为1,3,9能符合。此题为44个
```python
import math

def is_square_number_N(n):
    temp = []
    for x in range(1,2015):
        if math.pow(int(math.sqrt(x)),2)==x:
            temp.append(x)
    return temp

print('in2015',is_square_number_N(2015))
print("in 2015:",len(is_square_number_N(2015)))
# or use lambda,since it is known to loop 1~the square number<2015
print('in 2015',[(lambda x:x*x)(x) for x in range(1,math.floor(math.sqrt(2015)+1))])
```
# [美团2012研发工程师笔试题(数数字问题)](http://group.jobbole.com/13802/)
答案：1~(10^k-1),其中(10^k-1)为k-1位数，0~9在每个数位出现概率一样，都是10^(k-1)。以1为例，由于是k-1位数，所以0~(10^k-1)范围内出现次数应该是k*(10^(k-1))次。又1~10000000，包括10000000，次数加1，为6*100000+1次
# [京东2016研发工程师笔试题](http://group.jobbole.com/13420/)
答案：目前没有计算量小的方案。但如果使用判断法，可以转化为二进制，判断最后两位是01 




