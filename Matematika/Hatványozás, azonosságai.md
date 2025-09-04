---
title: Hatványozás, azonosságai
tags:
  - Matematika
date: 2025-09-04
---

# Hatványozás, azonosságai

## 1. Kitevő természetes szám*

$$
a^n =
\begin{cases}
\underbrace{a \cdot a \cdot \ldots \cdot a}_{n \text{ db}}, & n > 1, \; a \in \mathbb{R} \\
a, & n = 1 \\
1, & n = 0, \; a \neq 0
\end{cases}
$$

> Megjegyzés:
> - $a$: hatványalap (alap)
> - $n$: hatványkitevő (kitevő)

---

### Hatványozás azonosságai

#### Szorzás azonos alapú hatványok esetén

$$
a^n \cdot a^m = a^{n + m}, \quad a \in \mathbb{R}, \; n, m \in \mathbb{N}^*, \; (n = m = 0 \Rightarrow a \neq 0)
$$

**Bizonyítás**:

$$
a^n \cdot a^m = \underbrace{a \cdot a \cdot a \cdot \ldots \cdot a}_{n \text{ db}} \cdot \underbrace{a \cdot a \cdot a \cdot \ldots \cdot a}_{m \text{ db}} = a^{n + m}
$$

---

#### Osztás azonos alapú hatványok esetén

$$
\dfrac{a^n}{a^m} = a^{n - m}, \quad a \in \mathbb{R}, \; a \neq 0, \; n, m \in \mathbb{N}^*, \; n \ge m
$$

---

#### Hatvány hatványa

$$
(a^n)^m = a^{n \cdot m}, \quad a \in \mathbb{R}, \; n, m \in \mathbb{N}^*, \; (a = 0 \Rightarrow n, m \neq 0)
$$

---

#### Szorzat hatványa

$$
(a \cdot b)^n = a^n \cdot b^n, \quad a, b \in \mathbb{R}, \; n \in \mathbb{N}^*, (a = 0 \text{ v. } b = 0 \Rightarrow n \neq 0)
$$

---

#### Hányados hatványa

$$
\left( \dfrac{a}{b} \right)^n = \dfrac{a^n}{b^n}, \quad a, b \in \mathbb{R}, \; b \neq 0, \; n \in \mathbb{N}^*, n = 0 \Rightarrow a \neq 0
$$

---

#### **Permanencia-elv**

Az eddigi megismert azonosságok maradjanak érvényben a hatványkitevő kiterjesztése esetén is.

---

## 2. Kitevő egész szám

$$
\dfrac{a^n}{a^m} = a^{n - m}
$$

---

$$
a^{-n} = \dfrac{1}{a^n}, \quad a \in \mathbb{R}, \; a \neq 0, \; n \in \mathbb{N}
$$

---

## 3. Kitevő racionális

$$
a^{\frac{p}{q}} = \sqrt[q]{a^p}, \quad p, q \in \mathbb{Z}, \; q \neq 0, \; q \ge 2, \; a \in \mathbb{R}_0^+
$$

---

## 4. Kitevő irracionális

$$
\begin{array}{c}
3.1 < \pi < 3.2 \quad a^{3.1} < a^\pi < a^{3.2} \\
3.11 < \pi < 3.19 \quad a^{3.11} < a^\pi < a^{3.19} \\[2mm]
\Downarrow \text{Rendőr elv} \\[1mm]
a^\pi \approx \text{valahol } a^{3.15} \text{ körül}
\end{array}
$$



