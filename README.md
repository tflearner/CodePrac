# LeetCode

从easy开始，分类刷算法题，暂定每天两道。。有待删减qwq

## notes

```python
# map
map(function,iterable)
py2.x返回list
py2.x返回迭代器
#example
map(str,[1,2,3])
>['1','2','3']
```

```python
#python enumerate 遍历索引和元素
list1 = ["这", "是", "一个", "测试"]
for index, item in enumerate(list1):
    print index, item
>>>
0 这
1 是
2 一个
3 测试
```

```python
#python set 创建集合
a = set("boy")
b = sum(set([2,2,3,1]))-sum(set([2,2,3]))
print a
print b
>>>
set(['y', 'b', 'o'])
1
```

```python
#链表
#reverse
#定义链表
class Listnode(object):
  def __init__(self):
    self.val = None
    self.next = None
#操作链表
class ListNode(object):
    def __init__(self, x):
        self.val = x
        self.next = None

def isPalindrome(head):
        """
        :type head: ListNode
        :rtype: bool
        """
        tmp = None
        while head:
            n = ListNode(head.val)
            n.next = tmp
            tmp = n
            head = head.next
        return tmp

head=ListNode(1)
p1=ListNode(2)     
p2=ListNode(3)
p3=ListNode(4)
head.next=p1
p1.next=p2
p2.next=p3
p=isPalindrome(head);
while p:
    print p.val
    p = p.next
```

```python
#binary search
def bin_search(data_list, val):    
    low = 0                         # 最小数下标    
    high = len(data_list) - 1       # 最大数下标    
    while low <= high:        
        mid = (low + high) // 2     # 中间数下标        
        if data_list[mid] == val:   # 如果中间数下标等于val, 返回            
            return mid        
        elif data_list[mid] > val:  # 如果val在中间数左边, 移动high下标            
            high = mid - 1        
        else:                       # 如果val在中间数右边, 移动low下标            
            low = mid + 1    
    return
```

```python
#Sort

#bubblesort
def bubblesort(nums):
	for i in range(len(nums)):
		for j in range(len(nums)-i-1):
			if nums[j]>nums[j+1]:
				nums[j],nums[j+1]=nums[j+1],nums[j]
	return nums

#insert_sorts
def insert_sort(nums):
	for i in range(1,len(nums)):
		key = nums[i]
		j = i - 1
		while j >= 0:
			if nums[j] > key:
				nums[j+1] = nums[j]
				nums[j] = key
			j-=1
	return nums

def insert_sort(nums):
    for i in range(i,len(nums)):
        j=i
        while j>0 and nums[j-1]>nums[i]:
            j-=1
        nums.insert(j,nums[i])
        nums.pop(i+1)
       
#shell_sort 定义一个增量，每个分组做插入排序   
def shell_sort(nums):
	length = len(nums)
	inc = 0
	while inc <= length/3:
		inc = inc*3+1
	while inc >= 1:
		for i in range(inc,len(nums)):
			tmp = nums[i]
			for j in range(i,0,-inc):
				if tmp < nums[j-inc]:
					nums[j] = nums[j-inc]
				else:
					j+=inc
					break
			nums[j-inc] = tmp	
		inc //= 3
	return nums
```
