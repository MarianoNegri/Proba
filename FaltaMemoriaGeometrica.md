La geométrica no tiene memoria es decir, sea $$X \sim G(p)$$ entonces $$P(X \geq k + n | X \geq n) = P(X \geq k)$$

**Demostración:** Observemos que $$P(X \geq k) = \lim_{n \rightarrow \infty} \sum_{i = k-1}^n p(1-p)^i = (1-p)^{k-1} \lim_{n \rightarrow \infty} \sum_{i = 0}^{n - (k-1)} p(1-p)^i = (1-p)^{k-1} \underbrace{\sum_{i = 0}^{\infty} p(1-p)^i}_{ p\sum (1-p)^i = 1} = (1-p)^{k-1}$$ 

Es decir $$P(X \geq k) = (1-p)^{k-1}$$

Entonces tenemos $$P(X \geq k + n | X \geq n) = \frac{P(X \geq k + n)}{P(X \geq  n)} = \frac{(1-p)^{k+n-1}}{(1-p)^{n-1}} = (1-p)^{k} = P(X \geq k)$$ 
