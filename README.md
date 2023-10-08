# Sorting---Algorithms

### Water Trapping Probelm
a = [2,0,2,3,1,3,2,4,3]

# def water_trap(a):
    
def left_list(a):
    l1 = a.copy()
    for i in range(len(l1)-1):
        if l1[i] > l1[i+1]:
            l1[i+1] = l1[i]
    return l1
    
def right_list(a):
    l2 = a.copy()
    for i in range(len(l2)-1, 0,-1):
        if l2[i]> l2[i-1]:
            l2[i-1] = l2[i]
        # print("a[i-1] :", l2[i-1])
    return l2
    
def water_trap(a):
    left = left_list(a)
    right = right_list(a)
    
    print("left :", left)
    print("right :", right)
    print("a is :", a)
    sum = 0
    for i in range(len(a)):
        sum += (min(left[i], right[i]))-a[i]
        print("sum :", sum)
    return sum
    
    
print(a)
print("left_list(a) :",left_list(a))
print("right_list(a) :",right_list(a))
print("water_trap(a) :",water_trap(a))
