#LeetCode

从easy开始，分类刷算法题，暂定每天两道。。有待删减qwq

##notes

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
#定义链表
class Listnode(object):
  def __init__(self):
    self.val = None
    self.next = None
#操作链表
class ListNode_handle:
    def __init__(self):
        self.cur_node = None
    def add(self,data):
        #add a new node pointed to previous node
        node = ListNode()
        node.val = data
        node.next = self.cur_node
        self.cur_node = node
        return node
    def _reverse(self,nodelist):
        list = []
        while nodelist:
            list.append(nodelist.val)
            nodelist = nodelist.next
        result = Listnode()
        result_handle = ListNode_handle()
        for i in list:
            result = result_handle.append(i)
        return result
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

#quicksort
def quicksort(nums):
	for i in range(len(nums)):
		for j in range(i+1,len(nums)):
			if nums[j] < nums[i]:
				nums[i],nums[j] = nums[j],nums[i]
	return nums
```
