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
p = p1+p2+p3+p4
```

</details>  


  
2) Se estima que el 19% de cierta población padece una enfermedad viral. Cierto test para detectar la enfermedad,
se sabe que resulta negativo en el 32% de los casos. Sin embargo, este porcentaje cambia cuando se testea a
la población de verdaderos enfermos con el virus: al 68.42% de la población que padece la enfermedad viral, el
test para detectarla le resulta negativo. Si un paciente adulto elegido al azar recibe un test negativo para la
enfermedad, ¿cuál es la probabilidad de que realmente la padezca?
