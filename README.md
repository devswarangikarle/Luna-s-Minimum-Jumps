# Luna-s-Minimum-Jumps

Luna, an adventurous explorer, has devised a jumping challenge for herself. She starts at the beginning of a path, represented by an array of non-negative integers. Each number in the array indicates the maximum distance Luna can jump from that spot. Her goal is to reach the last position on the path using the fewest jumps possible. Your mission is to help Luna determine the minimum number of jumps she needs to reach the end of her journey.


def minimum_jumps(n, arr):
    if n == 1:
        return 0
    
    jumps = 0
    current_end = 0
    farthest = 0

    for i in range(n - 1):  # No need to process the last index
        farthest = max(farthest, i + arr[i])
        if i == current_end:
            jumps += 1
            current_end = farthest
            if current_end >= n - 1:
                break

    return jumps

# Input Handling
n = int(input())
arr = list(map(int, input().split()))
print(minimum_jumps(n, arr))
