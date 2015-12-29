---
title: 고교수학
tags: [getting_started, formatting, content-types]
keywords: pages, authoring, exclusion, frontmatter
last_updated: November 30, 2015
summary: "This theme uses pages only, not posts. You need to make sure your pages have the appropriate frontmatter. One frontmatter tag your users might find helpful is the summary tag. This functions similar in purpose to the shortdesc element in DITA."
---


## Function

* 단사(injective)
* 전사(surjective)
* 전단사(bijective)


## 수열(progression)

### 중항(mean)

Let a &gt; 0, b &gt; 0.

* 등차중항 - an arithmetical mean
\\[ A = \dfrac{a + b}{2} \\]

* 등비중항 - a mean proportional
\\[ G = \sqrt{ab} \\]

* 조화중항 - a harmonic mean
\\[ H = \dfrac{2ab}{a + b} \\]
\\[ A \geq G \geq H \\]
\\[ G^2 = AH \\]

### 등비수열의 합 
(Sum of a geometric progression)

* If \\( r \neq 1 \text{, } S_n = \dfrac{a(1-r^n)}{1-r} \\)
* If \\( r = 1 \text{, } S_n = na \\)


### 조화수열
(a harmonic progression)

* 어떤 수열의 각 항의 역수가 등차수열을 이룰 때 그 수열을 조화수열이라 한다. 곧,
\\( \dfrac{1}{a_1}, \dfrac{1}{a_2}, \dfrac{1}{a_3}, ..., \dfrac{1}{a_n} \\) 이 등차수열 \\( \iff a_1, a_2, a_3, ..., a_n \\) 이 조화수열


### 조화중항
harmonic mean

* 0이 아닌 세수 a, x, b 가 이 순서로 조화수열을 이룰 때 x를 a, b의 조화중항이라고 한다.

1. a, x, b 가 조화수열이면, \\( \dfrac{2}{x} = \dfrac{1}{a} + \dfrac{1}{b} \iff x = \dfrac{2ab}{a + b}\\)
1. a, b 의 조화중항 \\( \iff \\) a, b의 조화평균



### 이자계산-원리합계

#### 기수불 예금에서 원금을 a, 이율을 r, 기간을 n, 원리합계를 S라 할 때,
* 단리법으로 계산하면 \\( S = a(1 + rn) \\)
* 복리법으로 계산하면 \\( S = a(1 + r^n) \\)

### 적립총액

#### 연이율 r, 매년마다 복리로 매년총에 a원씩 적립하면 적립총액은 얼마가 되겠는가?

* 답안
구하는 적립총액을 S원이라 하면,
\\[ S = a(1 + r) + a(1 + r)^2 + a(1 + r)^3 + ... + a(1 + r)^n \\]
\\[ \Rightarrow S = \dfrac{a(1+r)\{(1+r)^n - 1\}}{(1+r)-1} = \dfrac{a(1+r)\{(1+r)^n - 1\}}{r}\\]


### 연부상환
연초에 A원을 빌리고, 그 해 말부터 매년 일정한 금액씩 갚아 n년간에 모두 갚으려고 한다. 매년 얼마씩 갚으면 좋은가? 단, 연이율 r, 1년마다 복리로 계산한다.

#### 답안
A원에 대한 n년 말의 원리합계는 \\( A(1+r)^n \\)원 \\( \cdots \\) ① <br>
한편, 매년 말에 x원씩 적립했다고 할 때 이들의 n년말에 가서의 원리합계는<br>
\\( x + x(1+r) + x(1+r)^2 + \cdots + x(1+r)^{n-1} = \dfrac{x\{(1+r)^n - 1\}}{(1+r)-1} \cdots \\) ② <br>
①과 ②는 같아야 하므로<br>
\\( \dfrac{x\{(1+r)^n - 1\}}{r} = A(1+r)^n \therefore x = \dfrac{Ar(1+r)^n}{(1+r)^n - 1} \\)

#### 참고
어떤 돈을 빌려쓰고, 매년 일정한 금액씩 갚아가는 것을 **연부상환**이라 하고, 이 일정한 금액을 **연부금**이라 한다. 또, 매월 일정한 금액씩 갚아가는 경우에는 이를 월부상환이라 하고, 이 일정한 금액을 월부금이라 한다.



### 연금
금년부터 매년말에 a원씩 n년간 계속해서 지급되는 연금이 있다. 이 연금을 금년 초에 한꺼번에 받는다면 얼마를 받아야 하는가? 단, 연이율 r, 1년마다 복리로 계산한다.

#### 답안
연금현가를 P원이라 하면,
\\[ P(1+r)^n = a + a(1+r) + a(1+r)^2 + \cdots + a(1+r)^{n-1} \\]
\\[ \therefore P(1+r)^n = \dfrac{a\{(1+r)^n - 1)\}}{(1+r)-1} \\]
\\[ \therefore P = \dfrac{a\{(1+r)^n - 1)\}}{r(1+r)^n} \\]

#### 참고
일정한 금액이 일정한 시기마다 계속해서 지급될 때 이것을 **연금**이라고 부른다. 그런데 이 연금은 장래에 받을 돈이므로 현재에 있어서는 그 액면대로의 가치가 없다. 그래서 이와 같은 연금을 현재의 값으로 따져 얼마의 가치가 있는 가를 생각해 본 것이 **연금의 현가**이다.

#### 부가문제
n년말에 fv(future value)를 지급받는다. 금년말을 1년말이라고 치고 n년말에 fv를 지급받는다. 단 연이율 r, 1년마다 복리로 계산한다. fv의 현재가치(pv)는?

#### 답안
1년말 : \\( fv = pv + pv \times r = pv \times (1+r) \\)<br>
n년말 : \\( fv = pv \times (1+r)^n \therefore pv = \dfrac{fv}{(1+r)^n}\\)






