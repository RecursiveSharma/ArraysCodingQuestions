### [Back2Home](https://github.com/RecursiveSharma/ArraysCodingQuestions/main/README.md) | [Go2Video](#)
# Previous Greater Element = Next Greater Element to Left
## Naive Solution = O(n)2
```java
// JAVA SOLUTION
public static void printPrevGreater(int arr[],int n){
        for(int i=0;i<n;i++){
            int j;
            for(j=i-1;j>=0;j--){
                if(arr[j]>arr[i]){
                    System.out.print(arr[j]+" ");
                    break;
                }
            }
            if(j==-1)
                System.out.print(-1+" ");
        }
    }


// C++ SOLUTION
void printPrevGreater(int arr[],int n){
    
    for(int i=0;i<n;i++){
        int j;
        for(j=i-1;j>=0;j--){
            if(arr[j]>arr[i]){
                cout<<arr[j]<<" ";
                break;
            }
        }
        if(j==-1)
            cout<<-1<<" ";
    }
}
```

##  Efficient Solution O(n) time complexity and space compexity = Using Stack
```java
//Java Solution
public static void printPrevGreater(int arr[],int n){
    
        Stack <Integer> s=new Stack<>();
        for(int i=0;i<n;i++){
            while(s.isEmpty()==false && s.peek()<=arr[i])
                s.pop();
            int pg=s.isEmpty()?-1:s.peek();
            System.out.print(pg+" ");
            s.add(arr[i]);
        }
    }


//C++ SOLUTION
void printPrevGreater(int arr[],int n){
    stack<int>s;
    for(int i=0;i<n;i++){
        while(s.empty()==false && s.top()<=arr[i])
            s.pop();
        int pg=s.empty()?-1:s.top();
        cout<<pg<<" ";
        s.push(arr[i]);
    }
}

```
