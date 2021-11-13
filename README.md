# Radix-Sort


## Working of Radix Sort

- Find the largest element in the array, i.e. max. Let X be the number of digits in max. X is calculated because we have to go through all the significant places of all elements.

- In this array [121, 432, 564, 23, 1, 45, 788], we have the largest number 788. It has 3 digits. Therefore, the loop should go up to hundreds place (3 times).
Now, go through each significant place one by one.

Use any stable sorting technique to sort the digits at each significant place. We have used counting sort for this.

Sort the elements based on the unit place digits (X=0).

<img width="714" alt="image" src="https://user-images.githubusercontent.com/65455865/141652406-2730c4e2-d5bd-4e5e-a21b-1421fcb75a38.png">

- Now, sort the elements based on digits at tens place.

<img width="508" alt="image" src="https://user-images.githubusercontent.com/65455865/141652437-8138fdd8-3c3b-469a-8ce9-cbfc44f5c4fd.png">

- Finally, sort the elements based on the digits at hundreds place.

<img width="508" alt="image" src="https://user-images.githubusercontent.com/65455865/141652454-2f5c6e9c-cd21-4b0d-b21f-b777f89c5cf9.png">



## RADIX ALGORITHM

radixSort(array)
  d <- maximum number of digits in the largest element
  create d buckets of size 0-9
  for i <- 0 to d
    sort the elements according to ith place digits using countingSort

countingSort(array, d)
  max <- find largest element among dth place elements
  initialize count array with all zeros
  for j <- 0 to size
    find the total count of each unique digit in dth place of elements and
    store the count at jth index in count array
  for i <- 1 to max
    find the cumulative sum and store it in count array itself
  for j <- size down to 1
    restore the elements to array
    decrease count of each element restored by 1
