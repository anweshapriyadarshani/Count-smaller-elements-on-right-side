# Count-smaller-elements-on-right-side
Given an array of integers, return a new array where each element in the new array is the number of smaller elements to the right of that element in the original input array.  For example, given the array [3, 4, 9, 6, 1], return [1, 1, 2, 1, 0], since:      There is 1 smaller element to the right of 3     There is 1 smaller element to the right of 4     There are 2 smaller elements to the right of 9     There is 1 smaller element to the right of 6     There are no smaller elements to the right of 1


void constructLowerArray (int *arr[], int *countSmaller, int n)
{
  int i, j;
 
  // initialize all the counts in countSmaller array as 0
  for  (i = 0; i < n; i++)
     countSmaller[i] = 0;
 
  for (i = 0; i < n; i++)
  {
    for (j = i+1; j < n; j++)
    {
       if (arr[j] < arr[i])
         countSmaller[i]++;
    }
  }
}
 
/* Utility function that prints out an array on a line */
void printArray(int arr[], int size)
{
  int i;
  for (i=0; i < size; i++)
    printf("%d ", arr[i]);
 
  printf("\n");
}
 
// Driver program to test above functions
int main()
{
  int arr[] = {12, 10, 5, 4, 2, 20, 6, 1, 0, 2};
  int n = sizeof(arr)/sizeof(arr[0]);
  int *low = (int *)malloc(sizeof(int)*n);
  constructLowerArray(arr, low, n);
  printArray(low, n);
  return 0;
}
