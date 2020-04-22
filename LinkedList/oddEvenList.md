## question

给定一个单链表，把所有的奇数节点和偶数节点分别排在一起。请注意，这里的奇数节点和偶数节点指的是节点编号的奇偶性，而不是节点的值的奇偶性。

请尝试使用原地算法完成。你的算法的空间复杂度应为 O(1)，时间复杂度应为 O(nodes)，nodes 为节点总数。


## code


class Solution:
    def oddEvenList(self, head: ListNode) -> ListNode:
        if not head:
            return head
        o = head
        e = head.next
        p = e
        while o.next and e.next:
            o.next = e.next
            o = e.next
            e.next = o.next
            e = o.next
        
        o.next = p
        
        return head
## analysis
    out_row,out_col = int(np.floor(in_row/poolStride)),int(np.floor(in_col/poolStride))
    row_remainder,col_remainder = np.mod(in_row,poolStride),np.mod(in_col,poolStride)
    if row_remainder != 0:
        out_row +=1
    if col_remainder != 0:
        out_col +=1
    outputMap = np.zeros((out_row,out_col))
    
    # padding
    temp_map = np.lib.pad(inputMap, ((0,poolSize-row_remainder),(0,poolSize-col_remainder)), 'edge')
    
    # max pooling
    for r_idx in range(0,out_row):
        for c_idx in range(0,out_col):
            startX = c_idx * poolStride
            startY = r_idx * poolStride
            poolField = temp_map[startY:startY + poolSize, startX:startX + poolSize]
            poolOut = np.max(poolField)
            outputMap[r_idx,c_idx] = poolOut
    
    # retrun outputMap
    return  outputMap
    
    Y = (X - running_mean) / sqrt(running_var + eps) * gamma + beta
