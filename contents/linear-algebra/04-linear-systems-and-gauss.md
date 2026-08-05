La mia risposta:

1. 一个线性方程组由哪些对象构成？



Un sistema lineare è determinato da una matrice dei coefficienti A, da un vettore colonna delle incognite x e da un vettore colonna dei termini noti b.



2. 为什么可以对方程进行行变换？



Le operazioni elementari sulle righe trasformano il sistema in un sistema equivalente, cioè in un sistema con lo stesso insieme delle soluzioni. Ciò è possibile perché ogni operazione elementare è invertibile.



3. Gauss 消元试图把矩阵变成什么形状？



L’eliminazione di Gauss serve a ridurre la matrice completa del sistema a una matrice a scala.



4. pivot 的数量如何决定无解、唯一解或无穷多解？



Quando i numeri di pivot maggiore i numeri delle equazioni, non c'è le soluzioni;



quando i numeri di pivot uguale i numeri delle equazioni, solo una soluzione;



quando i numeri di pivot minore i numeri delle equazioni, hanno le soluzioni infiniti.



1. Un sistema lineare di $m$ equazioni in $n$ incognite può essere scritto nella forma $[
   Ax=b,
   ]$ dove $(A\in M_{m,n}(k))$ è la matrice dei coefficienti, $(x\in k^n)$ è il vettore colonna delle incognite e $(b\in k^m)$ è il vettore colonna dei termini noti.

2. Le operazioni elementari sulle righe producono sistemi equivalenti,
   perché sono operazioni invertibili e quindi non modificano l'insieme delle soluzioni.

3. L'eliminazione di Gauss riduce la matrice completa a una matrice a scala.

4. Per il teorema di Rouché-Capelli, il sistema è compatibile se e solo se
   $[
   \operatorname{rank}(A)=\operatorname{rank}(A\mid b).
   ]$
   Se è compatibile, ammette un'unica soluzione quando
   $[
   \operatorname{rank}(A)=n,
   ]$
   mentre ha variabili libere quando
   $[
   \operatorname{rank}(A)<n.
   ]$

---


Supponiamo $z=t,\qquad t\in\mathbb R$, 

Dal sistema lineare si ottiene:
$$
\begin{cases}
2x-y+3z=5,\\
9y-5z=9
\end{cases}
$$

Risolvendo il sistema, otteniamo:

$$
\begin{cases}
x=3-\frac{11}{9}t \\
y=1+\frac{5}{9}t \\
z=t
\end{cases}
$$

Pertanto, l’insieme delle soluzioni è:
$$
S =
\left\{
\begin{pmatrix}
3\\
1\\
0
\end{pmatrix}
+
t
\begin{pmatrix}
-\frac{11}{9}\\
\frac{5}{9}\\
1
\end{pmatrix}
\middle|
t\in\mathbb{R}
\right\}
$$

Verifichiamo l'insieme delle soluzioni:
$$
A
\begin{pmatrix}
3\\
1\\
0
\end{pmatrix} =
\begin{pmatrix}
5\\
7
\end{pmatrix} =
b
,
\quad
A
\begin{pmatrix}
-\frac{11}{9}\\
\frac{5}{9}\\
1
\end{pmatrix} =
0
$$

---


