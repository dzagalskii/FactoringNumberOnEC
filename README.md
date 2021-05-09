# [ENG] Factorization of a number on an elliptic curve

## Setting up the development environment
This program was implemented in SageMath in the Python 3 programming language in the Jupyter Notebook development environment.
All dependencies are present in SageMath. You can install the SageMath package using the link from the official website: https://www.sagemath.org.

## A little about number decomposition algorithms
The problem of factoring a number n over a ring Z is reduced to finding all prime divisors of n. Methods for factoring a number into factors can be divided into special and universal.
Special methods are effective for some classes of composite numbers and typically use a random number generator or pseudo-random display. These methods include the ρ-Pollard method, (p-1) -Pollard method.
Generic methods do not assume any information about the form of the number n and its divisors. These methods include the trial division method, the giant step - baby step method, the Fermat method, the Diophantine approximation method, the continued fraction method, the quadratic sieve method, etc.
In 1987, H. Lenstra proposed an algorithm for factoring a number using elliptic curves.

## A little about Lenstra's algorithm

Lenstra's method is an analogue of Pollard's (p-1) -method in the group of points of an elliptic curve, which allows you to find a nontrivial divisor of a given number n.
Suppose the number n is factorized: n = pq, where p ≠ q are prime numbers. Then, by the Chinese remainder theorem, there is a group isomorphism:
E (Z⁄nZ) ≅ E (Z⁄pZ) ⊕ E (Z⁄qZ).
Multiplication of any element of the group E (Z⁄nZ) by m∈Z preserves this isomorphism:
mE (Z⁄nZ) ≅ mE (Z⁄pZ) ⊕ mE (Z⁄qZ).
In the formula for adding two points P_1 = (x_1, y_1) and P_2 = (x_2, y_2), the expression for the slope is: λ = (3x_1 ^ 2 + A) / (2y_1), and in the doubling formula (P_1 = P_2) the coefficient is respectively equal to λ = (y_2-y_1) / (x_2-x_1). In some cases, it may turn out that the points are different modulo p, and the same modulo q. Then the formulas for adding points will give an incorrect result, and the sum of points may not lie on the original curve.
This situation is easily detected by calculating the value d = GCD (n, λ_1), where λ_1 is the denominator in the formulas for the slope λ. If points are specified in projective coordinates (X, Y, Z), then when calculating d, you can use the value of the Z coordinate: d = GCD (n, Z). For d different from 1 and n, the problem of finding the divisor of the number n is solved. 


# [RU] Разложение числа на эллиптической кривой

## Настройка среды разработки
Данная программа была реализована на SageMath на языке программирования Python 3 в среде разработки Jupyter Notebook.
Все зависимости присутствуют в SageMath. Установить пакет SageMath можно по ссылке с официального сайта: https://www.sagemath.org.

## Немного об алгоритмах разложения чисел
Задача разложения на множители числа n над кольцом Z сводится к нахождению всех простых делителей числа n. Методы разложения числа на множители можно разделить на специальные и универсальные. 
Специальные методы эффективны для некоторых классов составных чисел и, как правило, используют генератор случайных чисел или псевдослучайное отображение. К таким методам относятся ρ-метод Полларда, (p-1)-метод Полларда.
Универсальные методы не предполагают никакой информации о виде числа n и его делителях. К таким методам относятся метод пробного деления, метод «giant step – baby step», метод Ферма, метод диофантовой аппроксимации, метод непрерывных дробей, метод квадратичного решета и др.
В 1987 г. Х. Ленстра предложил алгоритм разложения числа на множители с использованием эллиптических кривых.

## Немного об алгоритме Ленстры

Метод Ленстры является аналогом (p-1)-метода Полларда в группе точек эллиптической кривой, который позволяет найти нетривиальный делитель заданного числа n.
Предположим, что число n раскладывается на множители: n=pq, где p≠q – простые числа. Тогда по китайской теореме об остатках имеет место изоморфизм групп: 
E(Z⁄nZ) ≅ E(Z⁄pZ) ⊕ E(Z⁄qZ).
Умножение любого элемента группы E(Z⁄nZ) на m∈Z сохраняет данный изоморфизм:
mE(Z⁄nZ) ≅ mE(Z⁄pZ) ⊕ mE(Z⁄qZ).
В формуле сложения двух точек P_1 = (x_1,y_1) и P_2 = (x_2,y_2) выражение для углового коэффициента имеет вид: λ = (3x_1^2+A)/(2y_1), а в формуле удвоения (P_1 = P_2) коэффициент соответственно равен λ = (y_2-y_1)/(x_2-x_1 ). В некоторых случаях может получиться так, что по модулю p точки различны, а по модулю q одинаковы. Тогда формулы сложения точек дадут неправильный результат, и сумма точек может не лежать на исходной кривой.
Данная ситуация легко обнаруживается вычислением значения d = НОД(n, λ_1), где λ_1 – знаменатель в формулах углового коэффициента λ. Если точки заданы в проективных координатах (X, Y, Z), то при вычислении d можно использовать значение координаты Z: d = НОД(n,Z). При d, отличном от 1 и n, задача нахождения делителя числа n решена.

