---
title: Sobre o editor de expressão avançado
description: Saiba como criar expressões avançadas
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: e353d593ab2710f50a88a3715378c86c2e37b4f6
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 96%

---


# Sobre o editor de expressão avançado {#concept_uyj_trt_52b}

O editor de expressão avançado permite criar expressões avançadas em várias telas da interface, por exemplo, ao definir uma condição de fonte de dados.
Ele também está disponível sempre que for necessário definir parâmetros de ação que exijam manipulações de dados específicos. Você pode usar os dados provenientes dos eventos ou informações adicionais recuperadas da fonte de dados. Em uma jornada, a lista exibida de campos de evento é contextual e varia de acordo com os eventos adicionados na jornada.

O editor de expressão avançado oferece um conjunto de funções e operadores integrados, permitindo manipular valores e definir uma expressão que se ajuste especificamente às suas necessidades. O editor de expressão avançado também permite definir os valores do parâmetro de fonte de dados externa, manipular campos de mapa e coleções, como eventos de experiência.

![](../assets/journey65.png)

_A interface do editor de expressão avançado_

O editor avançado de expressões pode ser usado para:

* criar [condições avançadas](../building-journeys/condition-activity.md#about_condition) em fontes de dados e informações do evento
* definir [atividades de espera](../building-journeys/wait-activity.md#custom) personalizadas
* definir mapeamento de parâmetros de ação

Quando possível, você pode alternar entre os dois modos usando o botão **[!UICONTROL Advanced mode]** / **[!UICONTROL Simple mode]**. O modo simples é descrito [aqui](../building-journeys/condition-activity.md#about_condition).

>[!NOTE]
>
>As condições podem ser definidas no editor de expressão simples ou avançado. Eles sempre retornam um tipo booleano.
>
>Parâmetros de ações podem ser definidos selecionando campos ou por meio do editor de expressão avançado. Eles retornam um tipo de dados específico de acordo com a expressão.

## Acessar o editor de expressão avançado {#section_fdz_4nj_cjb}

Você pode acessar o editor de expressão avançado de diferentes maneiras:

* Ao criar uma condição de fonte de dados, você pode acessar o editor avançado clicando em **[!UICONTROL Advanced mode]**.

   ![](../assets/journeyuc2_33.png)

* Ao criar um temporizador personalizado, o editor avançado será exibido diretamente.
* Ao mapear o parâmetro de ação, clique em **[!UICONTROL Advanced mode]**.

## Descobrir a interface{#section_otq_tnj_cjb}

Nesta tela você pode escrever manualmente a expressão.

![](../assets/journey70.png)

Na parte esquerda da tela são exibidos os campos e as funções disponíveis:

* **[!UICONTROL Events]**: escolha um dos campos recebidos a partir do evento de entrada. A lista exibida dos campos do evento é contextual e varia de acordo com os eventos adicionados na jornada.
* **[!UICONTROL Data Sources]**: escolha na lista de campos disponíveis nos grupos de campos de suas fontes de dados.
* **[!UICONTROL Functions]**: escolha entre uma lista de funções integradas que permitem fazer uma filtragem complexa. As funções são organizadas por categorias.

![](../assets/journey65.png)

Um mecanismo de autopreenchimento exibe sugestões contextuais.

![](../assets/journey68.png)

Um mecanismo de validação de sintaxe verifica a integridade do código. Erros são exibidos na parte superior do editor.

![](../assets/journey69.png)

**Necessidade de parâmetros ao criar condições com o editor de expressão avançado**

If you select a field from an external data source requiring a parameter to be called (see [this page](../datasource/external-data-sources.md). Por exemplo, em uma fonte de dados relacionada ao clima, um parâmetro frequentemente usado será &quot;cidade&quot;. Como resultado, você deve selecionar onde deseja obter o parâmetro cidade. As funções também podem ser aplicadas aos parâmetros para executar alterações de formato ou concatenações.

![](../assets/journeyuc2_19.png)

Para casos de uso mais complexos, caso queira incluir os parâmetros da fonte de dados na expressão principal, é possível definir os valores usando a palavra-chave &quot;params&quot;. Consulte [esta página](../expression/field-references.md).
