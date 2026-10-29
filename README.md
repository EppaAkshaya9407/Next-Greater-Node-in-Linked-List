# Next-Greater-Node-in-Linked-List
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def nextLargerNodes(self, head: ListNode | None) -> list[int]:
        r=[]
        temp=head
        while temp:
            r.append(temp.val)
            temp=temp.next
        n=len(r)
        a=[0]*n
        s=[]
        for i in range(n):
            while s and  r[i] > r[s[-1]]:
                    j = s.pop()
                    a[j] = r[i]
            s.append(i)
        return a
