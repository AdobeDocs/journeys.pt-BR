---
product: adobe campaign
solution: Journey Orchestration
title: Atividade de condição
description: Saiba mais sobre atividades de condição
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '743'
ht-degree: 10%

---


# Atividade de condição{#section_e2n_pft_dgb}

Há quatro tipos de condições disponíveis:

* [Condição da fonte de dados](#data_source_condition)
* [Condição de tempo](#time_condition)
* [Divisão de porcentagem](#percentage_split)
* [Condição de data](#date_condition)

![](../assets/journey49.png)

## Sobre a atividade Condition {#about_condition}

Ao usar várias condições em uma jornada, você pode definir rótulos para cada uma delas para identificá-las mais facilmente.

Clique em **[!UICONTROL Add a path]** se desejar definir várias condições. Para cada condição, um novo caminho é adicionado na tela após a atividade.

![](../assets/journey47.png)

Observe que o projeto de viagens tem impactos funcionais. Quando vários caminhos são definidos após uma condição, somente o primeiro caminho elegível será executado. Isso significa que você pode variar a priorização de caminhos colocando-os acima ou abaixo uns dos outros.

Por exemplo, vamos pegar o exemplo da condição de um primeiro caminho &quot;A pessoa é um VIP&quot; e a condição de um segundo caminho &quot;A pessoa é um homem&quot;. Se uma pessoa que atende às duas condições (um macho que é um VIP) passar essa etapa, o primeiro caminho será escolhido mesmo se ele também estiver qualificado para o segundo, porque o primeiro caminho é &quot;acima&quot;. Para alterar essa prioridade, mova suas atividades em outra ordem vertical.

![](../assets/journey48.png)

Você pode criar outro caminho para audiências que não sejam elegíveis às condições definidas, verificando **[!UICONTROL Show path for other cases than the one(s) above]**. Observe que essa opção não está disponível em condições de divisão. Consulte [Divisão de porcentagem](#percentage_split).

O modo simples permite executar query simples com base em uma combinação de campos. Todos os campos disponíveis são exibidos no lado esquerdo da tela. Arraste e solte campos na zona principal. Para combinar os diferentes elementos, interbloqueie-os entre si para criar grupos e/ou níveis de grupo diferentes. Você pode selecionar um operador lógico para combinar elementos no mesmo nível:

* E: uma interseção de dois critérios. Somente os elementos que correspondem a todos os critérios são considerados.
* OU: uma união de dois critérios. Os elementos correspondentes a pelo menos um dos critérios são considerados.

![](../assets/journey64.png)

Se estiver usando o [Adobe Experience Platform Segmentation Service](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html) para criar seus segmentos, você pode aproveitá-los nas condições de viagem. Consulte [Usando segmentos em condições](../segment/using-a-segment.md).


>[!NOTE]
>
>Não é possível executar query em séries cronológicas (por exemplo, uma lista de compras, cliques passados em mensagens) com o editor simples. Para isso, será necessário usar o editor avançado. Consulte [esta página](../expression/expressionadvanced.md).

A jornada de uma pessoa para quando ocorre um erro em uma ação ou condição. O único modo de fazê-la continuar é marcando a caixa **[!UICONTROL Add an alternative path in case of a timeout or an error]**. Consulte [esta seção](../building-journeys/using-the-journey-designer.md#paths).

## Condição da Fonte de Dados {#data_source_condition}

Isso permite definir uma condição com base nos campos das fontes de dados ou dos eventos posicionados anteriormente na jornada. Para saber como usar o editor de expressões, consulte [esta página](../expression/expressionadvanced.md). Usando o editor de expressões avançado, você pode configurar condições mais avançadas manipulando coleções ou usando fontes de dados que exigem a passagem de parâmetros. Consulte [esta página](../datasource/external-data-sources.md).

![](../assets/journey50.png)

## Condição de hora{#time_condition}

Isso permite executar ações diferentes de acordo com a hora do dia e/ou o dia da semana. Por exemplo, você pode decidir enviar mensagens SMS durante o dia e e-mails à noite durante os dias da semana.

>[!NOTE]
>
>O fuso horário já não é específico de uma condição e está agora definido ao nível da viagem nas propriedades da viagem. Consulte [esta página](../building-journeys/timezone-management.md).

![](../assets/journey51.png)

## Porcentagem dividida {#percentage_split}

Essa opção permite que você divida aleatoriamente a audiência para definir uma ação diferente para cada grupo. Defina o número de divisões e a repartição para cada caminho. O cálculo da divisão é estatístico, já que o sistema não consegue prever quantas pessoas fluirão nesta atividade da viagem. Como resultado, a divisão tem uma margem de erro muito baixa. Esta função se baseia em um mecanismo aleatório Java (consulte esta [página](https://docs.oracle.com/javase/7/docs/api/java/util/Random.html)).

>[!NOTE]
>
>Observe que não há nenhum botão para adicionar um caminho na condição de divisão de porcentagem. O número de caminhos dependerá do número de divisões. Em condições divididas, não é possível adicionar um caminho para outros casos, pois ele não pode ocorrer. As pessoas sempre vão para um dos caminhos divididos.

![](../assets/journey52.png)

## Condição de data {#date_condition}

Isso permite definir um fluxo diferente com base na data. Por exemplo, se a pessoa entrar na etapa durante o período de &quot;vendas&quot;, você lhe enviará uma mensagem específica. No resto do ano, você enviará outra mensagem.

>[!NOTE]
>
>O fuso horário já não é específico de uma condição e está agora definido ao nível da viagem nas propriedades da viagem. Consulte [esta página](../building-journeys/timezone-management.md).

![](../assets/journey53.png)
