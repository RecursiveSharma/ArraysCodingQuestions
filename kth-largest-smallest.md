### [Back2Home](https://github.com/RecursiveSharma/ArraysCodingQuestions/main/README.md) | [Go2Video](#)
```java

//sol1 = using sorting or trick
// Time complexity = O(nlogn)
class Solution {
    public int findKthLargest(int[] nums, int k) {
          Arrays.sort(nums);
          return nums[nums.length-k];
    }
}

```

```java

//Best Solution O(N + klogN) time complexity 
PriorityQueue<Integer> pq = new PriorityQueue<>();
        
        for(int i : nums){
            pq.add(i);
            if(pq.size()>k){
                pq.remove();
            }
        }
        
        return pq.remove();

```
