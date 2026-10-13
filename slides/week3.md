# Week 3

(**Important note:** If you're seeing this before class, I've just published it and please don't look yet! If you're seeing this after class, I just haven't updated the website to add the slides yet...)

## In-Class Grading Activity

In your group, try to grade the following responses to this problem:

### Problem

Given an array of integers a[1] … a[n], find the maximum sum of a subset of elements, subject to the constraint that no two selected elements are adjacent in the array.

a) State the meaning of your table entries.

b) Give an efficiently computable recurrence for your table.

c) Justify the correctness.

### Sample Responses

#### Response 1
a) T[i] is the maximum sum of a non-adjacent subset of the first i elements.

b) T[0]=0, T[1]= max{0, a[1]}, and for i >= 2,
T[i] = max{T[i-1], T[i-2]+a[i]}.

c) This is correct by induction. The recurrence considers all possibilities, so it must give the optimal answer.

#### Response 2

a) Let T be the set of selected elements.

b) Start with an empty set. Find the largest element in the array, add it to (T), and remove that element and its adjacent elements from consideration. Repeat until no elements remain.

c) At each step, we choose the largest available element, so we maximize the sum. Removing its neighbors ensures that no two selected elements are adjacent.

#### Response 3

a) T[i] = the maximum sum a valid subset of the first i elements

b) T[i] = max{T[i-1], T[i-2] + 1}

c) My recurrence is correct because it handles both the cases of whether to include the ith element or not. If we don't include it then we can just get T[i-1], but if we do include it we can't use its neighbor so go back to T[i-2].

#### Response 4
a) T[i] = the maximum sum of a valid subset of a[1] ... a[i].

b) T[1] = max{0, a[1]}, T[2] = max{0, a[1], a[2]}, for i > 2, T[i] = max{T[i-2] + a[i], T[i-1]}

c) When considering the ith element, we can either choose to include it in our subset or not. If we don't include it, then the best we can do is take a subset from the first i - 1 elements, computed by T[i - 1]. If we do include it then a[i] is included in our sum, and we may as well add this to the best solution of the first i - 2 elements, since we can no longer use a[i-1] per the problem definition. In general, we want the maximum of these two cases. The base cases essentially brute force the max of all possible cases, which is trivially correct.

#### Response 5
a) T[i] = the maximum sum of a valid (possibly empty) subset of a[1] ... a[i].

b) T[0] = 0, T[1] = max{0, a[1]}, T[i] = max{T[i-2] + a[i], T[i-1]}

#### Response 6

a) T[i] is the maximum sum of a valid subset of the first i elements.

b) T[i] = max{T[i-1],T[i-2]+a[i]}.

c) Any optimal solution either contains a[i] or does not. If it does not, the solution is the same as T[i-1]. If it does, it cannot contain a[i-1], so its remaining elements come from the first i-2 elements. Thus the recurrence is correct.

#### Response 7

a) T[i] is the maximum sum of a valid subset of the first i elements that contains a[i].

b) T[i] = max{T[i-k]+a[i]} for the best choice of k >= 2.

c) By my table definition, T[i] must include a[i], which we want to add on to the best possible earlier solution that works with a[i] (i.e. any except T[i-1] bcuz this would be invalid). This covers all the cases for T[i], and at the end we would just want to be sure to take the maximum table entry, since the best might not be T[n].

#### Response 8
a) T[i] = sum of best solution to subproblem a[1] ... a[i]

b) T[i] = max{T[i-1], T[i-2] + a[i]}

c) This is just a weighted version of the standard include/exclude DP we saw in class.

#### Response 9
a) T[i] = the best subproblem solution

b) T[i] = max{T[i-1], T[i-1] + a[i], T[i-2],T[i-2] + a[i]}

c) It handles all the combinations of the last two elements, so it must be correct.

### Response 10
a) T[i] = the maximum sum of a valid subset of a[i] ... a[i]

b) T[i] = T[i - 1] + 

c)
