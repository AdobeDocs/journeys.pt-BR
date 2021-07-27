---
product: adobe campaign
title: Grupos de campos
description: Saiba mais sobre grupos de campos
feature: Jornadas
role: User
level: Intermediate
exl-id: 6f7f2673-9080-4274-afa3-a0255798f78d
source-git-commit: e1ee5a488e9eb6fd8d175a2ab8989c73289ea708
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 1%

---

# Grupos de campos {#concept_ntl_ypt_52b}

Grupos de campos são conjuntos de campos que podem ser recuperados de uma fonte de dados e usados em uma jornada.

## Definição de grupos de campos {#section_dsz_kjd_fjb}

Para cada fonte de dados, você pode definir vários grupos de campos.

Por exemplo, você pode criar um grupo de campos com o número de telefone, o email, o nome e o endereço do perfil. Você poderá usar esses dados na jornada para criar condições. Por exemplo, você pode decidir enviar um SMS somente se o número de telefone do perfil não estiver vazio. Se estiver vazio, você pode enviar um email.

Mesmo que um nome padrão seja adicionado automaticamente, recomendamos que você dê um nome ao seu grupo de campos. Na verdade, o nome do grupo de campos estará visível para outros usuários em [!DNL Journey Orchestration]. Fornecer um nome relevante para grupos de campos é uma prática recomendada.

Quando um campo de fonte de dados é usado em uma jornada, o sistema recuperará todos os campos definidos para esse grupo de campos. Portanto, selecionar apenas os campos necessários para suas jornadas é uma prática recomendada. Isso reduzirá a latência de solicitação em suas jornadas, aumentando assim o desempenho. Observe que é possível adicionar mais campos facilmente posteriormente em grupos de campos.

O número de jornadas que usam um grupo de campos é exibido no campo **[!UICONTROL Used in]**. Você pode clicar no botão **[!UICONTROL View journeys]** para exibir a lista de jornadas usando esse grupo de campos.

>[!NOTE]
>
>Observe que, se um grupo de campos não tiver um campo, ele não será exibido no editor de expressão.

![](../assets/journey3bis.png)

## Ciclo de vida do grupo de campos {#section_abk_njd_fjb}

Você pode adicionar ou remover campos de um grupo de campos que não é usado em nenhum rascunho ou jornada ativa.

É possível adicionar, mas não é possível remover um campo de um grupo de campos usado em uma ou mais jornadas de rascunho ou ativas. Isso evitará quebrar jornadas.

Para excluir um campo de um grupo de campos usado em uma ou mais jornadas, siga estas etapas. Vamos usar um exemplo de um grupo de campos chamado &quot;Grupo de campos A&quot;.

1. Na lista de grupos de campos, coloque o cursor em &quot;Grupo de campos A&quot; e clique no ícone **[!UICONTROL Duplicate]** localizado à direita. Nomeie o grupo de campos duplicados como &quot;Grupo de campos B&quot;, por exemplo.
1. Em &quot;Grupo de campos B&quot;, remova os campos que não deseja mais.
1. Em &quot;Grupo de campos A&quot;, verifique onde esse grupo de campos é usado. Essas informações são exibidas no campo **[!UICONTROL Used in]**.
1. Abra todas as jornadas que usam &quot;Grupo de campos A&quot;.
1. Crie novas versões de cada uma dessas jornadas. Edite todas as atividades usando &quot;Grupo de campos A&quot; e selecione &quot;Grupo de campos B&quot;.
1. Pare as versões antigas de jornadas que usam o &quot;Grupo de campos A&quot;. Você não deve ter jornada usando &quot;Grupo de campos A&quot;.
1. Remova &quot;Grupo de campos A&quot; como ele não é mais usado.
