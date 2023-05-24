<h2 align="center">🔢 Prime Numbers Statistical Analysis</h2>
<br />

<i><center>Let's dive into the Prime Numbers' World</center></i>

<br />

👋 Hello guys, today we will go into an advanced math topic: **Prime Numbers**. Our task here is to understand what they are, their importance and usages in real-life; understand the *Riemann Hypothesis*; make a Statistic Analysis of a dataset containing the first one million prime numbers; and play with simpy to classify numbers into primes and non-primes.

----

<h2 id='problem-description'>📝 Problem Description</h2>

<b>- Overview</b>

`Prime Numbers` are especific natural numbers that cannot be divised by other natural ones, but itself and 1. Natural numbers are those ones that are positives and integers, that is, fall into the range from 1 to positive infinite. And you may be wondering: "*Yeah, yeah, I learned about them on school. So what? What do they have that make them so special?*". You'll find it out right now!

You probably have ever heard from someone or read on the internet that you can do anything with your computer, especially if you know how to program. I am afraid, but I have bad news: That's *"bullshit"*! To a problem be considered possible to be solved by computers, it has to follow two conditions: 1) a pattern to solve the problem must exist and be possible to be implemented with a computer; and 2) the implementation should solve it in a considerable period of time using a considerable process cost. 

In Computer Science there are the **Nondeterministic Polynomial Problems (*NPs*)**, they are problems that does not follow one or both of the previous conditions, and guess what? Identifying `whether a number is prime or not` is one of them - just for curiosity, all NP problems are listed here: [List of Unsolved Problems in Mathematics](https://en.wikipedia.org/wiki/List_of_unsolved_problems_in_mathematics).

Guessing whether 5, 8, 80 and 987 are primes or not is a easy task for a computer, but when the number of digits increases, it becomes a tough task, demanding more time and process cost to solve it. For instance, consider the number 983,129,319,128,349,245,423,213,643,369,126,335,654,234,126,324,363, quite a big one, right? It would take years to be identified as prime or non-prime by a computer.

<br />

<figure>
    <img src="https://interestingengineering.com/_next/image?url=https%3A%2F%2Fimages.interestingengineering.com%2F1200x675%2Ffilters%3Aformat(webp)%2Fimages%2FNOVEMBER%2Fprime_numbers.jpg&w=1920&q=75" alt="An image containing random numbers" />
    <figcaption>Fig. 1 - Numbers. <a href="https://interestingengineering.com/science/the-incredible-importance-of-prime-numbers-in-daily-life" target="_blank"><b>Unacademy</b><sup>©</sup></a></figcaption>
</figure>

<br />

----

<b>- Cyber Security</b>

Having this in mind, Security Engineers chosen the Prime Numbers to be the base of Cyber Security Cyphers, such as `Hash Tables` and `Rivest–Shamir–Adleman (RSA) Algorithm`. In `RSA`, two large prime numbers are multiplied to result in a huge number to generate the `public and private keys` that will be used to encrypt and decrypt messages respectively. If a computer be able to decompose this huge number, the machine would be able to get the prime numbers that generated it and then, calculate the `private key` and decript any message encrypted by its public key.

If this becomes possible, the cyber-security in general would be in chaos. Imagine hackers getting access to your private messages and bank accounts. Now think bigger, picture hackers getting access to government databases and stealing and encrypting critical datas. The world would be in collapse!!

----

<b>- Riemann's Hypothesis</b>

`Riemann's Hypothesis` is a Hypothesis Equation that tells if the the number is prime or not. To our better understanding, consider the spiral below:

<br />

<figure>
    <img src="http://www.naturalnumbers.org/archspiralrnd.png" alt="Archimedean Spiral" />
    <figcaption>Fig. 2 - Archimedean Spiral. <a href="http://www.naturalnumbers.org/sparticle.html" target="_blank"><b>Michael M. Ross at naturalnumbers.org</b>©</a></figcaption>
</figure>

<br />

Now, let's fill the spiral line with numbers from 0 to infinite positive starting at the center.

<br />

<figure>
    <img src="http://www.naturalnumbers.org/numberline.png" alt="Archimedean Spiral with numbers" />
    <figcaption>Fig. 3 - Archimedean Spiral with numbers. <a href="http://www.naturalnumbers.org/sparticle.html" target="_blank"><b>Michael M. Ross at naturalnumbers.org</b>©</a></figcaption>
</figure>

<br />

Identifying the `counterclockwise`, that is, the positions where a [perfect square](https://en.wikipedia.org/wiki/Golden_spiral "Golden spiral") is formed, we'll realize that these positions are always in the east side - `1, 4, 9...`:

<br />

<figure>
    <img src="http://www.naturalnumbers.org/spiraldirection.png" alt="Archimedean Spiral counterclockwises" />
    <figcaption>Fig. 4 - Archimedean Spiral counterclockwises. <a href="http://www.naturalnumbers.org/sparticle.html" target="_blank"><b>Michael M. Ross at naturalnumbers.org</b>©</a></figcaption>
</figure>

<br />

And, after calculating the `Spiral's Product Curves`, we'll notice that all results corresponds to **Prime Numbers Positions (*Darkest Dots*)**:

<br />

<figure>
    <img src="http://www.naturalnumbers.org/numberdots.png" alt="Archimedean Spiral's Product Curves" />
    <figcaption>Fig. 5 - Archimedean Spiral's Product Curves. <a href="http://www.naturalnumbers.org/sparticle.html" target="_blank"><b>Michael M. Ross at naturalnumbers.org</b>©</a></figcaption>
</figure>

<br />

As more products we calculate, as more prime numbers we find; and tracing a sequential line on each dot position, we'll get another perfect spiral!

<br />

<figure>
    <img src="http://www.naturalnumbers.org/p+41.png" alt="Archimedean Spiral's Product Curves Lined" />
    <figcaption>Fig. 6 - Archimedean Spiral's Product Curves Lined. <a href="http://www.naturalnumbers.org/sparticle.html" target="_blank"><b>Michael M. Ross at naturalnumbers.org</b>©</a></figcaption>
</figure>

<br />

Taking this into account, Riemann Hypothesis gives an equation to calculate if the dot position of a given number fits a prime number dot in an *Archimedean Spiral*.

```python
zeta(s) = sum(1/n**s) # being n from 1 to positive infinite
```

$$
\zeta(s) = \sum_{n=1}^{\infty} \frac{1}{n^s}
$$

Even though this equation is the closest one to call as a pattern to identify prime numbers and working out for the first thousand ones, we cannot say that it is 100% correct since we cannot test it out to all existent numbers!

**OBS.:** this was a short explanation about Riemann Hypothesis, if you wanna see it deeper, I would recommend watching the [The Riemann Hypothesis, Explained](https://www.youtube.com/watch?v=zlm1aajH6gY) YouTube video from *Quanta Magazine* channel.

----

<h2 id="files-description">📁 Files Description</h2>

> **first_million_prime_numbers.csv and first_million_prime_numbers.parquet** - files containing the first million prime numbers.

> **natural_numbers.csv and natural_numbers.parquet** - files containing the numbers from one to the first million prime number.


<br />

The `.parquet` files are more suited for large datasets. In order to don't take a big section explaining the differences between CSV and Parquet files, here is a cheat sheet for you:

<br />

<figure>
    <img src="https://miro.medium.com/v2/resize:fit:828/1*lPfVDKtBBsZddmYP6fWeeA.gif" alt="Comparison between CSV, Parquet and JSON Files" />
    <figcaption>Fig. 7 - Comparison between CSV, Parquet and JSON Files. Even though Parquet files are harder to be read, they are more suitable for larger and complexes datasets. Also, you can read this type of file using any Apache tools, such as `Spark`, `Hadoop` and `Hive` or simply using the `read_parquet` function from Pandas library. <a href=https://weber-stephen.medium.com/csv-vs-parquet-vs-json-for-data-science-cf3733175176"" target="_blank"><b>Weber Stephen at Medium</b><sup>©</sup></a></figcaption>
</figure>

<br />

----

<h2 id="features">❓ Features</h2>

> **Rank** - prime number index;

> **Num | Number** - number;

> **Interval** - interval between the current and the previous prime number.

----

<h2 id="target">🌟 Target</h2>

> **Is Prime** - tells whether a number is prime (*True*) or not (*False*).

<table>
    <tr>
        <th>Is Prime</th>
        <th>Meaning</th>
    </tr>
    <tr>
        <td>True</td>
        <td>Number is prime</td>
    </tr>
    <tr>
        <td>False</td>
        <td>Number is not prime</td>
    </tr>
</table>

----

<h2 id="limitations">🛑 Limitations</h2>

As far as the dataset just contains the first million prime numbers, we cannot guarantee that this Statistical Analysis will be true for all existent ones that are not present in the dataset.

<div class="alert alert-block alert-info">
    <b>Riemann Hypothesis:</b> Keep in mind that the limitation we got here is the same one present in Riemann Hypothesis.
</div>

----

<h2 id="goals">🎯 Goals</h2>

> **Goal 1** - general statisc analysis of the dataset;

> **Goal 2** - check out for correlation between `Num` and `Interval` features;

> **Goal 3** - apply statistic tests for Hypothesis Confirmations;

> **Goal 4** - create `natural_numbers.csv` and `natural_numbers.parquet` files to store all numbers from 1 to the first million prime;

> **Goal 5** - explore the `isPrime` function from `sympy` library;

> **Goal 6** - explore the distribution of prime numbers over non-prime numbers.

----

<h2 id="setup">⚙️ Setup</h2>

> Tools

```
- Python 3.10.x version or later;
- Jupyter Lab;
- Jupyter Notebook.
```


----

> Libraries

```
- Pandas, Numpy, Matplotlib, Seaborn, Sympy and Scipy;
- Pandas Profiling and Lux API;
- Apache Spark and Java JDK version 8 or later (if you wanna use Apache Spark rather Pandas);
- Pyarrow (to generate .parquet files).
```

----

<h2 id="aknowledgements">🎉 Acknowledgements</h2>

> `first_million_prime_numbers` dataset provided by <a href="http://www.naturalnumbers.org/primes.html" target="_blank"><b>Michael M. Ross</b> in <i>naturalnumbers.org</i></a>.

> `The Riemann Hypothesis, Explained` YouTube video provided by <a href="https://www.youtube.com/watch?v=zlm1aajH6gY" target="_blank"><b>Quanta Magazine</b> channel</a>.

----

Hope you enjoyed this notebook and feel free to check out more of my projects!!

----

<h2 id='reach-me'>📫 Reach Me</h2>

> **Email** - [csfelix08@gmail.com](mailto:csfelix08@gmail.com?)

> **Linkedin** - [linkedin.com/in/csfelix/](https://www.linkedin.com/in/csfelix/)

> **GitHub:** - [CSFelix](https://github.com/CSFelix)

> **Kaggle** - [DSFelix](https://www.kaggle.com/dsfelix)

> **Portfolio** - [CSFelix.io](https://csfelix.github.io/).
