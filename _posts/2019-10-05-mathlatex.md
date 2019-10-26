---

layout: post

title: test 

tags:

- test

---

* 目录
{:toc}

數學公式

$$
\begin{align}
h(x) =& \frac{1}{\int_xt(x)\mathrm{d}x} \tag{1}\\
f(x) =& \frac{1}{\int_x\eta(x)\mathrm{d}x}g(x)\tag{2}
\end{align}
$$

$$
\begin{align}
a &= b + c \tag{3}\\
  &= d + e + f\tag{4}
\end{align}
$$

$$E=mc^2$$
\\[ \boxed{E=mc^2} \\]
\begin{equation}
    E=mc^2
\end{equation}

\newtheorem{definition }{定义}[section]
\newtheorem{theorem}{定理}[section]
\newtheorem{lemma}[theorem]{引理}
\newtheorem{corollary}[theorem]{推论}

$$
\begin{proof} [命题物质无限可分的证明]
    一尺之棰，日取其半，万世不竭。
\end{proof}
$$

流程图

<div class="mermaid">
graph TD;
A-->B;
A-->C;
B-->D;
C-->D;

</div>

时序图

<div class="mermaid">
sequenceDiagram
    participant Alice
    participant Bob
    Alice->John: Hello John,how are you?
    loop Healthcheck
        John->John: Fight against hypochondria
    end
    Note right of John: Rational thoughts <br/>prevail...
    John-->Alice: Great!
    John->Bob: How about you?
    Bob-->John: Jolly good!
</div>

甘特图

<div class="mermaid">
gantt
        dateFormat YYYY-MM-DD
        title Adding GANTT diagram functionality to mermaid
        section A section
        Completed task :done, des1, 2014-01-06,2014-01-08
        Active task :active, des2, 2014-01-09, 3d
        Future task : des3, after des2, 5d
        Future task2 : des4, after des3, 5d
        section Critical tasks
        Completed task in the critical line :crit, done, 2014-01-06,24h
        Implement parser and jison :crit, done, after des1, 2d
        Create tests for parser :crit, active, 3d
        Future task in critical line :crit, 5d
        Create tests for renderer :2d
        Add to mermaid :1d
</div>


本文共{{ page.content | number_of_words }}单词


本文共{{ page.content | strip_html | strip_newlines | split: "" | size }}字。

