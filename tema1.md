1) Una urna contiene $4$ bolas rojas, $5$ azules, $6$ verdes y $10$ negras. Se eligen tres bolas al azar. ¿Cuál es la
probabilidad de que todas sean del mismo color si se las selecciona con reposición? **Respuesta:** $a) \text{ }0.0899$.

<details>
  <summary>Tocar para ver resolución del ejercicio 1</summary>
$$P(\text{sacar 3 bolas del mismo color}) = P(\text{sacar 3 bolas rojas}) + P(\text{sacar 3 bolas azules}) + P(\text{sacar 3 bolas verdes}) + P(\text{sacar 3 bolas negras})$$ (son eventos disjuntos)

  
Si consideramos:

$X_R = \text{ cantidad de bolas rojas que salen en 3 experimentos}$, $X_R \sim Bi(3,4/25)$ entonces $P(\text{sacar 3 bolas rojas}) = P(X_R = 3) = 0.004096$ 

$X_A = \text{ cantidad de bolas azules que salen en 3 experimentos}$, $X_A \sim Bi(3,5/25)$ entonces $P(\text{sacar 3 bolas azules}) = P(X_A = 3) = 0.008$

$X_V = \text{ cantidad de bolas verdes que salen en 3 experimentos}$, $X_V \sim Bi(3,6/25)$ entonces $P(\text{sacar 3 bolas verdes}) = P(X_V = 3) = 0.013824$

$X_N = \text{ cantidad de bolas negras que salen en 3 experimentos}$, $X_N \sim Bi(3,10/25)$ entonces $P(\text{sacar 3 bolas negras}) = P(X_N = 3) = 0.064$

Luego $$P(\text{sacar 3 bolas del mismo color}) =  0.004096 + 0.008 + 0.013824 + 0.064 = 0.08992$$

```
p1 <- dbinom(3,3,4/25)
p2 <- dbinom(3,3,5/25)
p3 <- dbinom(3,3,6/25)
p4 <- dbinom(3,3,10/25)
p <- p1+p2+p3+p4
```

</details>  

***
  
2) Se estima que el 19% de cierta población padece una enfermedad viral. Cierto test para detectar la enfermedad,
se sabe que resulta negativo en el 32% de los casos. Sin embargo, este porcentaje cambia cuando se testea a
la población de verdaderos enfermos con el virus: al 68.42% de la población que padece la enfermedad viral, el
test para detectarla le resulta negativo. Si un paciente adulto elegido al azar recibe un test negativo para la
enfermedad, ¿cuál es la probabilidad de que realmente la padezca? **Respuesta:** $d) \text{ }0.4063$

<details>
  <summary>Tocar para ver resolución del ejercicio 2</summary>
Sabemos que: 

- $P(\text{Estar Enfermo}) = 0.19$
- $P(\text{El test salga negativo}) = 0.32$
- $P(\text{El test salga negativo} | \text{Estar Enfermo}) = 0.6842$

y nos preguntan $P(\text{Estar Enfermo}|\text{El test salga negativo})$. Por Bayes tenemos
$$P(\text{Estar Enfermo}|\text{El test salga negativo}) = \frac{P(\text{El test salga negativo} | \text{Estar Enfermo}) P(\text{Estar Enfermo})}{P(\text{El test salga negativo})} = \frac{0.6842 \cdot 0.19}{0.32} = 0.4062438$$
  
</details>

***  
  
3) Se tienen dos dados: uno cargado, en el que los números impares tienen probabilidad 0.23 de salir cada uno, y
uno equilibrado. Se lanza una moneda normal: si sale cara, se elige el dado cargado y si sale ceca, el equilibrado.
Luego, se arroja el dado 9 veces de forma independiente. Indicar el valor de la probabilidad de obtener impar
en 7 lanzamientos. **Respuesta:** $a) \text{ }0.164$ 


<details>
  <summary>Tocar para ver resolución del ejercicio 3</summary>
  
$P(\text{Sale impar 7 veces}) = P( \text{Sale impar 7 veces|Dado cargado})\underbrace{P(\text{Dado cargado})}_ {=0.5} + P(\text{Sale impar 7 veces|Dado equilibrado})\underbrace{P(\text{Dado equilibrado})}_ {=0.5}$ 

Ahora, si 
- $X_C = \text{Cantidad de éxitos en 9 experimentos Bernoulli con proba 0.69}$, $X_C \sim Bi(9,0.69)$
- $X_E = \text{Cantidad de éxitos en 9 experimentos Bernoulli con proba 0.5}$, $X_E \sim Bi(9,0.5)$

Entonces: 
- $P( \text{Sale impar 7 veces|Dado cargado} ) = P(X_E = 7) = 0.257614$
- $P( \text{Sale impar 7 veces|Dado equilibrado} ) = P(X_C = 7) = 0.0703125$
 
Luego $$P(\text{Sale impar 7 veces}) = 0.257614\cdot 0.5 + 0.0703125 \cdot 0.5 = 0.1639633 $$

```
p1 <- dbinom(7,9,0.69)
p2 <- dbinom(7,9,0.5)
p <- p1*0.5+p2*0.5
```
</details>
  
***
  
4) En la producción de cierto tipo de tela, el número de defectos por metro ($Y$) es una variable aleatoria que
puede asumirse que se distribuye como una Poisson de parámetro 12. La ganancia del fabricante (en unidades
monetarias por metro de tela) puede suponerse dada por $X = 257 - 2Y - Y^2$. ¿Cuánto es la ganancia esperada? **Respuesta:** $a) \text{ }77$

<details>
  <summary>Tocar para ver resolución del ejercicio 4</summary>
  
Tenemos $Y = \text{número de defectos por metro}$, $Y \sim P(12)$. Recordemos que $Var\[Y\] =  E\[Y^2\] - E\[Y\]^2$ con lo cual $E\[Y^2\] = Var\[Y\] + E\[Y\]^2$ 
  
Nos piden calcular $E\[ X \] = E\[ 257 \] - 2E\[ Y \] - E\[ Y^2 \] = 257 - 2E\[ Y \] - Var\[Y\] - E\[Y\]^2$.
  
Como sabemos que la esperanza y la varianza de una Poisson de parámetro $12$ es $12$, tenemos entonces que $$E\[X\] = 257 - 2\cdot 12 - 12^2 - 12 = 77$$.
  
</details>

***  
  
5) Sea $X$ una variable aleatoria con función de densidad $f_X(x) = \frac{64k}{(x + 4)^5}$ , para $x \geq 0$. Indicar el valor que corresponde a $k$. **Respuesta:** $a) \text{ }16$

<details>
  <summary>Tocar para ver resolución del ejercicio 5</summary>
Buscamos que $$\int_0^{+\infty} f_X(s) ds = 1$$
Una primitiva es $-4^2k(x+4)^{-4}$. Entonces $\int_0^{+\infty} f_X(s) ds = 4^2k4^{-4} = 4^{-2}k$ Con lo cual $$k = 4^2 = 16$$
  
</details>

***
  
6) Los colectivos de la línea 199 salen de la cabecera en intervalos de 18 minutos a partir de las 8 ∶ 00 am. Si un
pasajero llega a la parada de cabecera a una hora uniformemente distribuida entre las 8 ∶ 00 am y las 8 ∶ 36 am,
indicar el valor que corresponde a la probabilidad de que deba esperar menos de 6 minutos el colectivo. **Respuesta:** $a) \text{ } \frac{1}{3}$


<details>
  <summary>Tocar para ver resolución del ejercicio 6</summary>

Sea $X \sim U[0,36]$. Nos preguntan: $$P( \\{ 12 \leq X \leq 18 \\} \cup \\{30 \leq X \leq 36 \\}) = \frac{6}{36} + \frac{6}{36} = \frac{12}{36} = \frac{1}{3}$$  
  
</details>

***
  
7) Sea $Y$ una variable aleatoria con función de densidad $f_Y(y) = \frac{2}{9}ye^{-y^2/9}$, para $y \geq 0$.
Indicar el valor que corresponde al percentil $89$ de la variable $X = Y^2$. **Respuesta:** $a) \text{ } 19.8655$
  
<details>
  <summary>Tocar para ver resolución del ejercicio 7</summary>

Nos preguntan por un $p$ tal que $P(X \leq p) = 0.89$. Esto es $P(Y^2 \leq p) = 0.89$ o lo que es lo mismo $P(-\sqrt{p} \leq |Y| \leq \sqrt{p}) = 0.89$. En este caso, esto es lo mismo que $P(Y \leq \sqrt{p}) = 0.89$. Es decir buscamos $p$ tal que $$\int_0^{\sqrt{p}} \frac{2}{9}ye^{-y^2/9} = 0.89$$

Una primitiva es $-e^{-y^2/9}$, con lo cual $$\int_0^{\sqrt{p}} \frac{2}{9}ye^{-y^2/9} = -e^{-p/9}+1$$ 
Luego tenemos que resolver la ecuación $$-e^{-p/9}+1 = 0.89 \iff e^{-p/9} = 0.11 \iff p = -9 \cdot \text{ln}(0.11) \iff p = \text{ln}(0.11^{-9})$$ 
Esto da que $p \approx 19.8655$.
  
</details>

***  
  
8) Sea $(X, Y)$ el vector aleatorio con función de densidad conjunta $f_{XY}(x, y) = 4(1-(x + y)^2)$, para $0 \leq x + y \leq 1$.

Indicar el valor que corresponde a $P(X + Y < 0.72)$.

<details>
  <summary>Tocar para ver resolución del ejercicio 8</summary>
  
  Nos piden calcular $$\int \int_{0 < x+y < 0.72} f_{XY}(x,y) dx dy = \int \int_{-x < y < 0.72-x} 4(1-(x + y)^2) dx dy $$  

  
</details>

***  
  
9) Diariamente, una empresa hormigonera produce una cierta variedad de cemento (en bolsas) cuyo peso, en kg,
es una v.a. con media $\mu = 9.8$ y varianza $\sigma^2 = 0.23$. Para todo lo que sigue, suponer que todas las variables
involucradas en esta situación son i.i.d. Usar el Teorema Central del Límite para calcular cuántas unidades,
como mínimo, deberán producirse un día cualquiera de la semana si se quiere satisfacer un pedido de al menos
3310 kg con probabilidad aproximada mayor que $0.9515$.


  
Definimos $X = \text{ Peso en kg de cemento producido diariamente}$. Sabemos que $E\[X\] = 9.8$ y $Var\[X\] = 0.23$.
Definamos 
  
  
