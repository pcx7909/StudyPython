# StudyPython
def quick_sort(a, first, last):
    """***快速排序"""
    if first >= last:
        return

    mid_val = a[first]
    low = first
    high = last
    while low < high:
        # 判断两边数的大小，并控制游标移动
        while low < high and a[high] >= mid_val:
            high -= 1
        a[low] = a[high]
        while low < high and a[low] < mid_val:
            low += 1
        a[high] = a[low]
    a[low] = mid_val
    # 递归时传入位置，此位置不是最开始的位置
    quick_sort(a, first, low-1)
    quick_sort(a, low+1, last)


a_list = [24,26,93,17,99,21,44,55,20,19,19]
print(a_list)
# 传入初始的头部位置和尾部位置
quick_sort(a_list, 0, len(a_list)-1)
print(a_list)
