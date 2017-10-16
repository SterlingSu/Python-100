# Python-100
100道Python编程题

#1：有1、2、3、4个数字，能组成多少个互不相同且无重复数字的三位数？都是多少？
```Python
m=0
for i in range(1,5):
    for j in range(1,5):
        for k in range(1,5):
            if(i!=j)and(i!=k)and(j!=k):
                m+=1
                print(i,j,k,m)
print("次数是m",format(m))
```
