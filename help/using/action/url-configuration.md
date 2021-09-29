---
product: adobe campaign
title: Configurar o URL
description: Saiba mais sobre a configuração do URL
feature: Journeys
role: User
level: Intermediate
exl-id: e7cba6c4-a231-44f9-927a-10115e7ab1dd
source-git-commit: 2a93bce42ea9f1f21d70c68da3dbc36844dafd1b
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 4%

---

# Configurar o URL {#concept_gbg_1f1_2gb}

Ao configurar uma ação personalizada, você precisa definir os seguintes parâmetros **[!UICONTROL URL Configuration]**:

![](../assets/journeyurlconfiguration.png)

1. No campo **[!UICONTROL URL]** , especifique o URL do serviço externo:

   * Se o URL for estático, insira o URL neste campo.

   * Se o URL incluir um caminho dinâmico, insira apenas a parte estática do URL, ou seja, o esquema, o host, a porta e, opcionalmente, uma parte estática do caminho.

      Exemplo: `https://xxx.yyy.com/somethingstatic/`

      Você especificará o caminho dinâmico do URL ao adicionar a ação personalizada a uma jornada. [Saiba mais](../building-journeys/using-custom-actions.md).
   >[!NOTE]
   >
   >Por motivos de segurança, recomendamos que você use o esquema HTTPS para o URL. Não permitimos o uso de endereços Adobe que não são públicos e o uso de endereços IP.
   >
   >Somente as portas padrão são permitidas ao definir uma ação personalizada: 80 para http e 443 para https.

1. Selecione a chamada **[!UICONTROL Method]**: pode ser **[!UICONTROL POST]** ou **[!UICONTROL PUT]**.
1. Na seção **[!UICONTROL Headers]** , defina os cabeçalhos HTTP da mensagem de solicitação a ser enviada ao serviço externo:
   1. Para adicionar um campo de cabeçalho, clique em **[!UICONTROL Add a header field]**.
   1. Insira a chave do campo de cabeçalho.
   1. Para definir um valor dinâmico para o par de valores chave, selecione **[!UICONTROL Variable]**. Caso contrário, selecione **[!UICONTROL Constant]**.

      Por exemplo, para um carimbo de data e hora, é possível definir um valor dinâmico.

   1. Se você selecionou **[!UICONTROL Constant]**, insira o valor constante.

      Se tiver selecionado **[!UICONTROL Variable]**, você especificará essa variável ao adicionar a ação personalizada a uma jornada. [Saiba mais](../building-journeys/using-custom-actions.md).

      ![](../assets/journeyurlconfiguration2.png)

   1. Para excluir um campo de cabeçalho, aponte para o campo de cabeçalho e clique no ícone **[!UICONTROL Delete]**.
   Os campos de cabeçalho **[!UICONTROL Content-Type]** e **[!UICONTROL Charset]** são definidos por padrão. Não é possível modificar ou excluir esses campos.

   Após adicionar a ação personalizada a uma jornada, você ainda poderá adicionar campos de cabeçalho a ela se a jornada estiver em status de rascunho. Se não quiser que a jornada seja afetada por alterações de configuração, duplique a ação personalizada e adicione os campos de cabeçalho à nova ação personalizada.

   >[!NOTE]
   >
   >Os cabeçalhos são validados de acordo com as regras de análise de campo. [Saiba mais](https://tools.ietf.org/html/rfc7230#section-3.2.4).
