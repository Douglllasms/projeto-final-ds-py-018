# Autoavaliação — Projeto Final DS-PY-018

## O que aprendi

- Que limpar dados não é apagar linhas. Nos 33 tempos inválidos (código 999 e
  negativos) e nas 7 distâncias impossíveis, troquei só o valor errado por NaN
  e criei uma flag. Assim preservei os 8.058 pedidos e as outras informações
  de cada um.
- Que um valor extremo nem sempre é erro. Os pedidos de até R$ 2.299 pareciam
  erro, mas, investigando, pareciam pedidos grandes reais. Por isso passei a
  usar a mediana como ticket típico.
- Que amostras grandes podem detectar diferenças muito pequenas como
  estatisticamente significativas. Por isso, além do p-valor, preciso
  considerar o tamanho do efeito (d de Cohen, ε², V de Cramér) e avaliar
  a importância prática do resultado para o negócio.
- Que correlação não é causa. Os dias de chuva têm mais pedidos, mas a chuva
  se concentra em dezembro, que também tem mais pedidos. A época do ano pode
  explicar parte da relação.

## O que foi mais difícil

- Escolher o teste certo para cada hipótese, principalmente entender quando
  usar Mann-Whitney ou Spearman em vez do teste t.
- Decidir o que era erro e o que era valor real nos outliers, porque cada
  critério (IQR, z-score) apontava uma quantidade diferente.
- Trabalhar com granularidade: entender que a chuva vale para a cidade-dia,
  e não para cada pedido.

## O que eu faria diferente

- Organizaria as pastas e o repositório desde o início, e não no fim.
- Refaria o teste da chuva (H1) usando a média de cada cidade-dia, porque a
  chuva é medida nessa granularidade e o teste por pedido deixa o p-valor
  otimista.
- Investigaria a possibilidade de estimar as 297 distâncias ausentes
  associadas a taxas positivas, utilizando a relação aproximada encontrada
  na Etapa 8 (taxa ≈ R$ 4,99 + R$ 0,90 por km). Antes, verificaria se a
  regra é válida para esses pedidos e identificaria as estimativas como
  valores estimados, não como distâncias realmente observadas.
