# Theory vs. Practice

- List 3 reasons why asymptotic analysis may be misleading with respect to
  actual performance in practice.
1. Asymptotic analysis mainly considers when input size $n$ gets big, this can be misleading for some functions wehn $n$ is small. For example, $n^3 + 2n^2 \in O(n^3)$ versus $100n^2 + 1000 \in O(n^2)$. A quick look at the big O for each wculd make you think that the latter is always faster but for small $n$ it's the inverse.
2. Similar to the previous reason, asymptotic analysis ignores constant factors and the largest componets to a function. This can be misleading because some functions with a theoretically better big O can be slower then a theoritically worse function because of though ignored factors. For example $n^3 \in O(n^3)$ versus $n^2 + 1000 \in O(n^2)$ from $n = 0, ..., 10$.
3. Asymptotic analysis could also be misleading when the big O is very bad but the best and average cases are much better. An example of this is binary search, where the worst case is $O(n)$ but the average case is $O(log n)$ and the best case is $O(1)$.
   
- Suppose finding a particular element in a binary search tree with 1,000
  elements takes 5 seconds. Given what you know about the asymptotic complexity
  of search in a binary search tree, how long would you guess finding the same
  element in a search tree with 10,000 elements takes? Explain your reasoning.
  
We know for binary search the average time complexity is  $O(log n)$. Since this is a binary search tree,  $O(log_2 n)$. So:
$\frac{\log_{2}10000}{\log_{2}1000} = \frac{4}{3}$ so $5*\frac{4}{3} \approx 6.667$ seconds.

- You measure the time with 10,000 elements and it takes 100 seconds! List 3
  reasons why this could be the case, given that reasoning with the asymptotic
  complexity suggests a different time.
  For a 
Add your answers to this markdown file.

1. The time complexity of $O(log_2 n)$ is for the average case, in the worst case it has a complexity of $O(n)$. The tree might not be balanced so it could have to search every element before it finds it. The machine might take 100 seconds for $O(10,000)$
2. 
3. 
   
I certify that I have listed all sources used to complete this exercise, including the use of any Large Language Models. All of the work is my own, except where stated otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is suspected, charges may be filed against me without prior notice.

I used this site to review things like the time complexity of binary search.
https://www.geeksforgeeks.org/complexity-analysis-of-binary-search/
I also used the lecture slides.
