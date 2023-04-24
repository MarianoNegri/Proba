1) Una urna contiene $4$ bolas rojas, $5$ azules, $6$ verdes y $10$ negras. Se eligen tres bolas al azar. ¿Cuál es la
probabilidad de que todas sean del mismo color si se las selecciona con reposición?

$$P(\text{sacar 3 bolas del mismo color}) = P(\text{sacar 3 bolas rojas}) + P(\text{sacar 3 bolas azules}) + P(\text{sacar 3 bolas verdes}) + P(\text{sacar 3 bolas negras})$$ (son eventos disjuntos)

Si consideramos:

$X_R = \text{ cantidad de bolas rojas que salen en 3 experimentos}$, $X_R \sim Bi(4,4/25)$ entonces $P(\text{sacar 3 bolas rojas}) = P(X_R = 3) = 0.01376256$ 

$X_A = \text{ cantidad de bolas azules que salen en 3 experimentos}$, $X_A \sim Bi(4,5/25)$ entonces $P(\text{sacar 3 bolas azules}) = P(X_A = 3) = 0.0256$

$X_V = \text{ cantidad de bolas verdes que salen en 3 experimentos}$, $X_V \sim Bi(4,6/25)$ entonces $P(\text{sacar 3 bolas verdes}) = P(X_V = 3) = 0.04202496$

$X_N = \text{ cantidad de bolas negras que salen en 3 experimentos}$, $X_N \sim Bi(4,10/25)$ entonces $P(\text{sacar 3 bolas negras}) = P(X_N = 3) = 0.1536$

Luego $$P(\text{sacar 3 bolas del mismo color}) = 0.01376256 + 0.0256 + 0.04202496 + 0.1536 = 0.2349875$$
