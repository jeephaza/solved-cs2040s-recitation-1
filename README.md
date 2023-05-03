Download Link: https://assignmentchef.com/product/solved-cs2040s-recitation-1
<br>
<strong>Problem 1.           Order of Growth (Review)</strong>

<strong>Problem 1.a.             </strong>Consider the following function isPrime for checking if an integer <em>n </em>is prime:

public static boolean isPrime(int n) { if (n&lt;2) { return false;

} for (int i=2;i&lt;n;i++){ if (isDivisible(n,i)) { return false;

} } return true;

}

What is the order of growth for isPrime given the following order of growths for isDivisible(n,i)?

<ol>

 <li>Time: <em>O</em>(1), Space <em>O</em>(1)</li>

 <li>Time: <em>O</em>(<em>n</em>), Space <em>O</em>(<em>n</em>)</li>

 <li>Time: <em>O</em>(<em>n</em>), Space <em>O</em>(1)</li>

 <li>Time: <em>O</em>(<em>i</em>), Space <em>O</em>(1)</li>

</ol>

<strong>Problem 1.b. </strong>Next, consider the following function isPrime2 for checking if an integer <em>n </em>is prime:

public static boolean isPrime2(int n) { if (n&lt;2) { return false;

} for (int i=2;i&lt;sqrt(n);i++){ if (isDivisible(n,i)) { return false;

} } return true;

}

What is the order of growth for isPrime2 given the following order of growths for isDivisible(n,i)?

<ol>

 <li>Time: <em>O</em>(<em>n</em>), Space <em>O</em>(1)</li>

 <li>Time: <em>O</em>(<em>i</em>), Space <em>O</em>(1)</li>

</ol>

<strong>Problem 1.c. </strong>Consider yet another variant of an algorithm to check if an integer <em>n </em>is prime that we call isPrime3 below:

public static boolean isPrime3(int n) { if (n&lt;2) { return false;

} for (int i=2;i&lt;=sqrt(n);i++){ if (isPrime3(i) &amp;&amp; isDivisible(n,i)) { return false;

} } return true;

}

We are simulating the Sieve of Eratosthenes (see <a href="https://en.wikipedia.org/wiki/Sieve_of_Eratosthenes">https://en.wikipedia.org/wiki/Sieve_of_ </a><a href="https://en.wikipedia.org/wiki/Sieve_of_Eratosthenes">Eratosthenes</a><a href="https://en.wikipedia.org/wiki/Sieve_of_Eratosthenes">)</a>. How does the performance of isPrime3 compare to isPrime2?

You can assume that the order of growth for isDivisible(n,i) is <em>O</em>(1).

<strong>Problem 1.d.</strong>

<ol>

 <li>Is log<sub>2</sub>(<em>n</em>) = <em>O</em>(log(<em>n</em>))?</li>

 <li>Is 2<sup>2<em>n </em></sup>= <em>O</em>(2<em><sup>n</sup></em>)?</li>

</ol>

<strong>Problem 2.            How Much Do You Make?</strong>

<em>Learning objectives:</em>

<ol>

 <li>How do we make an algorithmic question precise?</li>

 <li>Metrics: what makes a solution a good solution? How do we measure goodness?</li>

 <li>Problem solving: how to iterate a solution?</li>

</ol>

A group of graduating CS students got offered well-paying jobs. They all want to know the market rate (average salary), but they do not want to tell anyone their own salary. (No one wants to brag or be embarrassed!) What should they do?

<strong>Problem 2.a. </strong>Come up with an algorithm that will allow the students to determine the average pay of the group without revealing their own salaries to any of the other members in the group.

If we want to evaluate how good our algorithm is, what metrics should we use? Realize that when evaluating an algorithm, it isn’t always obvious what metrics we care about, and you have to think hard to make sure you are optimizing the right thing!

<em>ProTip: </em>The choice of metrics should provide an good measure of how well the chosen objective is met. Metrics therefore drives the solution. You may be looking at multiple metrics at once, which is in the case where you are optimizing for multiple objectives. Often times, a single total metric can be obtained by linearly combining multiple metrics via weighing the relative importance of the objectives they correspond to.

<strong>Problem 2.b. </strong>Now think about what happens if <em>k </em>members of the group decide to collude and share information. Is your algorithm still able to preserve the privacy of all the members, or could the salary for some of the members be leaked?

If there is a possibility for privacy to be compromised, modify your proposed algorithm to “fix” this leak.

How well does your new algorithm perform? Is that the best we can do? Can you do even better? What is the best that we can do?

<strong>Problem 2.c. </strong>We had earlier assumed that all the participants in the group are all honest. Suppose that one of the group members is a saboteur who wants to mislead the rest by submitting a salary that is many times higher or lower than the actual salary. You can assume that the salaries have a normal distribution with a “reasonable” variance. This saboteur would introduce a salary point that will appear as an outlier in the full data set. What if instead of just 1 saboteur, we had a small number <em>s </em>of them?

Given your proposed algorithm, how else could a saboteur decide to do to cause inaccuracies in the results?