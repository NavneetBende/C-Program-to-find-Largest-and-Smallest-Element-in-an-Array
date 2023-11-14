# C-Program-to-find-Largest-and-Smallest-Element-in-an-Array

Smallest and Largest Element in an Array in C
Here, in this page we will discuss the program to find largest and smallest element in an array in C programming language. We are given with an integer array and need to print the largest and smallest element of the array. We will discuss various approaches to find the smallest and largest element.

find smallest and largest
Implementations discussed:-
Method 1 deals with simple iterative approach
Method 2 deals with top down recursive approach
Method 3 details with bottom up recursive approach
Method 1
We will run a simple iterative for loop approach in this method

Method 1 Code in C
Run
#include <stdio.h>

void getSmallLarge(int arr[], int n)
{
    int smallest, largest;
    
    smallest = largest = arr[0];
    
    for(int i = 1; i < n ;i++){
        
        // finding smallest here
        if(arr[i] < smallest) smallest = arr[i]; // finding largest here
 if(arr[i] > largest) largest = arr[i]; 
        
    } 
    printf("Smallest: %d\n",smallest);
    printf("Largest: %d", largest); 
    
} 
int main() 
{ 
    int arr[] = {25, 40, 35, 20, 10, 80}; 
int len = sizeof(arr)/sizeof(arr[0]);
getSmallLarge(arr, len); 
    
}
Output
Smallest: 10
Largest: 80
Related Pages
Find Largest element in an array
 
Find Smallest Element in an Array
 
Find Second Smallest Element in an Array

Calculate the sum of elements in an array 

Reverse an Array

Method 2 (Top Down Recursive Approach)
This method requires you to know recursion in C.

Make sure to check these two pages before going ahead with this method –

Smallest element in an array
Largest element in an array
Method 2 Code in C
Run
// C Program to find smallest and largest elements in an array
// using top down recursive approach
#include <stdio.h>

// getting smallest here
void getSmallest(int arr[], int i, int len, int min)
{
    // base case, when last element was read in previous recursion 
    if(i >= len){
        printf("Smallest: %d\n", min);
        return;
    }
    
    if(arr[i] < min) 
        min = arr[i];
getSmallest(arr, i+1, len, min);
}

// getting largest here
void getLargest(int arr[], int i, int len, int max)
{
// base case, when last element was read in previous recursion
if(i >= len)
{ 
    printf("Largest: %d", max); 
    return; 
    
} 
if(arr[i] > max) max = arr[i]; 
getLargest(arr, i+1, len, max); 
    
}
int main() 
{ int arr[] = {70, 20, 10, 90, 30, 40, 60}; // get the length of the array 
int len = sizeof(arr)/sizeof(arr[0]); 
getSmallest(arr, 0, len, arr[0]); 
getLargest(arr, 0, len, arr[0]); 
return 0; 
    
} // Time complexity: O(N) // Space complexity: O(1) // Auxilary space complexity : O(N) due to function call stack
Output
Smallest: 10
Largest: 90
Method 3 (Bottom Up Recursive Approach)
This method requires you to know recursion in C.

Make sure to check these two pages before going ahead with this method –

Smallest element in an array
Largest element in an array
Method 3 Code in C
Run
// C Program to find smallest element in an array
// using bottom up recursive approach
#include <stdio.h>
// find smallest here
int minimum(int arr[], int i, int end)
{
    int min;
    
    // when we reach 2nd last array element
    // return the smaller b/w last & 2nd last elements
    if(i == end-1){
        return (arr[i] < arr[i + 1]) ? arr[i] : arr[i + 1];}
        
    min = minimum(arr, i + 1, end);

    return (arr[i] < min) ? arr[i] : min; 
    
}
// find largest here
int maximum(int arr[], int i, int end)
{
int max;

// when we reach 2nd last array element
// return the larger b/w last & 2nd last elements
if(i == end-1){ 
    return (arr[i] > arr[i + 1]) ? arr[i] : arr[i + 1]; }
max = maximum(arr, i + 1, end); 
return (arr[i] > max) ? arr[i] : max;
} 
int main()
{ 
    int arr[] = {70, 20, 10, 90, 30, 40, 60}; // storing the index of end array element // end = 5 : arr[5] = 80 (the end element) 

int end = sizeof(arr)/sizeof(arr[0]) - 1; 
int min = minimum(arr, 0, end); 
int max = maximum(arr, 0, end); 
printf("Smallest: %d\n", min); 
printf("Largest: %d\n", max); 

return 0;
}
Output
Smallest: 10
Largest: 90
