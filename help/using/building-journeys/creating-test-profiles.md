---
product: adobe campaign
title: Criação de um perfil de teste
description: Saiba mais sobre a criação de perfil de teste
exl-id: f1be46a8-04b9-4f40-b18e-9099099d2e1c
source-git-commit: fb6bdb60ac70a94a62956a306bedee9cb607e2a2
workflow-type: tm+mt
source-wordcount: '675'
ht-degree: 5%

---

# Criar perfis de teste {#create-test-profiles}

Os perfis de teste são necessários ao usar o modo de teste em uma jornada. Para saber como usar o modo de teste, consulte [nesta seção](../building-journeys/testing-the-journey.md).

Há diferentes maneiras de criar um perfil de teste no Adobe Experience Platform. Nesta documentação, nos concentramos em dois métodos: fazer upload de um [arquivo csv](../building-journeys/creating-test-profiles.md#create-test-profiles-csv) e usando [Chamadas de API](../building-journeys/creating-test-profiles.md#create-test-profiles-api). Também é possível fazer upload de um arquivo json em um conjunto de dados, consulte [Documentação de assimilação de dados](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/ingest-batch-data.html#add-data-to-dataset).

Esses métodos de importação também permitem atualizar os atributos do perfil. Dessa forma, você pode transformar um perfil existente em um perfil de teste. Basta usar um arquivo semelhante ou uma chamada de API e incluir apenas o campo &quot;testProfile&quot; com o valor &quot;true&quot;.

A criação de um perfil de teste é semelhante à criação de perfis comuns no Adobe Experience Platform. Para obter mais informações, consulte [Documentação de Perfil do cliente em tempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=pt-BR).

## Pré-requisitos{#test-profile-prerequisites}

Para criar perfis, primeiro é necessário criar um esquema e um conjunto de dados na Adobe Experience Platform.

Primeiro, é necessário **criar um esquema**. Siga estas etapas:

1. No Adobe Experience Platform, clique em **[!UICONTROL Schemas]**, no menu esquerdo.
   ![](../assets/test-profiles-0.png)
1. Clique em **[!UICONTROL Create schema]**, na parte superior direita e selecione um tipo de esquema, por exemplo **[!UICONTROL XDM Individual Profile]**.
   ![](../assets/test-profiles-1.png)
1. Escolha um nome para o esquema.
1. Na seção **[!UICONTROL Mixins]**, clique em **[!UICONTROL Add]**.
   ![](../assets/test-profiles-1-bis.png)
1. Selecione os mixins apropriados. Certifique-se de adicionar o **[!UICONTROL Profile test details]** mixin. Clique em **[!UICONTROL Add mixin]**.
   ![](../assets/test-profiles-1-ter.png)
A lista de mixins é exibida na tela de visão geral do schema.
   ![](../assets/test-profiles-2.png)
1. Na lista de campos, clique no campo que você deseja definir como a identidade principal.
   ![](../assets/test-profiles-3.png)
1. No **[!UICONTROL Field properties]** painel direito, marque a opção **[!UICONTROL Identity]** e **[!UICONTROL Primary Identity]** e selecione um namespace. Se quiser que a identidade principal seja um endereço de email, escolha a **[!UICONTROL Email]** namespace. Clique em **[!UICONTROL Apply]**.
   ![](../assets/test-profiles-4.png)
1. Selecione o esquema e ative a variável **[!UICONTROL Profile]** opção no **[!UICONTROL Schema properties]**.
   ![](../assets/test-profiles-5.png)
1. Clique em **[!UICONTROL Save]**.

>[!NOTE]
>
>Para obter mais informações sobre criação de schema, consulte [Documentação XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html#prerequisites).

Então você precisa **criar o conjunto de dados** na qual os perfis serão importados. Siga estas etapas:

1. No Adobe Experience Platform, clique em **[!UICONTROL Datasets]**, no menu esquerdo e clique em **[!UICONTROL Create dataset]**.
   ![](../assets/test-profiles-6.png)
1. Escolher **[!UICONTROL Create dataset from schema]**.
   ![](../assets/test-profiles-7.png)
1. Selecione o schema criado anteriormente e clique em **[!UICONTROL Next]**.
   ![](../assets/test-profiles-8.png)
1. Escolha um nome e clique em **[!UICONTROL Finish]**.
   ![](../assets/test-profiles-9.png)
1. Ativar o **[!UICONTROL Profile]** opção.
   ![](../assets/test-profiles-10.png)

>[!NOTE]
>
> Para obter mais informações sobre a criação de conjuntos de dados, consulte a [Documentação do Serviço de catálogo](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html#getting-started).

## Criação de um perfil de teste usando um arquivo csv{#create-test-profiles-csv}

No Adobe Experience Platform, é possível criar perfis carregando um arquivo csv contendo os diferentes campos de perfil no conjunto de dados. Esse é o método mais fácil.

1. Crie um arquivo csv simples usando um software de planilha.
1. Adicione uma coluna para cada campo necessário. Adicione o campo de identidade principal (&quot;personID&quot; no exemplo acima) e o campo &quot;testProfile&quot; definido como &quot;true&quot;.
   ![](../assets/test-profiles-11.png)
1. Adicione uma linha por perfil e preencha os valores para cada campo.
   ![](../assets/test-profiles-12.png)
1. Salve a planilha como um arquivo csv. Verifique se as vírgulas são usadas como separadores.
1. No Adobe Experience Platform, clique em **[!UICONTROL Workflows]**, no menu esquerdo.
   ![](../assets/test-profiles-14.png)
1. Escolher **[!UICONTROL Map CSV to XDM schema]** e, em seguida, clique em **[!UICONTROL Launch]**.
   ![](../assets/test-profiles-16.png)
1. Selecione o conjunto de dados para o qual você deseja importar os perfis. Clique em **[!UICONTROL Next]**.
   ![](../assets/test-profiles-17.png)
1. Clique em **[!UICONTROL Choose files]** e selecione o arquivo csv. Quando o arquivo for carregado, clique em **[!UICONTROL Next]**.
   ![](../assets/test-profiles-18.png)
1. Mapeie os campos do csv de origem para os campos de esquema e clique em **[!UICONTROL Finish]**.
   ![](../assets/test-profiles-19.png)
1. A importação de dados é iniciada. O status será movido de **[!UICONTROL Processing]** para **[!UICONTROL Success]**. Clique em **[!UICONTROL Preview data set]**, no canto superior direito.
   ![](../assets/test-profiles-20.png)
1. Verifique se os perfis de teste foram adicionados corretamente.
   ![](../assets/test-profiles-21.png)

Seus perfis de teste são adicionados e agora podem ser usados ao testar uma jornada. Consulte [esta seção](../building-journeys/testing-the-journey.md).
>[!NOTE]
>
> Para obter mais informações sobre importações de csv, consulte [Documentação de assimilação de dados](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/map-a-csv-file.html#tutorials).

## Criar perfis de teste usando chamadas de API{#create-test-profiles-api}

Você também pode criar perfis de teste por meio de chamadas de API. Consulte esta [página](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=pt-BR).

Você deve usar um esquema de Perfil que contenha a combinação &quot;Detalhes do teste de perfil&quot;. O sinalizador testProfile faz parte deste mixin.

Ao criar um perfil, passe o valor: testProfile = true.

Observe que você também pode atualizar um perfil existente para alterar seu sinalizador testProfile para &quot;true&quot;.

Este é um exemplo de uma chamada de API para criar um perfil de teste:

```
curl -X POST \
'https://dcs.adobedc.net/collection/xxxxxxxxxxxxxx' \
-H 'Cache-Control: no-cache' \
-H 'Content-Type: application/json' \
-H 'Postman-Token: xxxxx' \
-H 'cache-control: no-cache' \
-H 'x-api-key: xxxxx' \
-H 'x-gw-ims-org-id: xxxxx' \
-d '{
"header": {
"msgType": "xdmEntityCreate",
"msgId": "xxxxx",
"msgVersion": "xxxxx",
"xactionid":"xxxxx",
"datasetId": "xxxxx",
"imsOrgId": "xxxxx",
"source": {
"name": "Postman"
},
"schemaRef": {
"id": "https://example.adobe.com/mobile/schemas/xxxxx",
"contentType": "application/vnd.adobe.xed-full+json;version=1"
}
},
"body": {
"xdmMeta": {
"schemaRef": {
"contentType": "application/vnd.adobe.xed-full+json;version=1"
}
},
"xdmEntity": {
"_id": "xxxxx",
"_mobile":{
"ECID": "xxxxx"
},
"testProfile":true
}
}
}'
```
