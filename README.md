<table style="height: 120px;" width="203">
<tbody>
<tr>
<td style="width: 193.76px;">
<p>Annam Dheeraj</p>
<p>RA1811029010032</p>
<p>CSE-CN-L2</p>
</td>
</tr>
</tbody>
</table>
<p>&nbsp;</p>
<h1>DESIGN ANALYSIS AND ALGORITHM</h1>
<p>An algorithm is a set of steps of operations to solve a problem performing calculation, data processing, and automated reasoning tasks. An algorithm is an efficient method that can be expressed within finite amount of time and space.</p>
<p>An algorithm is the best way to represent the solution of a particular problem in a very simple and efficient way. If we have an algorithm for a specific problem, then we can implement it in any programming language, meaning that the&nbsp;<strong>algorithm is independent from any programming languages</strong>.</p>
<p>&nbsp;</p>
<p>Here in this algorithms has 6 different paradigms</p>
<p>BRUTE FORCE<br />DIVIDE AND CONQUER<br />GREETY ALGORITHM<br />DYNAMIC PROGRAMMING<br />BACKTRACKING<br />BRANCH AND BOUND<br />DIVIDE AND CONQUER:</p>
<p>According to SRM we have np-complete problems&nbsp;</p>
<ul>
<li>boolen satisfiability problem</li>
<li>knapsack problem</li>
<li>hamiltonian problem</li>
<li>subgraph isomorphism problem</li>
<li>subset sum problem</li>
<li>clique problem</li>
<li>vertex cover problem</li>
<li>graph colouring problem</li>
</ul>
<p>According to sessions from UNIT-1 to UNIT-5</p>
<ol>
<li>Algorithm and pseudo code(unit-1)</li>
<li>Algorithm design techniques</li>
<li>Algorithm analysis</li>
<li>Asymptotic notations</li>
<li>Recurrsion call,mathematical induction</li>
<li>substution methord</li>
<li>recurrence relation</li>
<li>Masters theorem</li>
<li>Binary search(unit-2)</li>
<li>Merge sort</li>
<li>Quick sort</li>
<li>Strassens matrix multiplication</li>
<li>Finding max and min</li>
<li>Finding closest pair</li>
<li>Convex hull</li>
<li>Huffman coding(unit-3)</li>
<li>Knapsack problem</li>
<li>minimum spanning tree</li>
<li>knapsack problem(dynamic)</li>
<li>knapsack</li>
<li>Travelling salesman problem</li>
<li>multistage graph</li>
<li>N-queens problem(unit-4)</li>
<li>N-queens problem</li>
<li>Sum of subsets</li>
<li>Graph colouring</li>
<li>Hamiltonian circuit</li>
<li>Travelling salesman problem</li>
<li>generating permutation</li>
<li>knapsack problem(branchbound)(unit-5)</li>
<li>branch bound and randomized algorithm</li>
</ol>
<p>&nbsp;</p>
<p>&nbsp;</p>
<header class="entry-header">
<h1 class="entry-title">Binary Search</h1>
</header>
<div class="entry-content">
<p>Given a sorted array arr[] of n elements, write a function to search a given element x in arr[].</p>
<p>A simple approach is to do&nbsp;<strong><a href="http://quiz.geeksforgeeks.org/linear-search/">linear search</a>.</strong>The time complexity of above algorithm is O(n). Another approach to perform the same task is using Binary Search.</p>
<p><strong>Binary Search:</strong>&nbsp;Search a sorted array by repeatedly dividing the search interval in half. Begin with an interval covering the whole array. If the value of the search key is less than the item in the middle of the interval, narrow the interval to the lower half. Otherwise narrow it to the upper half. Repeatedly check until the value is found or the interval is empty.</p>
<p>&nbsp;</p>
<header class="entry-header">
<h1 class="entry-title">Merge Sort</h1>
</header>
<div class="entry-content">
<p>Like&nbsp;<a href="https://www.geeksforgeeks.org/quick-sort/">QuickSort</a>, Merge Sort is a&nbsp;<a href="https://www.geeksforgeeks.org/divide-and-conquer-introduction/" target="_blank" rel="noopener">Divide and Conquer</a>&nbsp;algorithm. It divides input array in two halves, calls itself for the two halves and then merges the two sorted halves.&nbsp;<strong>The merge() function</strong>&nbsp;is used for merging two halves. The merge(arr, l, m, r) is key process that assumes that arr[l..m] and arr[m+1..r] are sorted and merges the two sorted sub-arrays into one. See following C implementation for details.</p>
<pre><strong>MergeSort(arr[], l,  r)</strong>
If r &gt; l
     <strong>1. </strong>Find the middle point to divide the array into two halves:  
             middle m = (l+r)/2
    <strong> 2. </strong>Call mergeSort for first half:   
             Call mergeSort(arr, l, m)
     <strong>3.</strong> Call mergeSort for second half:
             Call mergeSort(arr, m+1, r)
     <strong>4. </strong>Merge the two halves sorted in step 2 and 3:
             Call merge(arr, l, m, r)</pre>
<p>The following diagram from&nbsp;<a href="http://en.wikipedia.org/wiki/File:Merge_sort_algorithm_diagram.svg" target="_blank" rel="noopener">wikipedia</a>&nbsp;shows the complete merge sort process for an example array {38, 27, 43, 3, 9, 82, 10}. If we take a closer look at the diagram, we can see that the array is recursively divided in two halves till the size becomes 1. Once the size becomes 1, the merge processes comes into action and starts merging arrays back till the complete array is merged.</p>
<p>&nbsp;</p>
<header class="entry-header">
<h1 class="entry-title">QuickSort</h1>
</header>
<div class="entry-content">
<div>&nbsp;Like&nbsp;<a href="http://quiz.geeksforgeeks.org/merge-sort/" target="_blank" rel="noopener">Merge Sort</a>, QuickSort is a Divide and Conquer algorithm. It picks an element as pivot and partitions the given array around the picked pivot.&nbsp;There are many different versions of quickSort that pick pivot in different ways.</div>
<ol>
<li>Always pick first element as pivot.</li>
<li>Always pick last element as pivot (implemented below)</li>
<li>Pick a random element as pivot.</li>
<li>Pick median as pivot.</li>
</ol>
<p>The key process in quickSort is partition(). Target of partitions is, given an array and an element x of array as pivot, put x at its correct position in sorted array and put all smaller elements (smaller than x) before x, and put all greater elements (greater than x) after x. All this should be done in linear time.</p>
<p><strong>Pseudo Code for recursive QuickSort function :</strong></p>
<pre>/* low  --&gt; Starting index,  high  --&gt; Ending index */
quickSort(arr[], low, high)
{
    if (low &lt; high)
    {
        /* pi is partitioning index, arr[pi] is now
           at right place */
        pi = partition(arr, low, high);

        quickSort(arr, low, pi - 1);  // Before pi
        quickSort(arr, pi + 1, high); // After pi
    }<img src="https://medium.com/@codingfreak/binary-search-practice-problems-4c856cd9f26c" alt="" /><br /><br /></pre>
<h2>FINDING MAX AND MIN</h2>
<p>To find the maximum and minimum numbers in a given array&nbsp;<strong><em>numbers[]</em></strong>&nbsp;of size&nbsp;<strong>n</strong>, the following algorithm can be used. First we are representing the&nbsp;<strong>naive method</strong>&nbsp;and then we will present&nbsp;<strong>divide and conquer approach</strong>.</p>
<h2>Na&iuml;ve Method</h2>
<p>Na&iuml;ve method is a basic method to solve any problem. In this method, the maximum and minimum number can be found separately. To find the maximum and minimum numbers, the following straightforward algorithm can be used.</p>
<pre class="result notranslate"><strong>Algorithm: Max-Min-Element (numbers[])</strong> 
max := numbers[1] 
min := numbers[1] 

for i = 2 to n do 
   if numbers[i] &gt; max then  
      max := numbers[i] 
   if numbers[i] &lt; min then  
      min := numbers[i] 
return (max, min) 
</pre>
<h3>Analysis</h3>
<p>The number of comparison in Naive method is&nbsp;<strong>2n - 2</strong>.</p>
<p>The number of comparisons can be reduced using the divide and conquer approach. Following is the technique.</p>
<h2>Divide and Conquer Approach</h2>
<p>In this approach, the array is divided into two halves. Then using recursive approach maximum and minimum numbers in each halves are found. Later, return the maximum of two maxima of each half and the minimum of two minima of each half.</p>
<p>In this given problem, the number of elements in an array is&nbsp;<span id="MathJax-Element-1-Frame" class="MathJax" style="display: inline; font-style: normal; font-weight: normal; line-height: normal; font-size: 15px; text-indent: 0px; text-align: left; text-transform: none; letter-spacing: normal; word-spacing: normal; overflow-wrap: normal; white-space: nowrap; float: none; direction: ltr; max-width: none; max-height: none; min-width: 0px; min-height: 0px; border: 0px; padding: 0px; margin: 0px; position: relative;" tabindex="0" role="presentation" data-mathml="&lt;math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;&gt;&lt;mi&gt;y&lt;/mi&gt;&lt;mo&gt;&amp;#x2212;&lt;/mo&gt;&lt;mi&gt;x&lt;/mi&gt;&lt;mo&gt;+&lt;/mo&gt;&lt;mn&gt;1&lt;/mn&gt;&lt;/math&gt;"><span id="MathJax-Span-1" class="math"><span id="MathJax-Span-2" class="mrow"><span id="MathJax-Span-3" class="mi">y</span><span id="MathJax-Span-4" class="mo">&minus;</span><span id="MathJax-Span-5" class="mi">x</span><span id="MathJax-Span-6" class="mo">+</span><span id="MathJax-Span-7" class="mn">1</span></span></span><span class="MJX_Assistive_MathML" role="presentation">y&minus;x+1</span></span>, where&nbsp;<strong>y</strong>&nbsp;is greater than or equal to&nbsp;<strong>x</strong>.</p>
<p><span id="MathJax-Element-2-Frame" class="MathJax" style="display: inline; font-style: normal; font-weight: normal; line-height: normal; font-size: 15px; text-indent: 0px; text-align: left; text-transform: none; letter-spacing: normal; word-spacing: normal; overflow-wrap: normal; white-space: nowrap; float: none; direction: ltr; max-width: none; max-height: none; min-width: 0px; min-height: 0px; border: 0px; padding: 0px; margin: 0px; position: relative;" tabindex="0" role="presentation" data-mathml="&lt;math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;&gt;&lt;mrow class=&quot;MJX-TeXAtom-ORD&quot;&gt;&lt;mrow class=&quot;MJX-TeXAtom-ORD&quot;&gt;&lt;mi class=&quot;MJX-tex-mathit&quot; mathvariant=&quot;italic&quot;&gt;M&lt;/mi&gt;&lt;mi class=&quot;MJX-tex-mathit&quot; mathvariant=&quot;italic&quot;&gt;a&lt;/mi&gt;&lt;mi class=&quot;MJX-tex-mathit&quot; mathvariant=&quot;italic&quot;&gt;x&lt;/mi&gt;&lt;mo class=&quot;MJX-tex-mathit&quot; mathvariant=&quot;italic&quot;&gt;&amp;#x2212;&lt;/mo&gt;&lt;mi class=&quot;MJX-tex-mathit&quot; mathvariant=&quot;italic&quot;&gt;M&lt;/mi&gt;&lt;mi class=&quot;MJX-tex-mathit&quot; mathvariant=&quot;italic&quot;&gt;i&lt;/mi&gt;&lt;mi class=&quot;MJX-tex-mathit&quot; mathvariant=&quot;italic&quot;&gt;n&lt;/mi&gt;&lt;mo class=&quot;MJX-tex-mathit&quot; mathvariant=&quot;italic&quot; stretchy=&quot;false&quot;&gt;(&lt;/mo&gt;&lt;mi class=&quot;MJX-tex-mathit&quot; mathvariant=&quot;italic&quot;&gt;x&lt;/mi&gt;&lt;mo class=&quot;MJX-tex-mathit&quot; mathvariant=&quot;italic&quot;&gt;,&lt;/mo&gt;&lt;mi class=&quot;MJX-tex-mathit&quot; mathvariant=&quot;italic&quot;&gt;y&lt;/mi&gt;&lt;mo class=&quot;MJX-tex-mathit&quot; mathvariant=&quot;italic&quot; stretchy=&quot;false&quot;&gt;)&lt;/mo&gt;&lt;/mrow&gt;&lt;/mrow&gt;&lt;/math&gt;"><span id="MathJax-Span-8" class="math"><span id="MathJax-Span-9" class="mrow"><span id="MathJax-Span-10" class="texatom"><span id="MathJax-Span-11" class="mrow"><span id="MathJax-Span-12" class="texatom"><span id="MathJax-Span-13" class="mrow"><span id="MathJax-Span-14" class="mi">M</span><span id="MathJax-Span-15" class="mi">a</span><span id="MathJax-Span-16" class="mi">x</span><span id="MathJax-Span-17" class="mo">&minus;</span><span id="MathJax-Span-18" class="mi">M</span><span id="MathJax-Span-19" class="mi">i</span><span id="MathJax-Span-20" class="mi">n</span><span id="MathJax-Span-21" class="mo">(</span><span id="MathJax-Span-22" class="mi">x</span><span id="MathJax-Span-23" class="mo">,</span><span id="MathJax-Span-24" class="mi">y</span><span id="MathJax-Span-25" class="mo">)</span></span></span></span></span></span></span><span class="MJX_Assistive_MathML" role="presentation">Max&minus;Min(x,y)</span></span>&nbsp;will return the maximum and minimum values of an array&nbsp;<span id="MathJax-Element-3-Frame" class="MathJax" style="display: inline; font-style: normal; font-weight: normal; line-height: normal; font-size: 15px; text-indent: 0px; text-align: left; text-transform: none; letter-spacing: normal; word-spacing: normal; overflow-wrap: normal; white-space: nowrap; float: none; direction: ltr; max-width: none; max-height: none; min-width: 0px; min-height: 0px; border: 0px; padding: 0px; margin: 0px; position: relative;" tabindex="0" role="presentation" data-mathml="&lt;math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;&gt;&lt;mrow class=&quot;MJX-TeXAtom-ORD&quot;&gt;&lt;mrow class=&quot;MJX-TeXAtom-ORD&quot;&gt;&lt;mi class=&quot;MJX-tex-mathit&quot; mathvariant=&quot;italic&quot;&gt;n&lt;/mi&gt;&lt;mi class=&quot;MJX-tex-mathit&quot; mathvariant=&quot;italic&quot;&gt;u&lt;/mi&gt;&lt;mi class=&quot;MJX-tex-mathit&quot; mathvariant=&quot;italic&quot;&gt;m&lt;/mi&gt;&lt;mi class=&quot;MJX-tex-mathit&quot; mathvariant=&quot;italic&quot;&gt;b&lt;/mi&gt;&lt;mi class=&quot;MJX-tex-mathit&quot; mathvariant=&quot;italic&quot;&gt;e&lt;/mi&gt;&lt;mi class=&quot;MJX-tex-mathit&quot; mathvariant=&quot;italic&quot;&gt;r&lt;/mi&gt;&lt;mi class=&quot;MJX-tex-mathit&quot; mathvariant=&quot;italic&quot;&gt;s&lt;/mi&gt;&lt;mo class=&quot;MJX-tex-mathit&quot; mathvariant=&quot;italic&quot; stretchy=&quot;false&quot;&gt;[&lt;/mo&gt;&lt;mi class=&quot;MJX-tex-mathit&quot; mathvariant=&quot;italic&quot;&gt;x&lt;/mi&gt;&lt;mo class=&quot;MJX-tex-mathit&quot; mathvariant=&quot;italic&quot;&gt;.&lt;/mo&gt;&lt;mo class=&quot;MJX-tex-mathit&quot; mathvariant=&quot;italic&quot;&gt;.&lt;/mo&gt;&lt;mo class=&quot;MJX-tex-mathit&quot; mathvariant=&quot;italic&quot;&gt;.&lt;/mo&gt;&lt;mi class=&quot;MJX-tex-mathit&quot; mathvariant=&quot;italic&quot;&gt;y&lt;/mi&gt;&lt;mo class=&quot;MJX-tex-mathit&quot; mathvariant=&quot;italic&quot; stretchy=&quot;false&quot;&gt;]&lt;/mo&gt;&lt;/mrow&gt;&lt;/mrow&gt;&lt;/math&gt;"><span id="MathJax-Span-26" class="math"><span id="MathJax-Span-27" class="mrow"><span id="MathJax-Span-28" class="texatom"><span id="MathJax-Span-29" class="mrow"><span id="MathJax-Span-30" class="texatom"><span id="MathJax-Span-31" class="mrow"><span id="MathJax-Span-32" class="mi">n</span><span id="MathJax-Span-33" class="mi">u</span><span id="MathJax-Span-34" class="mi">m</span><span id="MathJax-Span-35" class="mi">b</span><span id="MathJax-Span-36" class="mi">e</span><span id="MathJax-Span-37" class="mi">r</span><span id="MathJax-Span-38" class="mi">s</span><span id="MathJax-Span-39" class="mo">[</span><span id="MathJax-Span-40" class="mi">x</span><span id="MathJax-Span-41" class="mo">.</span><span id="MathJax-Span-42" class="mo">.</span><span id="MathJax-Span-43" class="mo">.</span><span id="MathJax-Span-44" class="mi">y</span><span id="MathJax-Span-45" class="mo">]</span></span></span></span></span></span></span><span class="MJX_Assistive_MathML" role="presentation">numbers[x...y]</span></span>.</p>
<pre class="result notranslate"><strong>Algorithm: Max - Min(x, y)</strong> 
if y &ndash; x &le; 1 then  
   return (max(numbers[x], numbers[y]), min((numbers[x], numbers[y])) 
else 
   (max1, min1):= maxmin(x, &lfloor;((x + y)/2)&rfloor;) 
   (max2, min2):= maxmin(&lfloor;((x + y)/2) + 1)&rfloor;,y) 
return (max(max1, max2), min(min1, min2)) 
</pre>
<h3>Analysis</h3>
<p>Let&nbsp;<strong><em>T(n)</em></strong>&nbsp;be the number of comparisons made by&nbsp;<span id="MathJax-Element-4-Frame" class="MathJax" style="display: inline; font-style: normal; font-weight: normal; line-height: normal; font-size: 15px; text-indent: 0px; text-align: left; text-transform: none; letter-spacing: normal; word-spacing: normal; overflow-wrap: normal; white-space: nowrap; float: none; direction: ltr; max-width: none; max-height: none; min-width: 0px; min-height: 0px; border: 0px; padding: 0px; margin: 0px; position: relative;" tabindex="0" role="presentation" data-mathml="&lt;math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;&gt;&lt;mrow class=&quot;MJX-TeXAtom-ORD&quot;&gt;&lt;mrow class=&quot;MJX-TeXAtom-ORD&quot;&gt;&lt;mi class=&quot;MJX-tex-mathit&quot; mathvariant=&quot;italic&quot;&gt;M&lt;/mi&gt;&lt;mi class=&quot;MJX-tex-mathit&quot; mathvariant=&quot;italic&quot;&gt;a&lt;/mi&gt;&lt;mi class=&quot;MJX-tex-mathit&quot; mathvariant=&quot;italic&quot;&gt;x&lt;/mi&gt;&lt;mo class=&quot;MJX-tex-mathit&quot; mathvariant=&quot;italic&quot;&gt;&amp;#x2212;&lt;/mo&gt;&lt;mi class=&quot;MJX-tex-mathit&quot; mathvariant=&quot;italic&quot;&gt;M&lt;/mi&gt;&lt;mi class=&quot;MJX-tex-mathit&quot; mathvariant=&quot;italic&quot;&gt;i&lt;/mi&gt;&lt;mi class=&quot;MJX-tex-mathit&quot; mathvariant=&quot;italic&quot;&gt;n&lt;/mi&gt;&lt;mo class=&quot;MJX-tex-mathit&quot; mathvariant=&quot;italic&quot; stretchy=&quot;false&quot;&gt;(&lt;/mo&gt;&lt;mi class=&quot;MJX-tex-mathit&quot; mathvariant=&quot;italic&quot;&gt;x&lt;/mi&gt;&lt;mo class=&quot;MJX-tex-mathit&quot; mathvariant=&quot;italic&quot;&gt;,&lt;/mo&gt;&lt;mi class=&quot;MJX-tex-mathit&quot; mathvariant=&quot;italic&quot;&gt;y&lt;/mi&gt;&lt;mo class=&quot;MJX-tex-mathit&quot; mathvariant=&quot;italic&quot; stretchy=&quot;false&quot;&gt;)&lt;/mo&gt;&lt;/mrow&gt;&lt;/mrow&gt;&lt;/math&gt;"><span id="MathJax-Span-46" class="math"><span id="MathJax-Span-47" class="mrow"><span id="MathJax-Span-48" class="texatom"><span id="MathJax-Span-49" class="mrow"><span id="MathJax-Span-50" class="texatom"><span id="MathJax-Span-51" class="mrow"><span id="MathJax-Span-52" class="mi">M</span><span id="MathJax-Span-53" class="mi">a</span><span id="MathJax-Span-54" class="mi">x</span><span id="MathJax-Span-55" class="mo">&minus;</span><span id="MathJax-Span-56" class="mi">M</span><span id="MathJax-Span-57" class="mi">i</span><span id="MathJax-Span-58" class="mi">n</span><span id="MathJax-Span-59" class="mo">(</span><span id="MathJax-Span-60" class="mi">x</span><span id="MathJax-Span-61" class="mo">,</span><span id="MathJax-Span-62" class="mi">y</span><span id="MathJax-Span-63" class="mo">)</span></span></span></span></span></span></span><span class="MJX_Assistive_MathML" role="presentation">Max&minus;Min(x,y)</span></span>, where the number of elements&nbsp;<span id="MathJax-Element-5-Frame" class="MathJax" style="display: inline; font-style: normal; font-weight: normal; line-height: normal; font-size: 15px; text-indent: 0px; text-align: left; text-transform: none; letter-spacing: normal; word-spacing: normal; overflow-wrap: normal; white-space: nowrap; float: none; direction: ltr; max-width: none; max-height: none; min-width: 0px; min-height: 0px; border: 0px; padding: 0px; margin: 0px; position: relative;" tabindex="0" role="presentation" data-mathml="&lt;math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;&gt;&lt;mi&gt;n&lt;/mi&gt;&lt;mo&gt;=&lt;/mo&gt;&lt;mi&gt;y&lt;/mi&gt;&lt;mo&gt;&amp;#x2212;&lt;/mo&gt;&lt;mi&gt;x&lt;/mi&gt;&lt;mo&gt;+&lt;/mo&gt;&lt;mn&gt;1&lt;/mn&gt;&lt;/math&gt;"><span id="MathJax-Span-64" class="math"><span id="MathJax-Span-65" class="mrow"><span id="MathJax-Span-66" class="mi">n</span><span id="MathJax-Span-67" class="mo">=</span><span id="MathJax-Span-68" class="mi">y</span><span id="MathJax-Span-69" class="mo">&minus;</span><span id="MathJax-Span-70" class="mi">x</span><span id="MathJax-Span-71" class="mo">+</span><span id="MathJax-Span-72" class="mn">1</span></span></span><span class="MJX_Assistive_MathML" role="presentation">n=y&minus;x+1</span></span>.</p>
<p>If&nbsp;<strong><em>T(n)</em></strong>&nbsp;represents the numbers, then the recurrence relation can be represented as</p>
<div class="MathJax_Display"><span id="MathJax-Element-6-Frame" class="MathJax" style="display: inline; font-style: normal; font-weight: normal; line-height: normal; font-size: 15px; text-indent: 0px; text-align: center; text-transform: none; letter-spacing: normal; word-spacing: normal; overflow-wrap: normal; white-space: nowrap; float: none; direction: ltr; max-width: none; max-height: none; min-width: 0px; min-height: 0px; border: 0px; padding: 0px; margin: 0px; position: relative;" tabindex="0" role="presentation" data-mathml="&lt;math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot; display=&quot;block&quot;&gt;&lt;mi&gt;T&lt;/mi&gt;&lt;mo stretchy=&quot;false&quot;&gt;(&lt;/mo&gt;&lt;mi&gt;n&lt;/mi&gt;&lt;mo stretchy=&quot;false&quot;&gt;)&lt;/mo&gt;&lt;mo&gt;=&lt;/mo&gt;&lt;mrow&gt;&lt;mo&gt;{&lt;/mo&gt;&lt;mtable columnalign=&quot;left left&quot; rowspacing=&quot;.2em&quot; columnspacing=&quot;1em&quot; displaystyle=&quot;false&quot;&gt;&lt;mtr&gt;&lt;mtd&gt;&lt;mi&gt;T&lt;/mi&gt;&lt;mrow&gt;&lt;mo&gt;(&lt;/mo&gt;&lt;mrow&gt;&lt;mo fence=&quot;false&quot; stretchy=&quot;false&quot;&gt;&amp;#x230A;&lt;/mo&gt;&lt;mfrac&gt;&lt;mi&gt;n&lt;/mi&gt;&lt;mn&gt;2&lt;/mn&gt;&lt;/mfrac&gt;&lt;mo fence=&quot;false&quot; stretchy=&quot;false&quot;&gt;&amp;#x230B;&lt;/mo&gt;&lt;/mrow&gt;&lt;mo&gt;)&lt;/mo&gt;&lt;/mrow&gt;&lt;mo&gt;+&lt;/mo&gt;&lt;mi&gt;T&lt;/mi&gt;&lt;mrow&gt;&lt;mo&gt;(&lt;/mo&gt;&lt;mrow&gt;&lt;mo fence=&quot;false&quot; stretchy=&quot;false&quot;&gt;&amp;#x2308;&lt;/mo&gt;&lt;mfrac&gt;&lt;mi&gt;n&lt;/mi&gt;&lt;mn&gt;2&lt;/mn&gt;&lt;/mfrac&gt;&lt;mo fence=&quot;false&quot; stretchy=&quot;false&quot;&gt;&amp;#x2309;&lt;/mo&gt;&lt;/mrow&gt;&lt;mo&gt;)&lt;/mo&gt;&lt;/mrow&gt;&lt;mo&gt;+&lt;/mo&gt;&lt;mn&gt;2&lt;/mn&gt;&lt;/mtd&gt;&lt;mtd&gt;&lt;mi&gt;f&lt;/mi&gt;&lt;mi&gt;o&lt;/mi&gt;&lt;mi&gt;r&lt;/mi&gt;&lt;mspace width=&quot;mediummathspace&quot; /&gt;&lt;mi&gt;n&lt;/mi&gt;&lt;mo&gt;&amp;gt;&lt;/mo&gt;&lt;mn&gt;2&lt;/mn&gt;&lt;/mtd&gt;&lt;/mtr&gt;&lt;mtr&gt;&lt;mtd&gt;&lt;mn&gt;1&lt;/mn&gt;&lt;/mtd&gt;&lt;mtd&gt;&lt;mi&gt;f&lt;/mi&gt;&lt;mi&gt;o&lt;/mi&gt;&lt;mi&gt;r&lt;/mi&gt;&lt;mspace width=&quot;mediummathspace&quot; /&gt;&lt;mi&gt;n&lt;/mi&gt;&lt;mo&gt;=&lt;/mo&gt;&lt;mn&gt;2&lt;/mn&gt;&lt;/mtd&gt;&lt;/mtr&gt;&lt;mtr&gt;&lt;mtd&gt;&lt;mn&gt;0&lt;/mn&gt;&lt;/mtd&gt;&lt;mtd&gt;&lt;mi&gt;f&lt;/mi&gt;&lt;mi&gt;o&lt;/mi&gt;&lt;mi&gt;r&lt;/mi&gt;&lt;mspace width=&quot;mediummathspace&quot; /&gt;&lt;mi&gt;n&lt;/mi&gt;&lt;mo&gt;=&lt;/mo&gt;&lt;mn&gt;1&lt;/mn&gt;&lt;/mtd&gt;&lt;/mtr&gt;&lt;/mtable&gt;&lt;mo fence=&quot;true&quot; stretchy=&quot;true&quot; symmetric=&quot;true&quot;&gt;&lt;/mo&gt;&lt;/mrow&gt;&lt;/math&gt;"><span id="MathJax-Span-73" class="math"><span id="MathJax-Span-74" class="mrow"><span id="MathJax-Span-75" class="mi">T</span><span id="MathJax-Span-76" class="mo">(</span><span id="MathJax-Span-77" class="mi">n</span><span id="MathJax-Span-78" class="mo">)</span><span id="MathJax-Span-79" class="mo">=</span><span id="MathJax-Span-80" class="mrow"><span id="MathJax-Span-81" class="mo">⎧⎩⎨⎪⎪</span><span id="MathJax-Span-82" class="mtable"><span id="MathJax-Span-83" class="mtd"><span id="MathJax-Span-84" class="mrow"><span id="MathJax-Span-85" class="mi">T</span><span id="MathJax-Span-86" class="mrow"><span id="MathJax-Span-87" class="mo">(</span><span id="MathJax-Span-88" class="mrow"><span id="MathJax-Span-89" class="mo">&lfloor;</span><span id="MathJax-Span-90" class="mfrac"><span id="MathJax-Span-91" class="mi">n</span><span id="MathJax-Span-92" class="mn">2</span></span><span id="MathJax-Span-93" class="mo">&rfloor;</span></span><span id="MathJax-Span-94" class="mo">)</span></span><span id="MathJax-Span-95" class="mo">+</span><span id="MathJax-Span-96" class="mi">T</span><span id="MathJax-Span-97" class="mrow"><span id="MathJax-Span-98" class="mo">(</span><span id="MathJax-Span-99" class="mrow"><span id="MathJax-Span-100" class="mo">&lceil;</span><span id="MathJax-Span-101" class="mfrac"><span id="MathJax-Span-102" class="mi">n</span><span id="MathJax-Span-103" class="mn">2</span></span><span id="MathJax-Span-104" class="mo">&rceil;</span></span><span id="MathJax-Span-105" class="mo">)</span></span><span id="MathJax-Span-106" class="mo">+</span><span id="MathJax-Span-107" class="mn">2</span></span></span><span id="MathJax-Span-117" class="mtd"><span id="MathJax-Span-118" class="mrow"><span id="MathJax-Span-119" class="mn">1</span></span></span><span id="MathJax-Span-129" class="mtd"><span id="MathJax-Span-130" class="mrow"><span id="MathJax-Span-131" class="mn">0</span></span></span><span id="MathJax-Span-108" class="mtd"><span id="MathJax-Span-109" class="mrow"><span id="MathJax-Span-110" class="mi">f</span><span id="MathJax-Span-111" class="mi">o</span><span id="MathJax-Span-112" class="mi">r</span><span id="MathJax-Span-113" class="mspace"></span><span id="MathJax-Span-114" class="mi">n</span><span id="MathJax-Span-115" class="mo">&gt;</span><span id="MathJax-Span-116" class="mn">2</span></span></span><span id="MathJax-Span-120" class="mtd"><span id="MathJax-Span-121" class="mrow"><span id="MathJax-Span-122" class="mi">f</span><span id="MathJax-Span-123" class="mi">o</span><span id="MathJax-Span-124" class="mi">r</span><span id="MathJax-Span-125" class="mspace"></span><span id="MathJax-Span-126" class="mi">n</span><span id="MathJax-Span-127" class="mo">=</span><span id="MathJax-Span-128" class="mn">2</span></span></span><span id="MathJax-Span-132" class="mtd"><span id="MathJax-Span-133" class="mrow"><span id="MathJax-Span-134" class="mi">f</span><span id="MathJax-Span-135" class="mi">o</span><span id="MathJax-Span-136" class="mi">r</span><span id="MathJax-Span-137" class="mspace"></span><span id="MathJax-Span-138" class="mi">n</span><span id="MathJax-Span-139" class="mo">=</span><span id="MathJax-Span-140" class="mn">1</span></span></span></span><span id="MathJax-Span-141" class="mo"></span></span></span></span><span class="MJX_Assistive_MathML MJX_Assistive_MathML_Block" role="presentation">T(n)={T(&lfloor;n2&rfloor;)+T(&lceil;n2&rceil;)+2forn&gt;21forn=20forn=1</span></span></div>
<p>Let us assume that&nbsp;<strong><em>n</em></strong>&nbsp;is in the form of power of&nbsp;<strong>2</strong>. Hence,&nbsp;<strong>n = 2<sup>k</sup></strong>&nbsp;where&nbsp;<strong>k</strong>&nbsp;is height of the recursion tree.</p>
<p>So,</p>
<div class="MathJax_Display"><span id="MathJax-Element-7-Frame" class="MathJax" style="display: inline; font-style: normal; font-weight: normal; line-height: normal; font-size: 15px; text-indent: 0px; text-align: center; text-transform: none; letter-spacing: normal; word-spacing: normal; overflow-wrap: normal; white-space: nowrap; float: none; direction: ltr; max-width: none; max-height: none; min-width: 0px; min-height: 0px; border: 0px; padding: 0px; margin: 0px; position: relative;" tabindex="0" role="presentation" data-mathml="&lt;math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot; display=&quot;block&quot;&gt;&lt;mi&gt;T&lt;/mi&gt;&lt;mo stretchy=&quot;false&quot;&gt;(&lt;/mo&gt;&lt;mi&gt;n&lt;/mi&gt;&lt;mo stretchy=&quot;false&quot;&gt;)&lt;/mo&gt;&lt;mo&gt;=&lt;/mo&gt;&lt;mn&gt;2.&lt;/mn&gt;&lt;mi&gt;T&lt;/mi&gt;&lt;mo stretchy=&quot;false&quot;&gt;(&lt;/mo&gt;&lt;mfrac&gt;&lt;mi&gt;n&lt;/mi&gt;&lt;mn&gt;2&lt;/mn&gt;&lt;/mfrac&gt;&lt;mo stretchy=&quot;false&quot;&gt;)&lt;/mo&gt;&lt;mo&gt;+&lt;/mo&gt;&lt;mn&gt;2&lt;/mn&gt;&lt;mo&gt;=&lt;/mo&gt;&lt;mn&gt;2.&lt;/mn&gt;&lt;mrow&gt;&lt;mo&gt;(&lt;/mo&gt;&lt;mtable rowspacing=&quot;4pt&quot; columnspacing=&quot;1em&quot;&gt;&lt;mtr&gt;&lt;mtd&gt;&lt;mn&gt;2.&lt;/mn&gt;&lt;mi&gt;T&lt;/mi&gt;&lt;mo stretchy=&quot;false&quot;&gt;(&lt;/mo&gt;&lt;mfrac&gt;&lt;mi&gt;n&lt;/mi&gt;&lt;mn&gt;4&lt;/mn&gt;&lt;/mfrac&gt;&lt;mo stretchy=&quot;false&quot;&gt;)&lt;/mo&gt;&lt;mo&gt;+&lt;/mo&gt;&lt;mn&gt;2&lt;/mn&gt;&lt;/mtd&gt;&lt;/mtr&gt;&lt;/mtable&gt;&lt;mo&gt;)&lt;/mo&gt;&lt;/mrow&gt;&lt;mo&gt;+&lt;/mo&gt;&lt;mn&gt;2&lt;/mn&gt;&lt;mo&gt;.&lt;/mo&gt;&lt;mo&gt;.&lt;/mo&gt;&lt;mo&gt;.&lt;/mo&gt;&lt;mo&gt;.&lt;/mo&gt;&lt;mo&gt;.&lt;/mo&gt;&lt;mo&gt;=&lt;/mo&gt;&lt;mfrac&gt;&lt;mrow&gt;&lt;mn&gt;3&lt;/mn&gt;&lt;mi&gt;n&lt;/mi&gt;&lt;/mrow&gt;&lt;mn&gt;2&lt;/mn&gt;&lt;/mfrac&gt;&lt;mo&gt;&amp;#x2212;&lt;/mo&gt;&lt;mn&gt;2&lt;/mn&gt;&lt;/math&gt;"><span id="MathJax-Span-142" class="math"><span id="MathJax-Span-143" class="mrow"><span id="MathJax-Span-144" class="mi">T</span><span id="MathJax-Span-145" class="mo">(</span><span id="MathJax-Span-146" class="mi">n</span><span id="MathJax-Span-147" class="mo">)</span><span id="MathJax-Span-148" class="mo">=</span><span id="MathJax-Span-149" class="mn">2.</span><span id="MathJax-Span-150" class="mi">T</span><span id="MathJax-Span-151" class="mo">(</span><span id="MathJax-Span-152" class="mfrac"><span id="MathJax-Span-153" class="mi">n</span><span id="MathJax-Span-154" class="mn">2</span></span><span id="MathJax-Span-155" class="mo">)</span><span id="MathJax-Span-156" class="mo">+</span><span id="MathJax-Span-157" class="mn">2</span><span id="MathJax-Span-158" class="mo">=</span><span id="MathJax-Span-159" class="mn">2.</span><span id="MathJax-Span-160" class="mrow"><span id="MathJax-Span-161" class="mo">(</span><span id="MathJax-Span-162" class="mtable"><span id="MathJax-Span-163" class="mtd"><span id="MathJax-Span-164" class="mrow"><span id="MathJax-Span-165" class="mn">2.</span><span id="MathJax-Span-166" class="mi">T</span><span id="MathJax-Span-167" class="mo">(</span><span id="MathJax-Span-168" class="mfrac"><span id="MathJax-Span-169" class="mi">n</span><span id="MathJax-Span-170" class="mn">4</span></span><span id="MathJax-Span-171" class="mo">)</span><span id="MathJax-Span-172" class="mo">+</span><span id="MathJax-Span-173" class="mn">2</span></span></span></span><span id="MathJax-Span-174" class="mo">)</span></span><span id="MathJax-Span-175" class="mo">+</span><span id="MathJax-Span-176" class="mn">2</span><span id="MathJax-Span-177" class="mo">.</span><span id="MathJax-Span-178" class="mo">.</span><span id="MathJax-Span-179" class="mo">.</span><span id="MathJax-Span-180" class="mo">.</span><span id="MathJax-Span-181" class="mo">.</span><span id="MathJax-Span-182" class="mo">=</span><span id="MathJax-Span-183" class="mfrac"><span id="MathJax-Span-184" class="mrow"><span id="MathJax-Span-185" class="mn">3</span><span id="MathJax-Span-186" class="mi">n</span></span><span id="MathJax-Span-187" class="mn">2</span></span><span id="MathJax-Span-188" class="mo">&minus;</span><span id="MathJax-Span-189" class="mn">2</span></span></span><span class="MJX_Assistive_MathML MJX_Assistive_MathML_Block" role="presentation">T(n)=2.T(n2)+2=2.(2.T(n4)+2)+2.....=3n2&minus;2</span></span></div>
<p>Compared to Na&iuml;ve method, in divide and conquer approach, the number of comparisons is less. However, using the asymptotic notation both of the approaches are represented by&nbsp;<strong>O(n)</strong>.</p>
<p>&nbsp;</p>
<header class="entry-header">
<h1 class="entry-title">Convex Hull using Divide and Conquer Algorithm</h1>
</header>
<div class="entry-content">
<p>A convex hull is the smallest convex polygon containing all the given points.</p>
<p><a href="https://media.geeksforgeeks.org/wp-content/uploads/Convex_hull_1.jpg"><img class="aligncenter size-full wp-image-120730" src="https://media.geeksforgeeks.org/wp-content/uploads/Convex_hull_1.jpg" alt="convexHull" width="304" height="95" /></a></p>
<p>Input is an array of points specified by their x and y coordinates. The output is the convex hull of this set of points.</p>
<p><strong>Algorithm:</strong><br />Given the set of points for which we have to find the convex hull. Suppose we know the convex hull of the left half points and the right half points, then the problem now is to merge these two convex hulls and determine the convex hull for the complete set.<br />This can be done by finding the upper and lower tangent to the right and left convex hulls. This is illustrated here&nbsp;<a href="https://www.geeksforgeeks.org/tangents-two-convex-polygons/" target="_blank" rel="noopener">Tangents between two convex polygons</a></p>
<p>Let the left convex hull be a and the right convex hull be b. Then the lower and upper tangents are named as 1 and 2 respectively, as shown in the figure.<br />Then the red outline shows the final convex hull.<br /><img src="https://media.geeksforgeeks.org/wp-content/uploads/Convex_hull_2.jpg" alt="" /><br />Now the problem remains, how to find the convex hull for the left and right half. Now recursion comes into the picture, we divide the set of points until the number of points in the set is very small, say 5, and we can find the convex hull for these points by the brute algorithm. The merging of these halves would result in the convex hull for the complete set of points.</p>
<p><strong>Note:</strong><br />We have used the brute algorithm to find the convex hull for a small number of points and it has a time complexity of&nbsp;<img class="ql-img-inline-formula quicklatex-auto-format" title="Rendered by QuickLaTeX.com" src="https://www.geeksforgeeks.org/wp-content/ql-cache/quicklatex.com-dedd15777628b0e59b72f491f270fd26_l3.svg" alt="O(n^3)" width="65" height="31" />. But some people suggest the following, the convex hull for 3 or fewer points is the complete set of points. This is correct but the problem comes when we try to merge a left convex hull of 2 points and right convex hull of 3 points, then the program gets trapped in an infinite loop in some special cases. So, to get rid of this problem I directly found the convex hull for 5 or fewer points by&nbsp;<img class="ql-img-inline-formula quicklatex-auto-format" title="Rendered by QuickLaTeX.com" src="https://www.geeksforgeeks.org/wp-content/ql-cache/quicklatex.com-dedd15777628b0e59b72f491f270fd26_l3.svg" alt="O(n^3)" width="65" height="31" />&nbsp;algorithm, which is somewhat greater but does not affect the overall complexity of the algorithm.</p>
<p>&nbsp;</p>
<h1 class="entry-title">Kruskal&rsquo;s Minimum Spanning Tree Algorithm&nbsp;</h1>
<p>Below are the steps for finding MST using Kruskal&rsquo;s algorithm</p>
<blockquote>
<p><strong>1.</strong>&nbsp;Sort all the edges in non-decreasing order of their weight.<br /><strong>2.</strong>&nbsp;Pick the smallest edge. Check if it forms a cycle with the spanning tree formed so far. If cycle is not formed, include this edge. Else, discard it.<br /><strong>3.</strong>&nbsp;Repeat step#2 until there are (V-1) edges in the spanning tree.</p>
</blockquote>
<p>The step#2 uses&nbsp;<a href="https://www.geeksforgeeks.org/union-find/">Union-Find algorithm</a>&nbsp;to detect cycle. So we recommend to read following post as a prerequisite.<br /><a href="https://www.geeksforgeeks.org/union-find/">Union-Find Algorithm | Set 1 (Detect Cycle in a Graph)</a><br /><a href="https://www.geeksforgeeks.org/union-find-algorithm-set-2-union-by-rank/">Union-Find Algorithm | Set 2 (Union By Rank and Path Compression)</a></p>
<p>The algorithm is a Greedy Algorithm. The Greedy Choice is to pick the smallest weight edge that does not cause a cycle in the MST constructed so far. Let us understand it with an example: Consider the below input graph.</p>
<p><a href="https://media.geeksforgeeks.org/wp-content/cdn-uploads/Fig-0.jpg"><img class="aligncenter size-medium wp-image-26641" title="Fig 0" src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/Fig-0-300x139.jpg" sizes="(max-width: 300px) 100vw, 300px" srcset="https://www.geeksforgeeks.org/wp-content/uploads/Fig-0-300x139.jpg 300w, https://www.geeksforgeeks.org/wp-content/uploads/Fig-0.jpg 714w" alt="" width="300" height="139" /></a></p>
<p>The graph contains 9 vertices and 14 edges. So, the minimum spanning tree formed will be having (9 &ndash; 1) = 8 edges.</p>
<pre>After sorting:
Weight   Src    Dest
1         7      6
2         8      2
2         6      5
4         0      1
4         2      5
6         8      6
7         2      3
7         7      8
8         0      7
8         1      2
9         3      4
10        5      4
11        1      7
14        3      5</pre>
<p>&nbsp;</p>
<div id="AP_G4GR_5">&nbsp;</div>
<p>&nbsp;</p>
<p>Now pick all edges one by one from sorted list of edges<br /><strong>1.</strong>&nbsp;<em>Pick edge 7-6:</em>&nbsp;No cycle is formed, include it.<br /><a href="https://media.geeksforgeeks.org/wp-content/cdn-uploads/Fig-1.jpg"><img class="aligncenter size-full wp-image-26642" title="Fig 1" src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/Fig-1.jpg" alt="" width="100" height="30" /></a></p>
<p><strong>2.</strong>&nbsp;<em>Pick edge 8-2:</em>&nbsp;No cycle is formed, include it.<br /><a href="https://media.geeksforgeeks.org/wp-content/cdn-uploads/Fig-2.jpg"><img class="aligncenter size-medium wp-image-26643" title="Fig 2" src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/Fig-2-241x300.jpg" alt="" width="90" height="125" /></a></p>
<p><strong>3.</strong>&nbsp;<em>Pick edge 6-5:</em>&nbsp;No cycle is formed, include it.<br /><a href="https://media.geeksforgeeks.org/wp-content/cdn-uploads/Fig-3.jpg"><img class="aligncenter size-medium wp-image-26644" title="Fig 3" src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/Fig-3-300x232.jpg" alt="" width="145" height="125" /></a></p>
<p><strong>4.</strong>&nbsp;<em>Pick edge 0-1:</em>&nbsp;No cycle is formed, include it.<br /><a href="https://media.geeksforgeeks.org/wp-content/cdn-uploads/Fig-4.jpg"><img class="aligncenter size-medium wp-image-26645" title="Fig 4" src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/Fig-4-300x175.jpg" alt="" width="210" height="125" /></a></p>
<p>&nbsp;</p>
<div id="AP_G4GR_6">
<div id="76621e0b-1fac-4840-ba08-8ec48d007bc6" class="_ap_apex_ad" data-section="76621e0b-1fac-4840-ba08-8ec48d007bc6" data-xpath="#AP_G4GR_6:eq(0)" data-section-id="" data-render-time="1586017187904" data-refresh-time="1586017194330" data-timeout="303">
<div id="ADP_40792_728X280_76621e0b-1fac-4840-ba08-8ec48d007bc6" data-google-query-id="CPaDrrqWz-gCFcUNaAodfrANBQ">
<div id="google_ads_iframe_/103512698/21930050695_0__container__"><iframe id="google_ads_iframe_/103512698/21930050695_0" title="3rd party ad content" name="google_ads_iframe_/103512698/21930050695_0" width="300" height="250" frameborder="0" marginwidth="0" marginheight="0" scrolling="no" data-google-container-id="5" data-load-complete="true" data-mce-fragment="1"></iframe></div>
</div>
</div>
</div>
<p>&nbsp;</p>
<p><strong>5.</strong>&nbsp;<em>Pick edge 2-5:</em>&nbsp;No cycle is formed, include it.<br /><a href="https://media.geeksforgeeks.org/wp-content/cdn-uploads/Fig-5.jpg"><img class="aligncenter size-medium wp-image-26646" title="Fig 5" src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/Fig-5-300x175.jpg" alt="" width="210" height="125" /></a></p>
<p><strong>6.</strong><em>&nbsp;Pick edge 8-6:&nbsp;</em>Since including this edge results in cycle, discard it.</p>
<p><strong>7.</strong>&nbsp;<em>Pick edge 2-3:</em>&nbsp;No cycle is formed, include it.<br /><a href="https://media.geeksforgeeks.org/wp-content/cdn-uploads/Fig-6.jpg"><img class="aligncenter size-medium wp-image-26647" title="Fig 6" src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/Fig-6-300x175.jpg" alt="" width="210" height="125" /></a></p>
<p><strong>8.</strong>&nbsp;<em>Pick edge 7-8:</em>&nbsp;Since including this edge results in cycle, discard it.</p>
<p><strong>9.</strong>&nbsp;<em>Pick edge 0-7:</em>&nbsp;No cycle is formed, include it.<br /><a href="https://media.geeksforgeeks.org/wp-content/cdn-uploads/Fig-7.jpg"><img class="aligncenter size-medium wp-image-26648" title="Fig 7" src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/Fig-7-300x175.jpg" alt="" width="220" height="125" /></a></p>
<p><strong>10.</strong>&nbsp;<em>Pick edge 1-2:&nbsp;</em>Since including this edge results in cycle, discard it.</p>
<p><strong>11.</strong>&nbsp;<em>Pick edge 3-4:</em>&nbsp;No cycle is formed, include it.<br /><a href="https://media.geeksforgeeks.org/wp-content/cdn-uploads/fig8new.jpeg"><img class="aligncenter size-medium wp-image-26649" title="Fig 8" src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/fig8new.jpeg" alt="" width="270" height="125" /></a></p>
<p>Since the number of edges included equals (V &ndash; 1), the algorithm stops here.</p>
<h1 class="entry-title">Prim&rsquo;s Minimum Spanning Tree&nbsp;</h1>
<p>&nbsp;Prim&rsquo;s algorithm is also a&nbsp;<a href="https://www.geeksforgeeks.org/archives/18528">Greedy algorithm</a>. It starts with an empty spanning tree.&nbsp;The idea is to maintain two sets of vertices. The first set contains the vertices already included in the MST, the other set contains the vertices not yet included. At every step, it considers all the edges that connect the two sets, and picks the minimum weight edge from these edges. After picking the edge, it moves the other endpoint of the edge to the set containing MST.</p>
<p><strong><em>How does Prim&rsquo;s Algorithm Work?</em></strong>&nbsp;The idea behind Prim&rsquo;s algorithm is simple, a spanning tree means all vertices must be connected. So the two disjoint subsets (discussed above) of vertices must be connected to make a&nbsp;<em>Spanning&nbsp;</em>Tree. And they must be connected with the minimum weight edge to make it a&nbsp;<em>Minimum&nbsp;</em>Spanning Tree.</p>
<p><strong><em>Algorithm</em></strong><br /><strong>1)</strong>&nbsp;Create a set&nbsp;<em>mstSet</em>&nbsp;that keeps track of vertices already included in MST.<br /><strong>2)</strong>&nbsp;Assign a key value to all vertices in the input graph. Initialize all key values as INFINITE. Assign key value as 0 for the first vertex so that it is picked first.<br /><strong>3)</strong>&nbsp;While mstSet doesn&rsquo;t include all vertices<br />&hellip;.<strong>a)</strong>&nbsp;Pick a vertex&nbsp;<em>u</em>&nbsp;which is not there in&nbsp;<em>mstSet&nbsp;</em>and has minimum key value.<br />&hellip;.<strong>b)</strong>&nbsp;Include&nbsp;<em>u&nbsp;</em>to mstSet.<br />&hellip;.<strong>c)</strong>&nbsp;Update key value of all adjacent vertices of&nbsp;<em>u</em>. To update the key values, iterate through all adjacent vertices. For every adjacent vertex&nbsp;<em>v</em>, if weight of edge&nbsp;<em>u-v</em>&nbsp;is less than the previous key value of&nbsp;<em>v</em>, update the key value as weight of&nbsp;<em>u-v.</em></p>
<p>&nbsp;</p>
</div>
</div>
</div>
</div>
