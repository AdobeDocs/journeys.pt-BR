---
product: adobe campaign
solution: Journey Orchestration
title: Grupos de campos
description: Saiba mais sobre grupos de campos
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '589'
ht-degree: 0%

---



# Grupos de campos {#concept_ntl_ypt_52b}

Os grupos de campos são conjuntos de campos que você pode recuperar de uma fonte de dados e usar em uma jornada.

## Definindo grupos de campos {#section_dsz_kjd_fjb}

Para cada fonte de dados, é possível definir vários grupos de campos, cada um deles com uma duração específica do cache.

Por exemplo, você pode criar um grupo de campos com o número de telefone, o email, o nome e o endereço do perfil. Você poderá então usar esses dados em sua jornada para criar condições. Por exemplo, você pode decidir enviar um SMS somente se o número de telefone do perfil não estiver vazio. Se estiver vazio, você pode enviar um email.

Embora um nome padrão seja adicionado automaticamente, recomendamos que você atribua um nome ao grupo de campos. Na verdade, o nome do grupo de campos estará visível para outros usuários em [!DNL Journey Orchestration]. Dar um nome relevante aos grupos de campos é uma prática recomendada.

Quando um campo de fonte de dados é usado em uma jornada, o sistema recuperará todos os campos definidos para esse grupo de campos. Portanto, selecionar apenas os campos necessários para suas viagens é uma prática recomendada. Isso reduzirá a latência de solicitação em suas viagens, aumentando assim o desempenho. Observe que você pode adicionar mais campos facilmente em grupos de campos posteriormente.

**[!UICONTROL Cache duration]** também é importante, pois ajudará a otimizar o desempenho. A duração do cache significa que, em uma jornada, se os dados de um grupo de campos forem recuperados uma vez, o sistema armazenará o cache temporariamente. Se os mesmos dados forem necessários posteriormente na mesma jornada, o sistema não fará outra solicitação para a fonte de dados. A configuração da duração do cache deve ser adaptada para cada caso de uso. Se você precisar recuperar dados em tempo real, como status de reserva do hotel, informações meteorológicas ou o número de pontos de fidelidade, associará o grupo de campos que contém esses campos a uma curta duração do cache (1 segundo, por exemplo). Para campos que são atualizados com menos frequência (nome, gênero), você criará um segundo grupo de campos com uma duração de cache maior (5 dias, por exemplo).

O número de viagens que usam um grupo de campos é exibido no campo **[!UICONTROL Used in]**. Você pode clicar no botão **[!UICONTROL View journeys]** para exibir a lista de viagens usando esse grupo de campos.

>[!NOTE]
>
>Observe que, se um grupo de campos não tiver um campo, ele não será exibido no editor de expressões.

![](../assets/journey3bis.png)

## Ciclo de vida do grupo de campos {#section_abk_njd_fjb}

É possível adicionar ou remover campos de um grupo de campos que não seja usado em nenhum rascunho ou jornada ao vivo.

Você pode adicionar, mas não pode remover um campo de um grupo de campos usado em uma ou mais viagens de rascunho ou ao vivo. Isso evitará a quebra de viagens.

Para excluir um campo de um grupo de campo usado em uma ou mais viagens, siga estas etapas. Vamos usar um exemplo de um grupo de campo chamado &quot;Grupo de campo A&quot;.

1. Na lista de grupos de campos, posicione o cursor em &quot;Grupo de campos A&quot; e clique no ícone **[!UICONTROL Duplicate]** localizado à direita. Nomeie o grupo de campos duplicados como &quot;Grupo de campos B&quot;, por exemplo.
1. Em &quot;Grupo de campos B&quot;, remova os campos que não deseja mais.
1. Em &quot;Grupo de campos A&quot;, verifique onde esse grupo de campos é usado. Essas informações são exibidas no campo **[!UICONTROL Used in]**.
1. Abrir todas as viagens que utilizem o &quot;Grupo de Campo A&quot;.
1. Crie novas versões de cada uma dessas viagens. Edite todas as atividades usando &quot;Grupo de campos A&quot; e selecione &quot;Grupo de campos B&quot;.
1. Parar versões antigas de viagens que usam o &quot;Grupo de campo A&quot;. Você não deve ter nenhuma jornada usando o &quot;Grupo de campo A&quot;.
1. Remova o &quot;Grupo de campo A&quot;, pois ele não é mais usado.
