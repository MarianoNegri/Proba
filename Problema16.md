La variable aleatoria es $X =$ cantidad de libros mal ubicados, y su distribución es $X \sim Bi(1000,0.001)$, pues la binomial es la cantidad de experimentos independientes 
exitosos en $n$ intentos con probabilidad $p$, en este caso interpretamos experimento exitoso como ubicar mal un libro.

Ahora, recordemos que una binomial $Bi(n,p)$ se puede aproximar por una V.A. Poisson $X \sim P(\lambda)$ con $\lambda = np$. Entonces calculemos los valores aproximados y exactos:

a) 
Aproximado: $P(X \geq 1) = 1 - P(X = 0) = 1 - \frac{e^{-\lambda}\lambda^0}{0!} = 1 - e^{-1} \approx 0.632121$

Exacto: $1 - P(X = 0) = 1 - \binom{1000}{0}0.999^{1000} \approx 0.632304$

b) 
Aproximado: $P(X = 3) = \frac{e^{-1}}{3!} \approx 0, 0613132$

Exacto: $P(X = 3) = \binom{1000}{3}0.001^3 0.999^{997} \approx 0.06128$
