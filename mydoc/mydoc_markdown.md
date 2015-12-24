---
title: Markdown
tags: [tool]
keywords: "syntax, markdown"
last_updated: "December 25, 2015"
summary: "blur blur blur"
published: true
---

## Markdown Syntax

나는 김학진입니다. \\(abcdefg\\) 어쩌구 $$abc$$

$$a^2 + b^2 = c^2$$

{% gist hakchin/a29ed23af7aa58a6764c %}

![http://uml.mvnsearch.org/gist/a29ed23af7aa58a6764c](http://uml.mvnsearch.org/gist/a29ed23af7aa58a6764c)


### External Image
![](http://logdown.com/images/logo.png)

![oneM2M](http://img.etnews.com/ict/2013/term/image_020130329141422.jpg)

<a title="Chinese and Korean History Timeline.xlsx" href="https://www.flickr.com/photos/44489836@N06/22647903164/in/dateposted-public/"><img src="https://farm6.staticflickr.com/5767/22647903164_27c901b173_z.jpg" alt="Chinese and Korean History Timeline" width="640" height="620" /></a>


### External Video

* youtube in wordpress.com

[youtube https://www.youtube.com/watch?v=dj-x8_7VULc&amp;w=854&amp;h=480]


### plantuml

{% gist hakchin/a29ed23af7aa58a6764c %}

![http://uml.mvnsearch.org/gist/a29ed23af7aa58a6764c](http://uml.mvnsearch.org/gist/a29ed23af7aa58a6764c)



### Bloging with code snippet:

`inline code`

#### Plain Code

```
puts "Hello World!"
```

#### Code with Language

```ruby
puts "Hello World!"
```

### MathJax in Markdown

* [mathjax with jekyll-nice!!](http://gastonsanchez.com/blog/opinion/2014/02/16/Mathjax-with-jekyll.html)


#### Mathjax

```
$$ x = \dfrac{-b \pm \sqrt{b^2 - 4ac}}{2a} $$
```

$$ x = \dfrac{-b \pm \sqrt{b^2 - 4ac}}{2a} $$


#### Inline Mathjax

The answser is \\(a^2 + b^2 = c^2\\).

* inline \\(\dfrac{a}{b}\\) and not inline

$$ \dfrac{a}{b} $$

### Table Example

| Tables | Are | Cool |
| ------------- |:-------------:| -----:|
| col 1 | Hello | $1600 |
| col 2 | Hello | $12 |
| col 3 | Hello | $1 |

### Table Example by Hakchin

#### 1년 이내에 이루고 싶은 10가지 목표 (2017년)

| No. | S | T | Timely | Target | Remarks |
| ---------- |:-----:|:---:|:------:|:-----------------------------|---------:|
| 01 | O | O |99991231|123456789012345 |12345 |
| 02 | O | O | | | |
| 03 | O | O | | | |
| 04 | O | O | | | |
| 05 | O | O | | | |
| 06 | O | O | | | |
| 07 | O | O | | | |
| 08 | O | O | | | |
| 09 | O | O | | | |
| 10 | O | O | | | |

Specific: 구체적으로 작성한다.
Target: 목표물이 명확해야 한다.
Achievable: 성취 가능해야 한다.
Realistic: 실현 가능해야 한다.
Timely: 시기 적절하게 기한을 정한다.

### External Image Link Example by Hakchin
![](http://img.etnews.com/ict/2013/term/image_020130329141422.jpg)

### 수식 Example by Hakchin

$$ C = E_K(P) $$

$$ P = D_K(C) $$
* P: Plain text, 평문
* E: Encryption
* C: Cryptotext, 암호문
* D: Decryption

### snippet Example by Hakchin
```
For MacVim and Windows Gvim, simply add the following to your ~/.vimrc:
set clipboard=unnamed
```

***

## R Markdown

### Getting Started
* [Markdown by Hakchin](https://hakchin.wordpress.com/2015/12/04/markdown)
* [An Example R Markdown](http://www.statpower.net/Content/310/R%20Stuff/SampleMarkdown.html)
* [http://blog.naver.com/edgelab/220218470395](http://blog.naver.com/edgelab/220218470395)
* [An Introduction to R Markdown](http://rpubs.com/mansun_kuo/24330)

### markdown cheatsheet

* [Markdown quick reference by wordpress](https://en.support.wordpress.com/markdown-quick-reference/)
* [stackedit](https://stackedit.io/editor)
* [Mastering Markdown](https://guides.github.com/features/mastering-markdown)
* [markdown cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)
* [Some examples of using \\(\LaTeX\\) in R Markdown documents](http://www.calvin.edu/~rpruim/courses/m343/F12/RStudio/LatexExamples.html)


### markdown at atom

### preview

ctrl-shift-m.

### R Markdown 따라하기

### 참조 문서
* [Serve Jekyll Websites with servr and knitr](http://yihui.name/knitr-jekyll/2014/09/jekyll-with-knitr.html)
* [Wordpress에서 Jekyll로…](http://wsyang.com//r/2015/07/26/Goodbye-wordpress-hellow-Jekyll/)

### R 화면에서

> setwd("/Users/sn2ro/OneDrive/git-c/hakchin.github.io")
> servr::jekyll(command = '/Users/sn2ro/.rbenv/shims/jekyll build --watch')



## Rmarkdown
This is an R Markdown document. Markdown is a simple formatting syntax for authoring HTML, PDF, and MS Word documents. For more details on using R Markdown see <http://rmarkdown.rstudio.com>.

When you click the **Knit** button a document will be generated that includes both content as well as the output of any embedded R code chunks within the document. You can embed an R code chunk like this:

```r
summary(cars)
```

```
## speed dist
## Min. : 4.0 Min. : 2.00
## 1st Qu.:12.0 1st Qu.: 26.00
## Median :15.0 Median : 36.00
## Mean :15.4 Mean : 42.98
## 3rd Qu.:19.0 3rd Qu.: 56.00
## Max. :25.0 Max. :120.00
```

You can also embed plots, for example:

![unnamed-chunk-2-1.png](http://user-image.logdown.io/user/14781/blog/13978/post/303787/QrcGNegSRX6KfwiGrtFU_unnamed-chunk-2-1.png)

Note that the `echo = FALSE` parameter was added to the code chunk to prevent printing of the R code that generated the plot.

### Key Formatting Constructs
The key formatting constructs are discussed at . You can see above how I constructed main section headings. Now I’m going to create a series of sections using secondary headings.

#### Emphasis
This is italic. This is bold.

#### Superscripts

This is $$y^2$$.

#### Lists
##### Unordered
* Item 1
* Item 2
  * Item 2a
  * Item 2b

##### Ordered
1. Item 1
1. Item 2
1. Item 3
  1. Item 3a
  1. Item 3b

#### Block Quotes
A friend once said:

> It’s always better to give than to receive.

#### Displaying Blocks of Code Without Evaluating

In some situations, you want to display R code but not evaluate it. Here is an example of how you format.

```
This text is displayed verbatim / preformatted
```

#### Displaying R Code Inline in a Sentence
Sometimes, you need to include an R name or command inline in a sentence. Here is how your format it.

The `sqrt` function computes the square root of a number.

#### Evaluating and Inserting R Code in a Sentence
Sometimes, you want a result without showing the user that you used R to get it. Here is an example.

The mean of the numbers 2,3,4 is 3.

There are lots of ways you can exploit this capability. You can do more advanced calculations in a hidden code block, assign the results to variables, and then simply use the variable names to insert the results in a sentence.

In the following example, I compute the sum of the integers from 2 to 19 in a hidden code block. Then I display the result inline.

The sum of the integers from 2 to 19 is 189.

### Typesetting Equations
#### Inline vs. Display Material
Equations can be formatted inline or as displayed formulas. In the latter case, they are centered and set off from the main text. In the former case, the mathematical material occurs smoothly in the line of text.

In order to fit neatly in a line, summation expressions (and similar constructs) are formatted slightly differently in their inline and display versions.

Inline mathematical material is set off by the use of single dollar-sign characters. Consequently, if you wish to use a dollar sign (for example, to indicate currency), you need to preface it with a back-slash. The following examples, followed by their typeset versions, should make this clear

```
This summation expression $\\(\sum_{i=1}^n X_i \\) appears inline.
```

This summation expression \\(\sum_{i=1}^n X_i \\) appears inline.

```
This summation expression is in display form.

$$ \sum_{i=1}^n X_i $$
```



This summation expression is in display form.

$$\sum_{i=1}^n X_i $$





### Some LaTeX Basics
In this section, we show you some rudiments of the LaTeX typesetting language.

#### Subscripts and Superscripts
To indicate a subscript, use the underscore `_` character. To indicate a superscript, use a single caret character ^. Note: this can be confusing, because the R Markdown language delimits superscripts with two carets. In LaTeX equations, a single caret indicates the superscript.

If the subscript or superscript has just one character, there is no need to delimit with braces. However, if there is more than one character, braces must be used.

The following examples illustrate:
```
$$X_i$$
$$X_{i}$$
```
$$ X_i $$

$$ X_{i} $$

Notice that in the above case, braces were not actually needed.

In this next example, however, failure to use braces creates an error, as LaTeX sets only the first character as a subscript

```
$$X_{i,j}$$
$$X_i,j$$
```
$$ X_{i,j} $$

$$ X_i,j $$
Here is an expression that uses both subscripts and superscripts
```
$$X^2_{i,j}$$
```
$$ X^2_{i,j} $$

#### Square Roots
We indicate a square root using the `\sqrt` operator.
```
$$\sqrt{b^2 - 4ac}$$
```
$$ \sqrt{b^2 - 4ac} $$

#### Fractions
Displayed fractions are typeset using the `\frac` operator.
```
$$\frac{4z^3}{16}$$
```
$$ \frac{4z^3}{16} $$

#### Summation Expressions
These are indicated with the `’ operator, followed by a subscript for the material appearing below the summation sign, and a superscript for any material appearing above the summation sign.

Here is an example.

```
$$\sum_{i=1}^{n} X^3_i$$
```
$$ \sum_{i=1}^{n} X^3_i $$

#### Self-Sizing Parentheses
In LaTeX, you can create parentheses, brackets, and braces which size themselves automatically to contain large expressions. You do this using the `\left` and `\right` operators. Here is an example
```
$$\sum_{i=1}^{n}\left( \frac{X_i}{Y_i} \right)$$
```
$$ \sum_{i=1}^{n}\left( \frac{X_i}{Y_i} \right) $$

#### Greek Letters
Many statistical expressions use Greek letters. Much of the Greek alphabet is implemented in LaTeX, as indicated in the LaTeX cheat sheet available at the course website. There are both upper and lower case versions available for some letters.
```
$$\alpha, \beta, \gamma, \Gamma$$
```
$$ \alpha, \beta, \gamma, \Gamma $$

#### Special Symbols
All common mathematical symbols are implemented, and you can find a listing on the LaTeX cheat sheet.

Some examples. (Notice that, in the third example, I use the tilde character for a forced space. Generally LaTeX does spacing for you automatically, and unless you use the tilde character, R will ignore your attempts to add spaces.)

```
$$a \pm b$$
$$x \ge 15$$
$$a_i \ge 0~~~\forall i$$
```
$$ a \pm b $$
$$ x \ge 15 $$
$$ a_i \ge 0~~~\forall i $$

#### Special Functions
LaTeX typesets special functions in a different font from mathematical variables. These functions, such as sin, cos, etc. are indicated in LaTeX with a backslash. Here is an example that also illustrates how to typeset an integral.
```
$$\int_0^{2\pi} \sin x~dx$$
```
$$ \int_0^{2\pi} \sin x~dx $$

#### Matrices
Matrics are presented in the `array` environment. One begins with the statement `\begin{array}` and ends with the statement `\end{array}`. Following the opening statement, a format code is used to indicate the formatting of each column. In the example below, we use the code `{rrr}` to indicate that each column is right justified. Each row is then entered, with cells separated by the `&amp;` symbol, and each line (except the last) terminated by `\\`.

```
$$\begin{array}
{rrr}
1 & 2 & 3 \\
4 & 5 & 6 \\
7 & 8 & 9
\end{array}
$$
```
$$
\begin{array}
{rrr}
1 & 2 & 3 \\
4 & 5 & 6 \\
7 & 8 & 9
\end{array}
$$

In math textbooks, matrices are often surrounded by brackets, and are assigned to a boldface letter. Here is an example

```
$$\mathbf{X} = \left[\begin{array}
{rrr}
1 & 2 & 3 \\
4 & 5 & 6 \\
7 & 8 & 9
\end{array}\right]
$$
```
$$
\mathbf{X} = \left[\begin{array}
{rrr}
1 & 2 & 3 \\
4 & 5 & 6 \\
7 & 8 & 9
\end{array}\right]
$$

### Hakchin's

[comment1]: # title: "R Markdown"

[comment2]: # This actually is the most platform independent comment

Comment 처리는 아래와 같이 한다.
```
(empty line)
[comment1]: # (This actually is the most platform independent comment)
(empty line)
[comment2]: # (This actually is the most platform independent comment)
This is from http://stackoverflow.com/questions/4823468/store-comments-in-markdown-syntax
```

***
## mathjax example

[MathJax](http://www.mathjax.org/) is a simple way of including Tex/LaTex/MathML based mathematics in HTML webpages. To get up and running you need to include the MathJax script in the header of your github pages page, and then write some maths. For LaTex, there are two delimiters you need to know about, one for block or displayed mathematics `\[ ... \]`, and the other for inline mathematics `\( ... \)`.

### Usage

To enable MathJax support be sure Kramdown is your Markdown flavor of choice and MathJax is set to true in your `_config.yml` file.

```
markdown: kramdown
mathjax: true
```

```
Here is an example MathJax inline rendering \( 1/x^{2} \), and here is a block rendering:
\[ \frac{1}{n^{2}} \]
```

Here is an example MathJax inline rendering $$ 1/x^{2} $$, and here is a block rendering:

$$ \frac{1}{n^{2}} $$

The only thing to look out for is the escaping of the backslash when using markdown, so the delimiters become \\[ ... \\] and \\( ... \\) for inline and block maths respectively.


## markdown-uml
### Reference Sites
* Online Editor
  * [PlantText](http://www.planttext.com/planttext)
  * [PlantUML homepage](http://plantuml.sourceforge.net/)
* 참고 사이트
  * [UML (Unified Modeling Language)](http://blog.naver.com/hermet/220120846602)
  * [UML이란?](http://onecellboy.tistory.com/334)


### UML Diagram의 종류
* 구조적(Structural)
  * Class Diagram
  * Component Diagram
  * Deployment Diagram

* 행위적(Behavioral)
  * Use Case Diagram
  * Sequence Diagram
  * Collaboration Diagram
  * Statechart Diagram
  * Activity Diagram

<img src="https://docs.google.com/drawings/d/1sHxXx348RH4OHnhrOPMJJPgERLhGG39cBz9hKTQ85p8/pub?w=960&amp;h=514">

### plantuml

#### plantuml-basic

https://gist.github.com/hakchin/a29ed23af7aa58a6764c

![](http://uml.mvnsearch.org/gist/a29ed23af7aa58a6764c)


#### plantuml-class

{% gist hakchin/809a33ae61a4d82b0af7 %}

![](http://uml.mvnsearch.org/gist/809a33ae61a4d82b0af7)

#### 관계 (Relationship)

* Association
* Generalization
* Dependency
* Realization


#### plantuml-component

{% gist hakchin/1354c4215962341b7afa %}

![](http://uml.mvnsearch.org/gist/1354c4215962341b7afa)



#### plantuml-sequence

{% gist hakchin/0c6796799c1c9a50ae0e %}
![http://uml.mvnsearch.org/gist/0c6796799c1c9a50ae0e](http://uml.mvnsearch.org/gist/0c6796799c1c9a50ae0e)



#### Trouble Shooting

아래 그림과 같이 Graphviz 관련 에러가 났을 경우에

<img src="https://docs.google.com/drawings/d/1-5NBjkmTGIbAb0zjyOWbauo_quEVLTOa7OxZ2vOdlbA/pub?w=305&amp;h=228">


다음 명령어로 Graphviz을 설치하여 해결하였다.
* sudo apt-get install graphviz

---

## Overview 


## Getting started

To get started, see these three topics:

1. {{site.data.mydoc.mydoc_urls.mydoc_getting_started.link}}
2. {{site.data.mydoc.mydoc_urls.mydoc_configuration_settings.link}}
3. {{site.data.mydoc.mydoc_urls.mydoc_adding_new_projects.link}}

## PDF Download Option for Help Material

If you would like to download this help file as a PDF, you can do so here. The PDF is comprehensive of all the content in the online help.   

<a target="_blank" class="noCrossRef" href="files/{{site.pdf_file_name}}"><button type="button" class="btn btn-default" aria-label="Left Align"><span class="glyphicon glyphicon-download-alt" aria-hidden="true"></span> PDF Download</button></a>

The PDF contains a timestamp in the header indicating when it was last generated. 
