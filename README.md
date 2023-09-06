Consecutive Subsequences hackerrank


Jigar got a sequence of n positive integers as his birthday present! He likes consecutive subsequences whose sum is divisible by k. He asks you to write a program to count them for him.

Input Format
The first line contains T, the number of testcases.
T testcases follow. Each testcase consists of 2 lines.
The first line contains n and k separated by a single space.
And the second line contains n space separated integers.

Output Format
For each test case, output the number of consecutive subsequenences whose sum is divisible by k in a newline.

Constraints
1 ≤ T ≤ 20
1 ≤ n ≤ 106
1 ≤ k ≤ 100
1 ≤ a[i] ≤ 104

Sample Input

2
5 3
1 2 3 4 1
6 2
1 2 1 2 1 2
Sample Output

4
9
Explanation

For

1 2 3 4 1
there exists, 4 subsequences whose sum is divisible by 3, they are

3
1 2
1 2 3
2 3 4
For

1 2 1 2 1 2
there exists, 9 subsequences whose sum is divisible by 2, they are

2
2
2
1 2 1
1 2 1
1 2 1 2
2 1 2 1
1 2 1 2
2 1 2 1 2

************************************************************
*************************************************
*****************************

for _ in range(int(input())):
    n,k=map(int,input().split())
    list1=list(map(int,input().split()))
    dict1={0:1}
    sum1,res=0,0
    for i in range(len(list1)):
        sum1+=list1[i]
        t=sum1%k
        if t in dict1:
            res+=dict1[t]
            dict1[t]+=1
        else:
            dict1[t]=1
    print(res)
