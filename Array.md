# <font color=#00ffff>(1)Two sum</font>: 在nums中找到两个相加起来等于target的数的位置。
在字典中查找是O(1)的，把每个数：位置存储为字典，碰到新的数字，只需要看diff在不在字典里，O(N)的存储和速度
用字典而不sort的原因：题目要求得到下标，sort后下标打乱
# (4) Median of Two Sorted Arrays:给定两个排好序的list， 找到中位数。
合并两个list，这一步通过对两个list分别设定一个指针实现。
对有序序列找中位数直接公式
但我觉得这个要对两个list都扫一遍，不知道为什么可以是O(log (m+n))的1
# (11) container-with-most-water: 给定{(i, a_i)}，找到(|j-i|)*min(a_j, a_i)最大的I和j。
不能用循环，超时。这道题考虑当选定一组i j时， 如果a_i<a_j，那么所有k<j的k, a_i, a_k组合都会< a_i, a_j组合。所以此时应把i坐标向右移，这样只需要遍历一遍。
# (15) 3Sum: 给定一个list，找出三个加起来为0的数，结果不重复。
最开始尝试了用循环，一个个遍历过去，然后设定target=-nums[i]，用两数相加等于target的方式得到nums[i]对应的其他两个数，用set去重。(其实也可以，就是慢一点点，但是leetcode的python3 对set支持不是很好）
有一个会超时的原因是：在做两数相加得到target这一步时，如果像第一题那样用字典存储元素及其对应下标的方法去做，没有利用sort的结果去做精简（sort之后可以设置i,j分别从左到右，和右到做夹逼出结果）
本题只要求得到元素没有要求得到下标，所以可以用sort
# (16) 3Sum Closest:给定一个list，找出三个加起来最接近target的和，输出这个和。
跟上一题差不多，保存tmp_sum这个变量，判断与target的差是否比原来更小
# (18) 4Sum: 给定一个list和target， 找出四个加起来等于target的数，结果list不重复。
类15题，加一个对于第二个数的循环
# (26) Remove Duplicates from Sorted Array:给出一个排好序的list，求不包含重复的list的长度
两个指针a,b从左到右，碰到重复的项b不动，a移动，最后得到b
# (27) Remove Element:给定一个排好序的list和一个target，给不不含这个target的list的长度
类似上一题
# (31) Next Permutation:给定一个list，找出下一个按照字典序的全排列
字典序：一个个位置比，小的放前面。
这一题对给定的序列，从后往前看，一个比一个大的话，就是最大的那个字典序，如果出现某个数比他后面的小，那他后面的就是字典倒序，从他开始往后找，找到第一个比他小的，跟她换位置，然后把后面这部分颠倒一下就可以了。
# (39)Combination Sum: 给定一个list和一个target，找出list中能加起来等于这个target的所有组合（允许重复）
用dfs
