---
product: adobe campaign
title: Configuração de fontes de dados
description: Saiba como configurar a fonte de dados para o caso de uso avançado do jornada
feature: Jornadas
role: User
level: Intermediate
exl-id: 2cfa4397-fe8f-44b3-b219-2fd5d3bdd156
source-git-commit: e1ee5a488e9eb6fd8d175a2ab8989c73289ea708
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 15%

---

# Configuração de fontes de dados {#concept_vml_hdy_w2b}

Em nosso caso de uso, queremos usar dados de personalização para nossas mensagens. Também precisamos verificar se a pessoa é um membro do programa de fidelidade e não foi contatado nas últimas 24 horas. Essas informações são armazenadas no banco de dados do Perfil do cliente em tempo real. O **usuário técnico** precisa configurar a fonte de dados do Adobe Experience Platform para recuperar esses campos.

Para obter informações adicionais sobre a configuração da fonte de dados, consulte [esta página](../datasource/about-data-sources.md).

1. No painel de menus, selecione **[!UICONTROL Admin]**. Na seção **[!UICONTROL Data sources]**, clique em **[!UICONTROL Manage]**.
1. Selecione a fonte de dados integrada do Adobe Experience Platform.

   ![](../assets/journey23.png)

1. Nos campos de grupo pré-configurados, verifique se os seguintes campos estão selecionados:

   * _pessoa > nome > nome_
   * _pessoa > nome > sobrenome_
   * _email pessoal > endereço_

1. Clique em **[!UICONTROL Add a New Field Group]**, selecione um schema **[!UICONTROL Profiles]** e adicione o campo **Loyalty member** para nossa condição. O campo **Loyalty member** é um campo personalizado e foi adicionado no XDM: &quot;_customer > marlton > loyaltyMember&quot;

   ![](../assets/journeyuc2_6.png)

1. Clique em **[!UICONTROL Add a New Field Group]**, selecione um schema **[!UICONTROL ExperienceEvent]** e escolha os campos necessários para sua condição no número de mensagens enviadas em um determinado período: _carimbo de data e hora_ para a data e _directMarketing > envia > valor_ para o número de mensagens enviadas.

   ![](../assets/journeyuc2_7.png)

1. Clique em **[!UICONTROL Save]**.

Também precisamos verificar se a pessoa tem uma reserva no sistema de reservas do hotel. O **usuário técnico** precisa configurar uma segunda fonte de dados para recuperar esse campo.

1. Na lista de fontes de dados, clique em **[!UICONTROL Add]** para adicionar uma nova fonte de dados externa para definir a conexão com seu sistema de reservas de hotel.

   ![](../assets/journeyuc2_9.png)

1. Insira um nome para a fonte de dados e a URL do serviço externo, por exemplo: _https://marlton.com/reservation_

   >[!CAUTION]
   >
   >Recomendamos o uso de HTTPS por motivos de segurança.

1. Configure a autenticação dependendo da configuração do serviço externo: **[!UICONTROL No authentication]**, **[!UICONTROL Basic]**, **[!UICONTROL Custom]** ou **[!UICONTROL API key]**. No nosso exemplo, escolhemos &quot;Básico&quot; para o tipo e especificamos o nome de usuário e a senha para a chamada de API.

   ![](../assets/journeyuc2_10.png)

1. Clique em **[!UICONTROL Add a New Field Group]** para definir as informações a serem recuperadas e os parâmetros da API. Para nosso exemplo, há apenas um parâmetro (a id), portanto, precisamos criar um grupo de campos com as seguintes informações:

   * **[!UICONTROL Method]**: selecione o método POST ou GET. No nosso caso, selecionamos o método GET.
   * **[!UICONTROL Response Payload]**: clique dentro do  **[!UICONTROL Payload]** campo e cole um exemplo do payload. Verifique se os tipos de campo estão corretos. Cada vez que a API é chamada, o sistema recuperará todos os campos incluídos no exemplo de carga útil. No nosso exemplo, a carga contém apenas o status da reserva:

   ```
   {
       "reservation" : true
   }
   ```

   * **[!UICONTROL Dynamic Values]**: insira o parâmetro correspondente à chave usada para identificar cada cliente, &quot;id&quot; no nosso exemplo. O valor desse parâmetro será definido na jornada.

   ![](../assets/journeyuc2_11.png)

1. Clique em **[!UICONTROL Save]**.

   As fontes de dados agora estão configuradas e prontas para serem usadas na jornada.
