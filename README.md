# -Kth-Distinct-String-in-an-Array

A distinct string is a string that is present only once in an array.
Given an array of strings arr, and an integer k, return the kth distinct string present in arr. If there are fewer than k distinct strings, return an empty string "".
Note that the strings are considered in the order in which they appear in the array.

from collections import Counter
class Solution:
    def kthDistinct(self, arr: List[str], k: int) -> str:
        ans = []
        counted_items = Counter(arr)
        for key, value in counted_items.items():
            if value == 1:
                ans.append(key)
        n = len(ans)

        if k <= n and n > 0:
            return ans[k-1]
        else:
            return '' 

