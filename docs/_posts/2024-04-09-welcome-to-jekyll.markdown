---
layout: post
title:  "Welcome to Jekyll!"
date:   2024-04-09 19:05:41 -0400
categories: jekyll update
---
You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. You can rebuild the site in many different ways, but the most common way is to run `jekyll serve`, which launches a web server and auto-regenerates your site when a file is updated.

Jekyll requires blog post files to be named according to the following format:

`YEAR-MONTH-DAY-title.MARKUP`

Where `YEAR` is a four-digit number, `MONTH` and `DAY` are both two-digit numbers, and `MARKUP` is the file extension representing the format used in the file. After that, include the necessary front matter. Take a look at the source for this post to get an idea about how it works.

Jekyll also offers powerful support for code snippets:

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/

# Problem 1
### Part A
$$
\sum\limits_{j=1}^{n} p_{j} |\psi_{j} \times \psi_{j}|
$$
$$
\frac{1}{|B|}
\begin{bmatrix}
1 & 0 & 0 & ... & 0 \\ 
0 & 1 & 0 & ... & 0 \\ 
0 & 0 & 1 & ... & 0 \\ 
\vdots &   &   & \ddots & \vdots \\ 
0 & 0 & 0 & ... & 1
\end{bmatrix} = \frac{1}{|B|} I
$$
### Part B

1. By part (i), we know that the probability of a basis state being chosen is 1/B
2. The problem states that we are sampling from an orthonormal basis, so the inner product of any two vectors within the basis is 0.
3. Therefore, the basis states will always have a single 1, and the rest will be 0's.
4. Because the states are orthonormal, a single row in the density matrix will only have a single 1, with the rest being 0's as well
5. when taking the inner product, we will find that the matrix has a single entry at j, j

### Part C
##### part 1
It remains the same
$$
p \mapsto U p U^{\dagger}
$$
$$
\begin{align*}
UpU^{\dagger} &= U \left(\frac{1}{|B|} \sum\limits_{j=1}^{n} \ket{j}\bra{j} \right) U^{\dagger} \\
&=  \frac{1}{|B|} \sum\limits_{j=1}^{n} U\ket{j}\bra{j}U^{\dagger} \\
&= \frac{1}{|B|}  \sum\limits_{j=1}^{n} \ket{j}\bra{j}
\end{align*}
$$
unitary operators preserve the inner product

##### arbitrary measurements
It collapses. the probabilities are equal, so it will fall into any of the vector states in the basis with $\frac{1}{|B|}$ probability each

basically the same, when measuring, regardless of the measurement, you will have a 1/B probability of any measurement with a post measurement state of vector i

# Problem 2
### Part A
You cannot send an instantaneous yes/no message because you cannot transmit information faster than the speed of light.
Trying to change Alice's qubit will not affect Bob's qubit
If Alice measures her qubit, Bob's qubit will collapse, but he cannot gain any information about his qubit until he measures it.

Bob's qubit before Alice measures:
$$
\frac{1}{\sqrt{2}} (\ket{0}_{B} + {\ket{1}_B})
$$
This can be represented by the mixed state by applying the projectors
$$
\begin{align*}
\sum\limits_{j=1}^{n} p_{j} |\psi_{j} \times \psi_{j}|
\end{align*}
$$
To acquire the probabilities, we just have have to take the norm squared of $\alpha$ 
$$
|| \frac{1}{\sqrt{2}} || = \frac{1}{2}
$$
Thus, we acquire the mixed state
$$
p = \frac{1}{2}(\ket{0}\bra{0} + \ket{1}\bra{1}) = \frac{1}{2}I
$$

This is because the probability of Bob's qubit measuring as 0 or 1 is 1/2 each.

Bob's qubit after Alice measures:

Let's look at the post measurement states that Alice has after measuring
$$
\alpha \ket{\phi_{1}}, \beta \ket{\phi_{2}}
$$

Take the expectation over post measurement states
$$
p' = \sum\limits_{i=1}^{j}Pr(p'_{j}) p'_{j}
$$
$$
p'_{j} = \frac{\pi_{j}p\pi_j}{Tr[\pi_{j}p]}
$$
Prove that the post measurement states are the outer product of the projects
$$
\begin{align*}
p'_{j} &=  \frac{\pi_{j}p\pi_j}{Tr[\pi_{j}p]} \\
&= \frac{\pi_{j} \frac{1}{2}I \pi_j}{Tr[\pi_{j} \frac{1}{2}I]}\\
&= \begin{bmatrix} 
\pi_{j, 0, 0} & 0\\
0 & \pi_{j, 1, 1}
\end{bmatrix}
\end{align*}
$$

### You know what, lets move on
Bob does not gain any information. Bob is unaware of Charlie's qubit in the first place. Even if Charlie's qubit is entangled with Bob's qubit, it will not affect Bob's measurement of his qubit if he chooses to measure it before the classical message arrives.

Alice's and Charlie's entangled pair will be projected onto one of the bell states, but similar to part A, the mixed state will remain the same.


# Problem 3
This is stupid wtf






# Problem 4
### Part A
$$
\begin{align*}
p &= \sum\limits_{j=0}^{n} p_{j} |\psi_{j} \times \psi_{j}|\\
&= \frac{1}{3}\sum\limits_{j=0}^{2} \ket{j}\bra{j} \\
&= \frac{1}{3}\left( \ket{0}\bra{0} +  \ket{1}\bra{1} + \ket{2}\bra{2}\right)\\
&= \frac{1}{3}I
\end{align*}
$$
### Part B
$$
\begin{align*}
p &= \sum\limits_{j=0}^{n} p_{j} \left(|\psi_{j} \times \psi_{j}| \otimes |\psi_{j} \times \psi_{j}|\right)\\
&= \frac{1}{3}\sum\limits_{j=1}^{n} \ket{j}\bra{j} \otimes \ket{j}\bra{j}\\
&= \frac{1}{3}\left( \ket{0}\bra{0} \otimes \ket{0}\bra{0} +  \ket{1}\bra{1} \otimes \ket{1}\bra{1}+ \ket{2}\bra{2}  \otimes \ket{2}\bra{2}\right)\\
&= \frac{1}{3} 
\begin{bmatrix}
1 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0\\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0\\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0\\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & 1 & 0 & 0 & 0 & 0\\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0\\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0\\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0\\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 1
\end{bmatrix}
\end{align*}
$$

### Part C
i.
The superposition state is
$$
\ket{j} = \frac{1}{\sqrt{3}}(\ket{0} + \ket{1} + \ket{2})
$$
Since the only state we can choose is $\ket{j}$, the summation is ignored
$$
\begin{align*}
p_{A} &= \sum\limits_{j=0}^{n} p_{j} |\psi_{j} \times \psi_{j}|\\
&=\ket{j}\bra{j}\\
&= \frac{1}{3}\left(\ket{0}_{A}\bra{0} + \ket{0}_{A}\bra{1} + \ket{0}_{A}\bra{2} + \ket{1}_{A}\bra{0} + \ket{1}_{A}\bra{1} + \ket{1}_{A}\bra{2} + \ket{2}_{A}\bra{0} + \ket{2}_{A}\bra{1} + \ket{2}_{A}\bra{2}\right)\\
&= \frac{1}{3} \begin{bmatrix}
1 & 1 & 1\\
1 & 1 & 1\\
1 & 1 & 1
\end{bmatrix}
\end{align*}
$$
ii. 
$$
p_{B} = \begin{bmatrix}
1 & 0 & 0 \\ 0 & 0 & 0 \\ 0 & 0 & 0
\end{bmatrix}
$$
iii. 
The modular 3 operation isn't too significant here.
y + x will always equal x, since y is 0.
Entanglement occurs and the second qubit matches the 1st qubit
Therefore, the gate returns the combined superposition state
$$
\frac{1}{\sqrt{3}}(\ket{00}_{AB} + \ket{11}_{AB} + \ket{22}_{AB})
$$
The combined state is
$$
\begin{align*}
p_{AB} &= \ket{jj} \bra{jj} \\
&= \frac{1}{3}\left(\ket{00}_{AB}\bra{00} + \ket{00}_{AB}\bra{11} + \ket{00}_{AB}\bra{22} + \ket{11}_{AB}\bra{00} + \ket{11}_{AB}\bra{11} + \ket{11}_{AB}\bra{22} + \ket{22}_{AB}\bra{00} + \ket{22}_{AB}\bra{11} + \ket{22}_{AB}\bra{22}\right)\\
&= \frac{1}{3} 
\begin{bmatrix}
1 & 0 & 0 & 0 & 1 & 0 & 0 & 0 & 1\\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0\\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0\\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\
1 & 0 & 0 & 0 & 1 & 0 & 0 & 0 & 1\\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0\\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0\\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0\\
1 & 0 & 0 & 0 & 1 & 0 & 0 & 0 & 1
\end{bmatrix}
\end{align*}
$$
### Part D
The two qubit state is
$$
\frac{1}{\sqrt{3}}(\ket{00}_{AB} + \ket{11}_{AB} + \ket{22}_{AB})
$$
$$
\begin{align*}
Tr_{B}[p_{AB}] &=  \sum\limits_{a, a'} \left( \sum\limits_{b} p_{aa'bb} \right) |a \times a'|\\
&= \frac{1}{3} ( 1 \cdot |0 \times 0|_{A} + 0 \cdot |0 \times 1|_{A} + 0 \cdot |0 \times 2|_{A}\\
&+  0 \cdot |1 \times 0|_{A} + 1 \cdot |1 \times 1|_{A} + 0 \cdot |1 \times 2|_{A} \\
&+ 0 \cdot |2 \times 0|_{A} + 0 \cdot |2 \times 1|_{A} + 1 \cdot |2 \times 2|_{A})\\
&= \frac{1}{3} I_{A}
\end{align*}
$$
# Problem 5
### Part A
When A is prepared as a mixed state, we know that the trace equals 1. We have to find out the post measurement state.

$$
p'_{A} = \frac{\pi_{j}p\pi_j}{Tr[\pi_{j}p]}
$$
We also know that
$$
P(j) = Tr[\pi_{j}p_{A}]
$$
We also know that the post measurement state will often be the applied operator $\pi_{j}$
Measuring essentially measures how much we are in a the project, you know

I'm assuming 0-indexing because its weird to have a basis without 0?
We know that the basis vectors are $\ket{0}, \ket{1},..., \ket{n-1}$
$|j \times j|$ will result in a n by n matrix where only the value at j, j will be 1, and the rest are 0. From this, we know that the trace is $p'_{A, j, j}$


Applying the projector on both sides of $p_{A}$ preserves only the element at j, j. The element is preserved because the project multiplies the element by 1.
Applying all projectors will only keep elements when the row index is the same as the column index
ill just guess its p_A

Yea ill just use expected value and hope that works out
### Part B
I am absolutely guessing here, but the fact that we measure ensures that that B cannot be in a superposition. Regardless, A was a mixed state, so B would be a mixed state as well. B should be A