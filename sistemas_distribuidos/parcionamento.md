Atividade 1.3

A) 
Tal particionamento tem impacto nas relações de leitura e escrita

Leitura: 
Vantagens:
O Dado C fica disponível por toda a rede, logo ele só ficaria inacessível na indisponibilidade da rede por completo
Os dados A e B ficam particionados, balanceando a carga de leitura e permitindo leitura concorrente

Desvantagens:
Para requerer ambas as partes do dado A e B será necessária a disponibilidade completa da rede

Escrita:
Vantagens:
A escrita em A e B não correm risco de quebra de consistência visto que cada nó é delegado uma parte específica do dado

Desvantagens:
O dado C pode possuir falha na consistência dos dados pois ambos os nós possuem uma cópia dele

B) Caso o conjunto B seja muito mais acessado do que os outros, a melhor situação seria ele estar replicado nas duas instâncias da rede

C) O Ideal seria que a maior parte dos dados fossem passados para o Nó 1, principalmente, os dados que possuem uma maior taxa de escrita

D) Tipo de dado: Caso alguma parte dos dados seja mais de escrita do que de leitura seria ideal uma reorganização, dados mais de leitura idealmente devem existir em todas as instâncias enquanto os de escrita somente nas com maior disponibilidade



Atividade 1.4




Cliente -> Servidor : Min = 2, Max = 6
Banco : Min = 1.5, Max = 2.5
Servidor -> Cliente : Min = 10, Max = 25
Melhor caso = 2 + 1.5 + 10 = 13.5
Pior caso = 6 + 2.5 + 25 = 33.5

A) 
Melhor caso (dado no cache) = 2 + 0.5 + 10 = 12.5
Pir caso (dado fora do cache) = 6 + 2.5 + 25 = 33.5

B)

Melhor caso (Dado no cache, sem falha) = 2 + 0.5 + 10 = 12.5
Pior caso (Dado fora do cache, com falha) = 
6 + 2 (detecção da falha) + 5 (espera para o re envio) + 6 (envio novamente) + 2.5 + 25 = 46.5


Atividade 1.5

A) Nos sistemas distribuídos, caso ocorra um particionamento na rede o sistema deve escolher manter o AP(disponibilidade e tolerância ao particionamento) ou CP (Consistência dos dados e tolerância ao particionamento). Essa escolha deve ser feita pois, para suprir a disponibilidade, Nós não "sincronizados" deveriam responder mesmo sem estar com o dado consistente, se eles não responderem a disponibilidade é comprometida comprometendo o fator AP, portanto não é possível manter Consistência Disponibilidade e tolerância ao particionamento.

B)
AP: sistemas de streaming, como os dados não são geralmente atualizados com frequência, mais importa que o sistema possua uma tolerância ao particionamento e alta disponibilidade.

CP: Blockchain, para uma blockchain é crucial a consistência dos dados, nela são utilizados mecanismos de eleição de nós que podem escrever na rede, e também, possui mecanismos de consenso, para garantir que pelo menos 50% + 1 da rede possuam os mesmos dados.

CA: O teorema CA é mais raro de ser alcançado pois exige que a rede não seja particionada. Segundo a IBM "enquanto podemos discutir um banco de dados distribuído CA em teoria, para todos os efeitos práticos, um banco de dados distribuído CA não pode existir"

C) O Teorema CAP continua relevante em computação em nuvem, contêineres, microsserviços e arquiteturas serverless, influenciando a gestão de dados sob falhas. Essas tecnologias modernas não eliminam o dilema entre consistência e disponibilidade, especialmente em sistemas que escalam dinamicamente. A decisão entre manter dados consistentes ou serviços disponíveis em face de partições de rede é crucial, mantendo o teorema como um pilar na arquitetura de sistemas distribuídos.

