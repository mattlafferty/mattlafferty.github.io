Last time we defined the set of natural numbers $\mathbb{N}$ axiomatically using Peano's axioms. The last axiom, known as Peano's Induction Postulate, gave us a powerful proof technique called the Principle of Mathematical Induction. Let's quickly recall this technique.

Suppose for each $n\in\mathbb{N}$ we have some statement or proposition $P_n$, and we would like to show that all such propositions are true. The Principle of Mathematical Induction tells us we only have to show two things:

  1. $P_1$ is true,
  2. if $P_n$ is true, then $P_{n+1}$ is true as well.

Let's take a look at some examples.


#Induction examples

!!! example
    Prove that for all $n\in\mathbb{N}$, we have

    $$
    \sum_{k=1}^n (2k-1) ~=~n^2
    $$

**Proof:** We first want to prove that the above equality holds  when $n=1$ (the base case). We have

$$
\sum_{k=1}^1 (2k-1) ~=~ 2\cdot 1 - 1 ~=~ 1^2.
$$

So the claim is true when $n=1$.

Suppose the claim is true for some $n\in\mathbb{N}$. We want to show that it must then be true for $n+1$ as well (the induction step). We have

$$
\begin{align*}\sum_{k=1}^{n+1} (2k-1) &~=~2(n+1)-1 + \sum_{k=1}^{n} (2k-1)\\
 &~=~ 2(n+1)-1 + n^2\end{align*}
$$

with the last equality following from our assumption that the claim it true for for $n$. Finally we note that

$$
\begin{align*}
2(n+1)-1 + n^2 & ~=~ n^2 + 2n+1~=~ (n+1)^2.
\end{align*}
$$

Hence, the claim holds for $n+1$. Therefore, by the principle of mathematical induction, the equality holds for all $n\in\mathbb{N}$.

Notice that in each of the two examples that we've considered (the first of which was the example we looked at last time), in order to prove the claim is true for $n+1$ we rewrote the proposition in a way that allowed us to employ our assumption that the claim is true for $n$. For example, we wrote

$$
\underbrace{\sum_{k=1}^{n+1} (2k-1)}_{(n+1)^\mathrm{st}~\text{case}}~=~2(n+1)-1 + \underbrace{\sum_{k=1}^{n} (2k-1)}_{n^\mathrm{th}~\text{case}}.
$$

This will happen in all of your induction proofs (it's the idea that is fundamental to induction), so keep this in mind if you get stuck.



!!! example "Example \#2"
    If $0\leq a \leq 1$, prove that for all $n\in\mathbb{N}$

    $$
    (1-a)^n \geq 1-na.
    $$

??? quote "Example \#2 Proof"
    **Proof:** First we must prove the inequality holds when $n=1$. For this case we have

    $$
    (1-a)^1~=~1-a ~=~1-1\cdot a.
    $$

    Hence, the claim is in fact true when $n=1$.

    Suppose the claim holds for some $n\in\mathbb{N}$. We want to show it must then hold for $n+1$ as well. We have

    $$
    \begin{align*}(1-a)^{n+1} &~=~ (1-a)(1-a)^n\\
     &~\geq~ (1-a)(1-na)
     \end{align*}
    $$

    with the inequality following from our assumption that the claim is true for $n$. Continuing on we get

    $$
    \begin{align*}
    (1-a)(1-na)&~=~ 1-na - a + na^2\\
    &~=~ 1-(n+1)a  + na^2\\
    &~\geq~ 1-(n+1)a.\end{align*}
    $$

    Hence the claim holds for $n+1$. By the Principle of Mathematical Induction, the claim holds for all $n\in\mathbb{N}$ :fontawesome-solid-square-full: :fontawesome-solid-1:


**Proof:** First we must prove the inequality holds when $n=1$. For this case we have

$$
(1-a)^1~=~1-a ~=~1-1\cdot a.
$$

Hence, the claim is in fact true when $n=1$.

Suppose the claim holds for some $n\in\mathbb{N}$. We want to show it must then hold for $n+1$ as well. We have

$$
\begin{align*}(1-a)^{n+1} &~=~ (1-a)(1-a)^n\\
 &~\geq~ (1-a)(1-na)
 \end{align*}
$$

with the inequality following from our assumption that the claim is true for $n$. Continuing on we get

$$
\begin{align*}
(1-a)(1-na)&~=~ 1-na - a + na^2\\
&~=~ 1-(n+1)a  + na^2\\
&~\geq~ 1-(n+1)a.\end{align*}
$$

Hence the claim holds for $n+1$. By the Principle of Mathematical Induction, the claim holds for all $n\in\mathbb{N}$

:fontawesome-solid-stop:







%~~~~~~~~~~~~
\begin{mdframed}\begin{exc} Prove that for any $n\in\mathbb{N}$, it is possible to tile any $2^n\times 2^n$ grid with \emph{any} one square removed using tiles of the following shape:
\[\begin{tikzpicture}
\draw (0,0) -- (0.5,0) -- (0.5,0.5) -- (0,0.5) -- (0,0);
\draw (0,0.5) -- (0.5,0.5) -- (0.5,1) -- (0,1) -- (0,0.5);
\draw (0.5,0) -- (1,0) -- (1,0.5) -- (0.5,0.5) -- (0.5,0);
\end{tikzpicture}\]

\begin{proof} We want to first consider the base case. When $n=1$, we need to tile a $2\times 2$ grid,
\[\begin{tikzpicture}
\draw (0,0) -- (0.5,0) -- (0.5,0.5) -- (0,0.5) -- (0,0);
\draw (0,0.5) -- (0.5,0.5) -- (0.5,1) -- (0,1) -- (0,0.5);
\draw (0.5,0) -- (1,0) -- (1,0.5) -- (0.5,0.5) -- (0.5,0);
\draw (0.5,0.5) -- (1,0.5) -- (1,1) -- (0.5,1) -- (0.5,0.5);
\end{tikzpicture}\]

with any one square removed. As usual with the base case, this is not too hard to show. We have

\[\begin{tikzpicture}
\draw (0,0) -- (0.5,0) -- (0.5,0.5) -- (0,0.5) -- (0,0);
\draw (0,0.5) -- (0.5,0.5) -- (0.5,1) -- (0,1) -- (0,0.5);
\draw (0.5,0) -- (1,0) -- (1,0.5) -- (0.5,0.5) -- (0.5,0);
\draw (0.5,0.5) -- (1,0.5) -- (1,1) -- (0.5,1) -- (0.5,0.5);
\filldraw[fill=black!40!white, draw=black] (0,0) rectangle (0.5,0.5);
\filldraw[fill=black!40!white, draw=black] (0.5,0.5) rectangle (1,1);
\filldraw[fill=black!40!white, draw=black] (0.5,0) rectangle (1,0.5);
\end{tikzpicture}\hspace{.25in}\begin{tikzpicture}
\draw (0,0) -- (0.5,0) -- (0.5,0.5) -- (0,0.5) -- (0,0);
\draw (0,0.5) -- (0.5,0.5) -- (0.5,1) -- (0,1) -- (0,0.5);
\draw (0.5,0) -- (1,0) -- (1,0.5) -- (0.5,0.5) -- (0.5,0);
\draw (0.5,0.5) -- (1,0.5) -- (1,1) -- (0.5,1) -- (0.5,0.5);
\filldraw[fill=black!40!white, draw=black] (0,0) rectangle (0.5,0.5);
\filldraw[fill=black!40!white, draw=black] (0,0.5) rectangle (0.5,1);
\filldraw[fill=black!40!white, draw=black] (0.5,0) rectangle (1,0.5);
\end{tikzpicture}\hspace{.25in}\begin{tikzpicture}
\draw (0,0) -- (0.5,0) -- (0.5,0.5) -- (0,0.5) -- (0,0);
\draw (0,0.5) -- (0.5,0.5) -- (0.5,1) -- (0,1) -- (0,0.5);
\draw (0.5,0) -- (1,0) -- (1,0.5) -- (0.5,0.5) -- (0.5,0);
\draw (0.5,0.5) -- (1,0.5) -- (1,1) -- (0.5,1) -- (0.5,0.5);
\filldraw[fill=black!40!white, draw=black] (0.5,0.5) rectangle (1,1);
\filldraw[fill=black!40!white, draw=black] (0,0.5) rectangle (0.5,1);
\filldraw[fill=black!40!white, draw=black] (0.5,0) rectangle (1,0.5);
\end{tikzpicture}\hspace{.25in}\begin{tikzpicture}
\draw (0,0) -- (0.5,0) -- (0.5,0.5) -- (0,0.5) -- (0,0);
\draw (0,0.5) -- (0.5,0.5) -- (0.5,1) -- (0,1) -- (0,0.5);
\draw (0.5,0) -- (1,0) -- (1,0.5) -- (0.5,0.5) -- (0.5,0);
\draw (0.5,0.5) -- (1,0.5) -- (1,1) -- (0.5,1) -- (0.5,0.5);
\filldraw[fill=black!40!white, draw=black] (0,0) rectangle (0.5,0.5);
\filldraw[fill=black!40!white, draw=black] (0,0.5) rectangle (0.5,1);
\filldraw[fill=black!40!white, draw=black] (0.5,0.5) rectangle (1,1);
\end{tikzpicture}\]

In fact, to make our proof a bit more compact, we could have assumed without loss of generality that the removed square is the upper right-hand corner; since if this were not the case, we could simply rotate the grid.

Let $n\in\mathbb{N}$ and suppose that any $2^n\times 2^n$ grid can be tiled with exactly one square removed. We need to use this to show that any $2^{n+1}\times 2^{n+1}$ grid can also be tiled in this way. Note that any $2^{n+1}\times 2^{n+1}$ grid will be of the form:

\[\begin{tikzpicture}
\draw (0,0) -- (2,0) -- (2,2) -- (0,2) -- (0,0);
\draw (0,2) -- (2,2) -- (2,4) -- (0,4) -- (0,2);
\draw (2,0) -- (4,0) -- (4,2) -- (2,2) -- (2,0);
\draw (2,2) -- (4,2) -- (4,4) -- (2,4) -- (2,2);
\draw [decorate,decoration={brace,amplitude=10pt},xshift=-.1cm,thick]
(0,0) -- (0,2) node [black,midway,xshift=-0.7cm]
{\footnotesize $2^n$};
\end{tikzpicture}\]

We may assume without loss of generality, that the removed square is in the upper right-hand $2^n\times 2^n$ square.
\[\begin{tikzpicture}
\draw (0,0) -- (2,0) -- (2,2) -- (0,2) -- (0,0);
\draw (0,2) -- (2,2) -- (2,4) -- (0,4) -- (0,2);
\draw (2,0) -- (4,0) -- (4,2) -- (2,2) -- (2,0);
\draw (2,2) -- (4,2) -- (4,4) -- (2,4) -- (2,2);
\draw (3,3) -- (3,3.25) -- (3.25,3.25) -- (3.25,3) -- (3,3);
\end{tikzpicture}\]


Notice that each of the larger squares are $2^n\times 2^n$, and therefore can be tiled with any one square removed. In fact, we can tile the squares on the left and the square on the bottom right so that the missing square is the one touching the center.

\[\begin{tikzpicture}
%\draw (2,2) -- (4,2) -- (4,4) -- (2,4) -- (2,2);
\filldraw[fill=black!40!white, draw=black] (0,0) rectangle (4,4);
\filldraw[fill=white, draw=black] (1.75,1.75) rectangle (2,2);
\filldraw[fill=white, draw=black] (1.75,2) rectangle (2,2.25);
\filldraw[fill=white, draw=black] (2,1.75) rectangle (2.25,2);
\draw (0,0) -- (2,0) -- (2,2) -- (0,2) -- (0,0);
\draw (0,2) -- (2,2) -- (2,4) -- (0,4) -- (0,2);
\draw (2,0) -- (4,0) -- (4,2) -- (2,2) -- (2,0);
\draw (2,2) -- (4,2) -- (4,4) -- (2,4) -- (2,2);
\draw (3,3) -- (3,3.25) -- (3.25,3.25) -- (3.25,3) -- (3,3);
\filldraw[fill=white, draw=black] (3,3) rectangle (3.25,3.25);
\end{tikzpicture}\]
Since the missing squares in the center can be tiled in, we see that the claim holds for $n+1$. Therefore, by the principle of mathematical induction, it holds for all $n\in\mathbb{N}$.
\end{proof}
\end{exc}
\end{mdframed}\medskip





\noindent From the above examples it may seem that proof by induction is both powerful and foolproof. However, one needs to be careful when proving the inductive step. Let's look at a cautionary example.\bigskip


\begin{mdframed}
\begin{exc} \emph{Claim}: For each $n\in\mathbb{N}$, any group of $n$ people will have the same name.

\begin{proof}[A flawed proof.] We first consider the base case. Clearly in any group of size $1$ everyone will have the same name! As usual, the base case is easy.

Now, let $n\in\mathbb{N}$ and suppose any group of $n$ people will have the same name. We want to show that any group of people of size $n+1$ will also have the same name. Let $\{p_1,\dots, p_{n+1}\}$ denote a group of people of size $n+1$. By the induction hypothesis, the people in the group $\{p_1,\dots,p_{n}\}$ all have the same name. Similarly, the people in the group $\{p_2,\dots,p_{n+1}\}$ have the same name. Since  the people $p_1$ and $p_{n+1}$ have the same name as people in the group $\{p_2,\dots,p_{n}\}$, everyone must have the same name.
\end{proof}

So where is the mistake in this proof? In the inductive step you consider an \emph{arbitrary} $n\in\mathbb{N}$. You cannot make any assumptions about this $n$ other than the fact that it is an element of $\mathbb{N}$. In the above proof, the group of $(n+1)$ people is broken into two subsets. This first subset $$\{p_1,\dots,p_n\}$$ is obtained by excluding the person $p_{n+1}$, and the second subset  $$\{p_2,\dots,p_{n+1}\}$$ is obtained by excluding the person $p_1$. Since both of these groups are of size $n$, we know that everyone must have the same name. It is then argued that everyone in the intersection of these two sets $$\{p_1,\dots,p_n\}\cap\{p_2,\dots,p_{n+1}\}~=~\{p_2,\dots,p_n\}$$ must have the same name, and therefore the people $p_1$ and $p_{n+1}$ must also share this name. However, this intersection $\{p_2,\dots,p_n\}$ is nonempty if and only if $n\geq 2$! So we see that the above argument would fail for $n=1$ in particular.



\end{exc}
\end{mdframed}



# Overview of the course

This course is titled Analysis, which is a very vague title. Analysis of what? Well, typically this course would be titled something along the lines of (an introduction to) Real Analysis.

The *Real* in that title is due to the fact that we will restrict our attention to the real numbers, as opposed to Complex Analysis which would consider (you guessed it) the complex numbers. We will be studying the real numbers themselves, sequences and series of real numbers, and real-valued functions (functions whose outputs are real numbers). Why study these objects? Well, beyond being interesting in their own right, understanding these objects will allow us to rigorously develop the theory covered in a basic calculus course.

By rigorous, we mean that the focus in this course will be on *why* things work, whereas in previous courses, the focus was on *how* things work. For example, in calculus you learn when and *how* to apply the Chain Rule of differentiation. In this course, we will give a rigorous mathematical proof of the chain rule and in so doing (hopefully!) come to an understanding of *why* it works.

In this first chapter we will study the number systems underlying much of the subsequent theory. Namely, the set of natural numbers, rational numbers, and real numbers. We begin with the a system you've been using since you could first count, the natural numbers.



# The natural numbers

The set of natural numbers (sometimes called the counting numbers), is the set of positive whole numbers:

$$\{1,2,3,4,5,\dots\}.$$

This set is commonly denoted by $\mathbb{N}$. Some define $\mathbb{N}$ to be all non-negative integers (i.e. they include $0$), and this is a perfectly fine choice to make. Doing so results in only cosmetic changes to what we are about to discuss.


Now, you're no doubt familiar with the natural numbers and very adept at using them, however, we want to define $\mathbb{N}$ axiomatically. What this means that we will give a minimal list of statements (axioms) that describe $\mathbb{N}$ uniquely. These axioms are known as Peano's axioms, and we begin with the most basic:

!!! note "Axiom 1 (A1)"
    $1$ is an element of $\mathbb{N}$.

Note that if we had defined the natural numbers to be all *non-negative* integers, the $1$ in the above axiom would be replaced by a $0$. Obviously, we need more than just one element on our set $\mathbb{N}$, and to define the other elements we will employ the next axiom:

!!! note "Axiom 2 (A2)"
    If $n$ is an element of $\mathbb{N}$, its *successor* $n+1$ is an element of $\mathbb{N}$.


If we're being truly rigorous here, you might notice that we're cheating a bit - we haven't defined what $+$ means! However, we'll skip over this for the moment. So what do we have thus far? Well, we know that $1$ is an element of $\mathbb{N}$ by **A1**, and **A2** tells us that $2=1+1$ is an element of $\mathbb{N}$. Since $2$ is an element of $\mathbb{N}$ (which we denote by $2\in\mathbb{N}$) we can employ **A2** once again to see that $2+1=3 \in \mathbb{N}$. You can see where we're going here. So are we done? Do **A1** and **A2** completely define $\mathbb{N}$?

!!! example "Exercise"
    Can you come up with a set of numbers $S$ that satisfies the above axioms, but is not $\mathbb{N}$?

If you attempted the above exercise, you may have realized that there are a many possible sets that are not $\mathbb{N}$, but satisfy **A1** and **A2**. Let's consider a few of example sets to help motivate our remaining axioms. Keep in mind that some of these examples are *not* obvious, and you wouldn't be expected to come up with them on your own.

1. The axioms **A1** and **A2** do not preclude the possibility of non-positive numbers being elements of $\mathbb{N}$. For example, the set of all whole numbers (also known as the integers) $\{\dots,-3,-2,-1,0,1,2,3,\dots\}$ satisfies both **A1** and **A2**, but clearly this set is not $\mathbb{N}$.

2. The next example is a somewhat pathological possibility that you may not have considered.  Suppose we have the set $\{1,2,\alpha,3,4,5,\dots\},$ where $\alpha + 1 = 3$ and $\alpha \neq 2$. Notice that this set satisfies **A1** and **A2**, but such an element $\alpha$ is not a member of $\mathbb{N}$.

3. Finally, consider the set $\left\{1,\frac{3}{2},2,\frac{5}{2}, 3, \frac{7}{2},\dots\right\}.$ While this set is not $\mathbb{N}$, you can verify that it satisfies  **A1** and **A2**.




We will introduce three more axioms that will address the above examples. Let's start with the first example. To preclude non-negative numbers in our set, we consider the following axiom:

!!! note "Axiom 3 (A3)"
    $1$ is not the successor of any element of $\mathbb{N}$.

Before moving on, take a moment to think about how would these first three axioms would have to be changed if we defined $\mathbb{N}$ to include 0, that is, if we defined $\mathbb{N}=\{0,1,2,3,\dots\}$.

Note that the pathological possibility given in example 2 still satisfies **A1**, **A2**, and **A3**. The issue that this example is illustrating is that our axioms do not preclude two distinct elements of $\mathbb{N}$ from sharing the same successor! We can remove this possibility with the following axiom:\bigskip

!!! note "Axiom 4 (A4)"
    If $n$ and $m$ have the same successor, then $n=m$.

Finally, we consider example 3. You should verify that the set in example 3 satisfies **A1**, **A2**, **A3**, and **A4**. Our final axiom will remove the possibility that there are additional, unwanted numbers in our set $\mathbb{N}$, and do so in a very clever way.

!!! note "Axiom 5 (A5 - Peano's Induction Postulate)"
    Let $S$ be a set. If

      1. $1$ is an element of $S$, and
      2. $n+1$ is an element $S$ whenever $n$ is,

    then $\mathbb{N}$ is a subset of $S$, which we denote $\mathbb{N}\subset S$.

You're probably asking yourself how the above axiom finally nails down $\mathbb{N}$. Well, by **A1** and **A2** we know that the set $\{1,2,3,4,\dots\}$ is contained in $\mathbb{N}$, that is,

$$
\{1,2,3,4,\dots\}~\subset~\mathbb{N}.
$$

In fact, this is the only set that we can conclude is contained in $\mathbb{N}$ from **A1** and **A2**. That is, while the previous axioms do not *preclude* a set such as

$$
\left\{1,\frac{3}{2},2,\frac{5}{2}, 3, \frac{7}{2},\dots\right\},
$$

from being contained in $\mathbb{N}$, they do not go so far as to say that such a set is contained in $\mathbb{N}$. Now, the last axiom **A5** gives us the inclusion

$$
\mathbb{N}~\subset~\{1,2,3,4,\dots\}.
$$

If we put these two inclusions together, we see that

$$
\mathbb{N} ~=~ \{1,2,3,4,\dots\}.
$$

These five axioms uniquely define the natural numbers $\mathbb{N}$. While we won't employ the first four very often, the last axiom is a very powerful tool.



# The principle of induction

Often in mathematics, you find yourself with list of statements or propositions $P_1$, $P_2$, $P_3$, $\dots$, which you would like to prove are all true. For example, for each natural number $n$ (which we can write more succinctly as $n\in\mathbb{N}$), let $P_n$ be the proposition that the following equality is true:

$$
\sum_{k=1}^n k ~=~\frac{n(n+1)}{2}.
$$

While determining if the above equality is true for a specific $n$, say $n=5$, is easy enough, how would you go about proving that the equality holds for *all* $n$?

Note that another way of saying that the propositions $P_1$, $P_2$, $P_3$, $\dots$, are true, would be to say that the set of $n$ for which $P_n$ is true, is all of $\mathbb{N}$. Or notationally,

$$
\{n\in \mathbb{N} : P_n\text{ is true}\} ~=~ \mathbb{N}.
$$

By **A5**, in order to show the above equality we just need to show two things:

  1. $P_1$ is true,
  2. If $P_n$ is true, then $P_{n+1}$ is true.

If we prove the above two statements, then **A5** tells us that

$$
\mathbb{N}\subset \{n\in \mathbb{N} : P_n\text{ is true}\}.
$$


However, we already know that the opposite inclusion holds, that is,

$$
\{n\in \mathbb{N} : P_n\text{ is true}\}\subset \mathbb{N}.
$$

When we put the above inclusions together, we get

$$
\mathbb{N}~=~ \{n\in \mathbb{N} : P_n\text{ is true}\}!
$$

This proof technique is called the Principle of Mathematical Induction, and it is both simple and powerful.

Let's see this technique in action by considering the example given above.

!!! example "Exercise"
    Prove that for all $n\in \mathbb{N}$,

    $$
    \sum_{k=1}^n k~=~ \frac{n(n+1)}{2}.
    $$

**Proof:**
We first want to prove that the above equality holds when $n=1$. This is typically referred to as the *base case*. We have,

$$
\sum_{k=1}^1 ~=~ 1 ~=~ \frac{1(1+1)}{2}.
$$

Hence, the base case it true.

Next, suppose the equality holds for $n$. We will use this to show that it must hold for $n+1$ as well. This is typically referred to as the *induction step*. We have

$$
\begin{align*}
\sum_{k=1}^{n+1} k &~=~ (n+1) + \sum_{k=1}^{n} k
~=~ (n+1) + \frac{n(n+1)}{2}
~=~ \frac{(n+1)(n+2)}{2}.
\end{align*}
$$

Hence, if the equality holds for $n$, it also holds for $n+1$. By the principle of mathematical induction, we see that the equality must hold for all $n\in \mathbb{N}$.




We'll look at several more examples of the proofs using the principle of mathematical induction in the next lecture.
