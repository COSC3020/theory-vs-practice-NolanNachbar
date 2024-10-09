# Theory vs. Practice

- List 3 reasons why asymptotic analysis may be misleading with respect to
  actual performance in practice.
1. Asymptotic analysis mainly considers when input size $n$ gets big, this can be misleading for some functions wehn $n$ is small. For example, $n^3 + 2n^2 \in O(n^3)$ versus $100n^2 + 1000 \in O(n^2)$. A quick look at the big O for each wculd make you think that the latter is always faster but for small $n$ it's the inverse.
2. Similar to the previous reason, asymptotic analysis ignores constant factors and the largest componets to a function. This can be misleading because some functions with a theoretically better big O can be slower then a theoritically worse function because of though ignored factors. For example $n^3 \in O(n^3)$ versus $n^2 + 1000 \in O(n^2)$ from $n = 0, ..., 10$.
3. Asymptotic analysis could also be misleading when it comes to actually using the algorithms. Depending on the language, compiler, and implementation you use, the time to run an algorithm can vary. The implementation may be recursive, and the compiler may not be using tail call optimization with hardware contraints. This can lead to a very inefficient runtime on one machine, while using a asymptotically less efficient tail recursive algorithm on that same machine will be much faster.

- Suppose finding a particular element in a binary search tree with 1,000
  elements takes 5 seconds. Given what you know about the asymptotic complexity
  of search in a binary search tree, how long would you guess finding the same
  element in a search tree with 10,000 elements takes? Explain your reasoning.

We know for binary search the average time complexity is  $O(log n)$. Since this is a binary search tree,  $O(log_2 n)$. So:
$\frac{\log_{2}10000}{\log_{2}1000} = \frac{4}{3}$ so $5*\frac{4}{3} \approx 6.667$ seconds.

- You measure the time with 10,000 elements and it takes 100 seconds! List 3
  reasons why this could be the case, given that reasoning with the asymptotic
  complexity suggests a different time.
Add your answers to this markdown file.

1. The time complexity of $O(log_2 n)$ is for the average case; in the worst case it has a complexity of $O(n)$. The tree might not be balanced, it could have to search every element before it finds it. The machine might take 100 seconds for $O(10,000)$. $\log_2 10,000 \approx 13$ and $\frac{n}{\log_2 n} = \frac{10,000}{\log_2 10,000} \approx 753$ So if the search is more like $O(n)$ it could take up to about 753x as many comparisons as the $O(\log n)$ suggests. 
2. The computer that the searches are run on may have hardware constraints. For example, a computer with a small amount of RAM may need paging to run the larger search. It could be that this does not affect the tree with $1,000$ elements but it does the tree with $10,000$.
3. The conditions of the the envirnment might be different. Things like the language, compiler, and implementation you use can affect the runtimes. If the first test was ran using a certain language on one machine and then the $10,000$ element test was ran on a less powerful machine even with the same code, it might take much longer to run. In order to see the expected asymptotic based results you would need to ensure things like the software and hardware limitations don't effect the larger tree more than they do the small one and vice versa. 

I used this site to review things like the time complexity of binary search.
https://www.geeksforgeeks.org/complexity-analysis-of-binary-search/

I also used the lecture slides.

I used looked at this to help come up with a third reason the search tooks 100 seconds.
https://github.com/COSC3020/theory-vs-practice-Assel-Aljazwe

I certify that I have listed all sources used to complete this exercise, including the use of any Large Language Models. All of the work is my own, except where stated otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is suspected, charges may be filed against me without prior notice.

