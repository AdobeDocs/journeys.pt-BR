---
product: adobe campaign
title: Atividade de condição
description: Saiba mais sobre atividades de condição
feature: Jornadas
role: User
level: Intermediate
exl-id: 7b44edbe-9d05-4d67-8a64-2a0a553fcb92
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 10%

---

# Atividade de condição{#section_e2n_pft_dgb}

Quatro tipos de condições estão disponíveis:

* [Condição da fonte de dados](#data_source_condition)
* [Condição de tempo](#time_condition)
* [Divisão de porcentagem](#percentage_split)
* [Condição de data](#date_condition)

![](../assets/journey49.png)

## Sobre a atividade Condição {#about_condition}

Ao usar várias condições em uma jornada, você pode definir rótulos para cada uma delas para identificá-las mais facilmente.

Clique em **[!UICONTROL Add a path]** se desejar definir várias condições. Para cada condição, um novo caminho é adicionado na tela após a atividade .

![](../assets/journey47.png)

Observe que o design das jornadas tem impactos funcionais. Quando vários caminhos são definidos após uma condição, somente o primeiro caminho elegível é executado. Isso significa que você pode variar a priorização de caminhos, colocando-os acima ou abaixo uns dos outros.

Por exemplo, vamos considerar o exemplo de uma condição de primeiro caminho &quot;A pessoa é um VIP&quot; e uma condição de segundo caminho &quot;A pessoa é um homem&quot;. Se uma pessoa que atende às duas condições (um homem que é um VIP) passar nessa etapa, o primeiro caminho será escolhido mesmo que também seja elegível para o segundo, porque o primeiro caminho é &quot;acima&quot;. Para alterar essa prioridade, mova suas atividades para outra ordem vertical.

![](../assets/journey48.png)

Você pode criar outro caminho para públicos-alvo que não estejam qualificados para as condições definidas marcando **[!UICONTROL Show path for other cases than the one(s) above]**. Observe que essa opção não está disponível em condições de divisão. Consulte [Divisão de porcentagem](#percentage_split).

O modo simples permite executar consultas simples com base em uma combinação de campos. Todos os campos disponíveis são exibidos no lado esquerdo da tela. Arraste e solte campos na zona principal. Para combinar os diferentes elementos, faça o interbloqueio entre eles para criar grupos e/ou níveis de grupo diferentes. Você pode selecionar um operador lógico para combinar elementos no mesmo nível:

* E: uma interseção de dois critérios. Somente os elementos que correspondem a todos os critérios são considerados.
* OU: uma união de dois critérios. Os elementos correspondentes a pelo menos um dos critérios são considerados.

![](../assets/journey64.png)

Se estiver usando o [Serviço de segmentação do Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html) para criar seus segmentos, você pode aproveitá-los em suas condições de jornada. Consulte [Uso de segmentos em condições](../segment/using-a-segment.md).


>[!NOTE]
>
>Não é possível executar consultas em séries de tempo (por exemplo, uma lista de compras, cliques anteriores em mensagens) com o editor simples. Para isso, será necessário usar o editor avançado. Consulte [esta página](../expression/expressionadvanced.md).

A jornada de uma pessoa para quando ocorre um erro em uma ação ou condição. O único modo de fazê-la continuar é marcando a caixa **[!UICONTROL Add an alternative path in case of a timeout or an error]**. Consulte [esta seção](../building-journeys/using-the-journey-designer.md#paths).

## Condição da fonte de dados {#data_source_condition}

Isso permite definir uma condição com base nos campos das fontes de dados ou nos eventos posicionados anteriormente na jornada. Para saber como usar o editor de expressão, consulte [esta página](../expression/expressionadvanced.md). Usando o editor de expressão avançado, você pode configurar condições mais avançadas manipulando coleções ou usando fontes de dados que exigem a passagem de parâmetros. Consulte [esta página](../datasource/external-data-sources.md).

![](../assets/journey50.png)

## Condição de tempo{#time_condition}

Isso permite executar ações diferentes de acordo com a hora do dia e/ou o dia da semana. Por exemplo, você pode decidir enviar mensagens SMS durante o dia e emails à noite durante os dias da semana.

>[!NOTE]
>
>O fuso horário não é mais específico de uma condição e agora é definido no nível da jornada nas propriedades da jornada. Consulte [esta página](../building-journeys/timezone-management.md).

![](../assets/journey51.png)

## Divisão de porcentagem {#percentage_split}

Essa opção permite dividir aleatoriamente o público-alvo para definir uma ação diferente para cada grupo. Defina o número de divisões e a repartição para cada caminho. O cálculo de divisão é estatístico, pois o sistema não pode prever quantas pessoas fluirão nessa atividade da jornada. Como resultado, a divisão tem uma margem de erro muito baixa. Essa função é baseada em um mecanismo aleatório do Java (consulte esta [página](https://docs.oracle.com/javase/7/docs/api/java/util/Random.html)).

No modo de teste, ao alcançar uma divisão, a ramificação superior é sempre escolhida. Você pode reorganizar a posição das ramificações divididas se quiser que o teste escolha um caminho diferente. Consulte [esta página](../building-journeys/testing-the-journey.md)

>[!NOTE]
>
>Observe que não há um botão para adicionar um caminho na condição de divisão de porcentagem. O número de caminhos dependerá do número de divisões. Em condições divididas, não é possível adicionar um caminho para outros casos, pois ele não pode ocorrer. As pessoas sempre vão para um dos caminhos divididos.

![](../assets/journey52.png)

## Condição de data {#date_condition}

Isso permite definir um fluxo diferente com base na data. Por exemplo, se a pessoa entrar na etapa durante o período de &quot;vendas&quot;, você lhe enviará uma mensagem específica. No resto do ano, você enviará outra mensagem.

>[!NOTE]
>
>O fuso horário não é mais específico de uma condição e agora é definido no nível da jornada nas propriedades da jornada. Consulte [esta página](../building-journeys/timezone-management.md).

![](../assets/journey53.png)
