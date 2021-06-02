---
product: adobe campaign
title: Criação de um perfil de teste
description: Saiba mais sobre a criação de perfil de teste
exl-id: f1be46a8-04b9-4f40-b18e-9099099d2e1c
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '677'
ht-degree: 3%

---

# Criar perfis de teste {#create-test-profiles}

Os perfis de teste são necessários ao usar o modo de teste em uma jornada. Para saber como usar o modo de teste, consulte [esta seção](../building-journeys/testing-the-journey.md).

Há diferentes maneiras de criar um perfil de teste no Adobe Experience Platform. Nesta documentação, nos concentramos em dois métodos: carregar um arquivo [csv](../building-journeys/creating-test-profiles.md#create-test-profiles-csv) e usar [chamadas de API](../building-journeys/creating-test-profiles.md#create-test-profiles-api). Você também pode fazer upload de um arquivo json em um conjunto de dados, consulte a [Documentação de assimilação de dados](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/ingest-batch-data.html#add-data-to-dataset).

Esses métodos de importação também permitem atualizar atributos de perfil. Dessa forma, você pode transformar um perfil existente em um perfil de teste. Basta usar um arquivo ou uma chamada de API semelhante e incluir apenas o campo &quot;testProfile&quot; com o valor &quot;true&quot;.

Criar um perfil de teste é semelhante à criação de perfis regulares no Adobe Experience Platform. Para obter mais informações, consulte a [documentação do Perfil do cliente em tempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html).

## Pré-requisitos{#test-profile-prerequisites}

Para criar perfis, primeiro é necessário criar um esquema e um conjunto de dados no Adobe Experience Platform.

Primeiro, você precisa **criar um schema**. Siga estas etapas:

1. No Adobe Experience Platform, clique em **[!UICONTROL Schemas]**, no menu à esquerda.
   ![](../assets/test-profiles-0.png)
1. Clique em **[!UICONTROL Create schema]**, na parte superior direita, e selecione um tipo de schema, por exemplo **[!UICONTROL XDM Individual Profile]**.
   ![](../assets/test-profiles-1.png)
1. Escolha um nome para o esquema.
1. Na seção **[!UICONTROL Mixins]**, clique em **[!UICONTROL Add]**.
   ![](../assets/test-profiles-1-bis.png)
1. Selecione as combinações apropriadas. Adicione a mistura **[!UICONTROL Profile test details]**. Clique em **[!UICONTROL Add mixin]**.
   ![](../assets/test-profiles-1-ter.png)
A lista de mixins é exibida na tela de visão geral do schema.

   ![](../assets/test-profiles-2.png)
1. Na lista de campos, clique no campo que deseja definir como a identidade primária.
   ![](../assets/test-profiles-3.png)
1. No painel direito **[!UICONTROL Field properties]**, marque as opções **[!UICONTROL Identity]** e **[!UICONTROL Primary Identity]** e selecione um namespace. Se quiser que a identidade primária seja um endereço de email, escolha o namespace **[!UICONTROL Email]**. Clique em **[!UICONTROL Apply]**.
   ![](../assets/test-profiles-4.png)
1. Selecione o schema e habilite a opção **[!UICONTROL Profile]** no **[!UICONTROL Schema properties]**.
   ![](../assets/test-profiles-5.png)
1. Clique em **[!UICONTROL Save]**.

>[!NOTE]
>
>Para obter mais informações sobre a criação do schema, consulte a [documentação XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html#prerequisites).

Em seguida, é necessário **criar o conjunto de dados** no qual os perfis serão importados. Siga estas etapas:

1. No Adobe Experience Platform, clique em **[!UICONTROL Datasets]**, no menu esquerdo, em seguida, clique em **[!UICONTROL Create dataset]**.
   ![](../assets/test-profiles-6.png)
1. Escolha **[!UICONTROL Create dataset from schema]**.
   ![](../assets/test-profiles-7.png)
1. Selecione o schema criado anteriormente e clique em **[!UICONTROL Next]**.
   ![](../assets/test-profiles-8.png)
1. Escolha um nome e clique em **[!UICONTROL Finish]**.
   ![](../assets/test-profiles-9.png)
1. Habilite a opção **[!UICONTROL Profile]**.
   ![](../assets/test-profiles-10.png)

>[!NOTE]
>
> Para obter mais informações sobre a criação do conjunto de dados, consulte a [Documentação do Serviço de Catálogo](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html#getting-started).

## Criação de um perfil de teste usando um arquivo csv{#create-test-profiles-csv}

No Adobe Experience Platform, é possível criar perfis carregando um arquivo csv contendo os diferentes campos de perfil no conjunto de dados. Este é o método mais fácil.

1. Crie um arquivo csv simples usando um software de planilha.
1. Adicione uma coluna para cada campo necessário. Certifique-se de adicionar o campo de identidade primário (&quot;personID&quot; no nosso exemplo acima) e o campo &quot;testProfile&quot; definidos como &quot;true&quot;.
   ![](../assets/test-profiles-11.png)
1. Adicione uma linha por perfil e preencha os valores de cada campo.
   ![](../assets/test-profiles-12.png)
1. Salve a planilha como um arquivo csv. Verifique se as vírgulas são usadas como separadores.
1. No Adobe Experience Platform, clique em **[!UICONTROL Workflows]**, no menu à esquerda.
   ![](../assets/test-profiles-14.png)
1. Escolha **[!UICONTROL Map CSV to XDM schema]** e clique em **[!UICONTROL Launch]**.
   ![](../assets/test-profiles-16.png)
1. Selecione o conjunto de dados para o qual deseja importar os perfis. Clique em **[!UICONTROL Next]**.
   ![](../assets/test-profiles-17.png)
1. Clique em **[!UICONTROL Choose files]** e selecione o arquivo csv. Quando o arquivo for carregado, clique em **[!UICONTROL Next]**.
   ![](../assets/test-profiles-18.png)
1. Mapeie os campos csv de origem para os campos de esquema e clique em **[!UICONTROL Finish]**.
   ![](../assets/test-profiles-19.png)
1. A importação de dados é iniciada. O status será movido de **[!UICONTROL Processing]** para **[!UICONTROL Success]**. Clique em **[!UICONTROL Preview data set]**, na parte superior direita.
   ![](../assets/test-profiles-20.png)
1. Verifique se os perfis de teste foram adicionados corretamente.
   ![](../assets/test-profiles-21.png)

Seus perfis de teste são adicionados e agora podem ser usados ao testar uma jornada. Consulte [esta seção](../building-journeys/testing-the-journey.md).
>[!NOTE]
>
> Para obter mais informações sobre importações de csv, consulte a [documentação sobre assimilação de dados](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/map-a-csv-file.html#tutorials).

## Criar perfis de teste usando chamadas de API{#create-test-profiles-api}

Também é possível criar perfis de teste por meio de chamadas de API. Consulte esta [página](https://docs.adobe.com/content/help/pt-BR/experience-platform/profile/home.html).

Você deve usar um Esquema de perfil que contenha a combinação &quot;Detalhes do teste de perfil&quot;. O sinalizador testProfile faz parte dessa mistura.

Ao criar um perfil, transmita o valor: testProfile = true.

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
