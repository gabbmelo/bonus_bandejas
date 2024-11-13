---
subtitle: Processo de vendas da operação
title: Algoritmo preditivo de vendas adicionais
---

# Introdução

Vendas adicionais são uma prática comum no comércio varejista. Este projeto
propõe uma estrutura de vendas adicionais para uma cafeteria e aplica um 
pipeline completo de análise, tratamento e modelagem de dados ingeridos por
diferentes modelos de aprendizado de máquina.

O desempenho preditivo de cada modelo usado é metrificado e validado, gerando
um resultado para um determinado perfil de vendas (ou seja, rotatividade de 
clientes e demanda de portfólio).

Selecionando-se o modelo com melhor acurácia para predição de recomendações 
baseada no movimento dos anos anteriores, busca-se aumentar a receita da
operação estabelecendo-se metas de vendas categorizadas para a equipe de 
baristas da loja.


# Objetivos do sistema de vendas adicionais

Estabelecer o processo de vendas para a operação, visando:

A.  aumentar o número de itens vendidos por cliente;

B.  aumentar o ticket médio das compras;

C.  avaliar a iniciativa e eficiência de vendas da equipe de baristas;

D.  avaliar aplicação de estratégias de marketing a partir dos dados
    coletados;

# Definições Gerais

O processo de vendas da operação é baseado no conceito da metodologia de
venda adicional. Este, por sua vez, está diretamente ligado ao conceito
de bandejas, adaptado de outas redes de varejo de alimentos.

Define-se venda adicional como a oferta de um novo produto ao cliente,
após ele ter decidido o que comprar. A bandeja ideal serve como guia de
qual categoria de produto o barista pode recomendar ao cliente, com base
no que ele já escolheu. As demais bandejas servem como parâmetros para
avaliação comercial da operação e de desempenho da equipe.

## Missão e valores da Cafeteria Montese (relembre)

O consumidor nos procura para fazer uma pausa no meio de seu dia
corrido, ou pelo simples desejo de comer e beber bem. É aquele café
saboroso ou aquele doce apetitoso que deixa a o dia a dia mais leve,
mesmo nos piores momentos. [A natureza primordial de todas as ações da
nossa cafeteria será proporcionar um momento prazeroso ao
cliente]{.underline}. Em caso de dúvidas sobre como agir, paute-se
sempre por esse princípio.

## Construção de uma experiência focada na visão do cliente (relembre)

O atendimento é um grande diferencial na construção de uma experiência
positiva com foco na visão do cliente. Cliente que adquire um produto
ruim, mas é bem atendido, volta. [Cliente que compra um produto bom, mas
o atendimento é ruim, não volta]{.underline}. No mundo interconectado de
hoje, a opinião de um consumidor não é isolada, mas influencia muitas
pessoas -- e essa percepção de valor (ou seja, a experiência com a
marca) pode significar o sucesso ou o fracasso das empresas.

# Boas práticas para realização de venda adicional

A ideia principal por trás da estratégia de venda adicional é que o
cliente irá, em algum momento de seu dia, consumir os itens de todas as
categorias da bandeja ideal. O papel do barista é induzir o cliente a
consumir o máximo de itens possíveis em nossa loja, aproveitando-se do
instinto de praticidade comum aos consumidores e dos diferenciais dos
produtos ofertados por nós.

As instruções a seguir servem de complemento ao passo a passo do
procedimento de recomendação descrito no POP-VENDAS-01:

1.  Sempre verifique a disponibilidade dos itens em cada categoria da
    bandeja ideal ao iniciar o turno;

2.  Saiba o momento ideal para ofertar a recomendação a partir de uma
    leitura dos sinais dados pelo cliente;

3.  Mostre sempre o item que o cliente realmente busca em primeiro
    lugar. Só depois invista na venda adicional;

4.  Invista em ações/discursos que façam os clientes economizarem (por
    exemplo, os combos vêm com desconto em relação à compra dos itens em
    separado);

5.  Se o cliente pediu uma comida, recomende um combo ou uma versão com
    sorvete, caso aplicável (no caso de conversão, deve-se anotar a
    conversão como combo ou dessert);

6.  Se o cliente pediu uma bebida, recomente um combo ou uma
    personalização ou uma versão com sorvete, caso aplicável (no caso de
    conversão, deve-se anotar a conversão como combo ou dessert);

7.  Pedidos com vários itens (para famílias ou grupos) fatalmente
    implicam na necessidade de uma ou mais garrafas d'água; o mesmo vale
    para clientes de negócios ou que fiquem por muito tempo na área de
    cadeiras;

8.  A linha de puristas combina bem com água com gás e comidas mais
    adocicadas (financier, bostock etc.)

9.  As bebidas mais doces combinam bem com itens de sabor neutro ou
    salgado (croissant, pão de queijo etc.).

# Medindo-se o processo de vendas da operação e da equipe

Define-se como bandeja ideal o conjunto composto pelo maior número de
categorias de produtos que seriam normalmente consumidos por um
determinado cliente. Espera-se que ele peça:

-   Uma bebida;

-   Uma comida simples;

-   Uma personalização cobrada;

-   Uma água.

Eventualmente o cliente pode pedir por uma sobremesa ou um combo. Estas
duas categorias são encaixadas dentro da categoria guarda-chuva
"comida", para efeitos de definição do valor da bandeja ideal e
acompanhamento do processo de venda. Isso se dá pois é improvável que o
cliente peça um combo mais uma comida simples, ou uma sobremesa mais uma
comida simples.

O conceito de bandejas será usado não só para orientar o barista na
realização da venda adicional. Ele será usado para:

-   Medição do desempenho comercial da operação;

-   Medição do desempenho de venda da equipe (e bonificação de
    desempenho);

-   Definição de agrupamentos de clientes para abordagens de venda ativa
    de maneira personalizada;

Assim, é importante entendê-lo bem a fim de o aplicar corretamente.

## A definição das bandejas (ideal, do período, recomendada) e de seus valores

### A bandeja ideal e a meta de vendas:

A bandeja ideal é aquela em que o cliente pede pelo menos um item de
cada **categoria** a seguir:

  --------------------------------------------------------------------------------------
  **Categoria**     **Subcategoria**        **Ticket médio de produtos      **Código da
                                        disponíveis (PL6, maio/23)**      categoria**
  ----------------- ------------------- ---------------------------------- --------------
  Bebidas                ---                 R\$ 14,07                         B

  Comidas               Simples              R\$ 10,69                         F

                        Combos*              R\$ 17,88                         K

                        Desserts             R\$ 20,02                         D

  Personalização        ---                  R\$ 2,69                          P

  Água                  ---                  R\$ 12,39                         A
  --------------------------------------------------------------------------------------


\*Valor do combo é contabilizado como a média aritmética de bebidas e
comidas

Seu valor é calculado da seguinte maneira:

$$Valor\ da\ bandeja\ ideal = B + Média\ (F,K,D) + P + A = R\$\ 48,89$$

Ele será atualizado sempre que houver uma alteração na disponibilidade
dos itens, ou quando houver alguma alteração na lista de preços.

O número de bandejas ideais a serem vendidas dentro de determinado
período (semana/mês/ano) será usado como a meta de vendas a ser
atingida:

$$Meta\ quantitativa\ de\ vendas\ do\ período = \ \frac{Meta\ de\ faturamento\ do\ período}{Valor\ da\ bandeja\ ideal} = Nº\ de\ bandejas\ ideais$$

### A bandeja do período:

O valor da bandeja semanal é uma média ponderada, cujos valores são os
tickets de cada categoria: e os pesos as respectivas quantidades:

$$Valor\ da\ bandeja\ do\ período = \ \frac{B \bullet Q_{B} + F \bullet Q_{F} + K \bullet Q_{K} + D \bullet Q_{D} + P \bullet Q_{P} + A \bullet Q_{A}}{Q_{B} + Q_{F} + Q_{K} + Q_{D} + Q_{P} + Q_{A}} = R\$\ xx,yy$$

Segue que o número de bandejas semanais vendidas é o valor faturado
dividido pelo valor dela:

$$Nº\ de\ bandejas\ do\ período = \frac{Valor\ faturado\ no\ período}{Valor\ da\ bandeja\ no\ período}$$

### A bandeja recomendada e as conversões:

Seu valor é calculado da mesma maneira que o da bandeja do período,
porém as quantidades vendidas são substituídas pelas anotações de
produtos recomendados pela equipe da loja a clientes, recomendações
essas convertidas em vendas. Assim:

$$Valor\ da\ bandeja\ recomendada = \ \frac{B \bullet R_{B} + F \bullet R_{F} + K \bullet R_{K} + D \bullet R_{D} + P \bullet R_{P} + A \bullet R_{A}}{R_{B} + R_{F} + R_{K} + R_{D} + R_{P} + R_{A}} = R\$\ xx,yy$$

## Indicadores de desempenho do processo de vendas

Há dois grupos de indicadores principais -- de vendas e de conversão.
Cada grupo principal tem dois indicadores -- quantidade e valor. Esses
indicadores serão calculados a partir dos valores e número de bandejas
para um determinado período (semana/mês/decênio):

> **Indicadores de vendas:**

-   Indicadores quantitativos:

    -   **Meta de vendas ajustada**: meta de vendas ideal\*valor da
        bandeja ideal/valor da bandeja do período;

    -   **Vendas realizadas**: valor de bandejas vendidas/ticket da
        bandeja do período;

    -   **% de meta de vendas:** número de bandejas do período/meta de
        vendas ajustada**;**

-   Indicadores valorativos:

    -   **% do valor ideal**: valor da bandeja do período/valor da
        bandeja ideal;

> **Indicadores de conversões**:

-   Indicadores quantitativos:

    -   **Total de conversões**: recomendações convertidas em vendas,
        anotadas pela equipe;

    -   **Equivalente product line:** valor de vendas da product line do
        período/valor da bandeja do período; é adicionado ao total de
        conversões para ser comparado com a meta calculada;

    -   **Meta de conversões**: calculada a partir das conversões
        realizadas pela equipe nas semanas anteriores, mais um
        percentual adicional definido de comum acordo entre a gestão e
        os baristas-chefes;

-   Indicadores valorativos:

    -   **Eficiência de conversão**: valor da bandeja recomendada/valor
        da bandeja do período;

Há um grupo de indicadores secundários, que auxiliam na formação do
cenário no qual a loja operou em dado período

-   **Movimento**: (n° de bandejas período anterior-nº de bandejas
    período atual)/(nº bandejas período anterior);

-   **Composição da demanda**: % do valor de cada categoria no valor
    total faturado no período;

# Bonificações

Os indicadores de venda e conversão são indicadores acionáveis, pois
partir deles se estabelecem diretrizes para atuação em determinado
aspecto/etapa do processo de vendas, acompanhando-se seu impacto nos
períodos subsequentes.

Uma das ferramentas de reforço positivo aplicável são as bonificações.

## Bonificação da equipe

Define-se um bônus de desempenho coletivo em valor monetário (uma vez
que o desempenho individual também está ligado ao turno no qual o
barista trabalha), a ser pago na terça feira seguinte ao período
anterior. O bônus é pago ao se superar os 100% na eficiência de
conversão E a soma de conversões e equivalente de product line for maior
que a meta de conversões;

O valor atual do bônus é de R\$60,00 por semana.

## Bonificação do cliente

O cliente é bonificado com um cartão de desconto caso:

-   Faça uma compra no valor de pelo menos 70% da bandeja ideal (ca.
    R\$30,00);

-   Faça uma compra de item da product line ou Coffee line;

-   Aceite uma recomendação feita pelo barista;

A ideia é bonificar o cliente quando ele apresentar um comportamento de
compra desejado pela operação, reforçando a interação com o ponto de
vendas de forma positiva e aumentando o percentual de fidelização do
consumidor.
