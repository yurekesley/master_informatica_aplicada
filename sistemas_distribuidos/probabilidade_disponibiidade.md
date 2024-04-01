# Mestrado Informática Aplicada - Sistemas Distribuídos
#### PPGIA - Unifor
#### Yure Kesley Moreira Plácido
#### Probabilidade de Disponibilidade


**Parâmetros:**

- \(n\) – número de servidores $n > 0$
- \(k\) – número mínimo de servidores disponíveis necessário para o serviço ser acessado de forma consistente $0 < k \leq n$
- \(p\) – probabilidade de cada servidor estar disponível em um dado instante $0 \leq p \leq 1$

**Casos específicos:**

**Caso \(k = 1\)** (Operação de Consulta):

Quando a indisponibilidade de um serviço implica na falha do sistema distribuído, dizemos que ao menos um serviço em execução é obrigatório para a operação de cosulta. Então, a disponibilidade $A_1$ é dada por:

$$A_1 = 1 - (1 - p)^n$$

**Caso \(k = n\)** (Operação de Atualização):

Neste caso, a disponibilidade do serviço é a obrigatoriedade de todos os servidores estarem disponíveis como probabilidade total. Portanto, a disponibilidade $A_n$ é simplesmente a multiplicação das probabilidades de cada servidor estar disponível:

$$A_n = p^n$$

**Generalização:**

Para valores de $k$ entre 1 e $n$, podemos calcular a disponibilidade $A_k$ como a soma das probabilidades de todos os conjuntos de servidores possíveis que podem atender a operação, cada conjunto consistindo de $k$ servidores. A fórmula para $A_k$ é dada por:

$$A_k = \sum_{i=k}^{n} \binom{n}{i} \cdot p^i \cdot (1-p)^{n-i}$$

onde $\binom{n}{i}$ representa o coeficiente binomial que calcula o número de maneiras de escolher $i$ servidores a partir de $n$.

**Exemplo:**

Considerando um serviço replicado em 3 servidores, sendo: $$n = 3$$ A necessidade de pelo menos 2 servidores disponíveis para o serviço funcionar $k = 2$ e com probabilidade de cada servidor estar disponível de 0.9% ou $p = 0.9$.

A fórmula para calcular a disponibilidade neste caso é:

$$A_2 = \sum_{i=2}^{3} \binom{3}{i} \cdot 0.9^i \cdot (1-0.9)^{3-i}$$

Calculando os termos da soma, obtemos:

$$A_2 = \binom{3}{2} \cdot 0.9^2 \cdot 0.1^1 + \binom{3}{3} \cdot 0.9^3 \cdot 0.1^0$$

$$A_2 = 3 \cdot 0.81 \cdot 0.1 + 1 \cdot 0.729 \cdot 1$$

$$A_2 = 0.243 + 0.729 = 0.972$$

Portanto, a disponibilidade do serviço neste exemplo é de 97.2%.