### [Back2Home](https://github.com/RecursiveSharma/ArraysCodingQuestions/main/README.md) | [Go2Video](#)
```java

//sol1 = using sorting or trick
class Solution {
    public int majorityElement(int[] nums) {
        Arrays.sort(nums);
        return nums[nums.length/2];
    }
}

```

```java

//Best Solution O(n) time complexity 
class Solution {
    public int majorityElement(int[] nums) {
        int count=1;
        int maj=nums[0];
        
        for(int i=1;i<nums.length;i++){
            if(nums[i]==maj){
                count++;
            }else if(count==0){
               maj=nums[i];
                count=1;
            }else{
                count--;
            }
            
        }
        return maj;
    }
}

//or concise form
//         int count = 0;
//         int maj=0;
//         for (int num : nums) {
//             if (count == 0) maj = num;
//             count += (num == maj) ? 1 : -1;
//         }
//         return maj;
```


```java

//sol3 = using hashmap for counting
if(nums.length==1) return nums[0];
    Map<Integer, Integer> map = new HashMap<Integer,Integer>();
    
    for(int i=0; i<nums.length; i++)
    {
        if(map.containsKey(nums[i]))
        {
           int n= map.get(nums[i])+1;
            if(n>nums.length/2) return nums[i];
            map.put(nums[i],n);
        }
        else
        {
            map.put(nums[i],1);
        }
    }
     return -1;
```
