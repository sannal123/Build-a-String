
#Python3!
rep = int(input())
for r in range(rep):
    l, a, b = map(int, input().split(' '))
    s = input().strip()
    i = 1
    cost = 0
    cost = [float('inf')] * (l + 1)
    cost[0] = 0
    k = 0
    while i <= l: # i is the number of char finished, s[i-1] finished
        # find the maximun substring
        j = max(i, k)
        while j<=l and (s[i-1:j] in s[:i-1]):
            j += 1
        
        # s[i-1:j-1] in s
            
        if j-1 != i:
            cost[j-1] = min(cost[i-1] + b, cost[j-1])
            k = j
        cost[i] = min(cost[i-1] + a, cost[i])
        #print(cost)
        #print(s[i], a)
        i += 1
            
            
    print(cost[-1])
