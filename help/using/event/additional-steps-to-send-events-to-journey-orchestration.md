---
product: adobe campaign
title: Etapas adicionais para enviar eventos ao Journey Orchestration
description: Saiba mais sobre as etapas adicionais para enviar eventos para o Journey Orchestration
feature: Journeys
role: User
level: Intermediate
exl-id: 11e337c6-5e05-4898-9953-b6b821af8fd1
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 17%
---
# Etapas adicionais para enviar eventos para [!DNL Journey Orchestration] {#concept_xrz_n1q_y2b}



>[!CAUTION]
>
>**Está procurando pelo Adobe Journey Optimizer**? Clique [aqui](https://experienceleague.adobe.com/pt-br/docs/journey-optimizer/using/ajo-home){target="_blank"} para acessar a documentação do Journey Optimizer.
>
>
>_Essa documentação refere-se ao material herdado do Journey Orchestration, que foi substituído pelo Journey Optimizer. Entre em contato com a equipe de contas em caso de dúvidas sobre como acessar o Journey Orchestration ou o Journey Optimizer._


>[!NOTE]
>
>Ao criar um evento, [!DNL Journey Orchestration] gera automaticamente uma ID para esse evento. O sistema que envia o evento não deve gerar uma ID, mas usar a disponível na pré-visualização de carga. Consulte [esta página](../event/previewing-the-payload.md).

Para configurar eventos a serem enviados para **[!UICONTROL Streaming Ingestion APIs]** e a serem usados em [!DNL Journey Orchestration], você precisa seguir estas etapas:

1. Obtenha o URL de entrada das APIs do Adobe Experience Platform (consulte [APIs de assimilação de streaming](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=pt-BR)).
1. Copie a carga da pré-visualização de carga no menu **[!UICONTROL Event]**. Consulte [esta página](../event/defining-the-payload-fields.md).

Em seguida, é necessário configurar o sistema de dados que envia eventos para as APIs de assimilação de streaming usando a carga útil copiada:

1. Configure uma chamada de API POST para o URL das APIs de assimilação de streaming (chamada de entrada).
1. Use a carga copiada de [!DNL Journey Orchestration] no corpo (&quot;seção de dados&quot;) da chamada da API para as APIs de assimilação de fluxo. Veja um exemplo abaixo
1. Determine onde obter todas as variáveis presentes na carga. Exemplo: se o evento deve transmitir o endereço, a carga colada mostrará &quot;address&quot;: &quot;string&quot;. &quot;string&quot; deve ser substituída pela variável que preencherá automaticamente o valor correto, o email da pessoa para a qual enviar uma mensagem. Observe que na pré-visualização de carga, na seção **[!UICONTROL Header]**, preenchemos automaticamente muitos valores para facilitar seu trabalho.
1. Selecione &quot;application/json&quot; como um tipo de corpo.
1. Passe sua IMS Organization ID no cabeçalho usando a chave &quot;x-gw-ims-org-id&quot;. Para o valor, use sua IMS Organization ID (&quot;XXX@AdobeOrg&quot;).

Este é um exemplo de um evento de APIs de assimilação de fluxo:

```
{
    "header": {
        "msgType": "xdmEntityCreate",
        "msgId": "c25585b9-252e-431d-b562-e73da70c04e7",
        "msgVersion": "1.0",
        "xactionId": "f5995abe-c49d-4848-9577-a7a4fc2996fb",
        "datasetId": "string - required if you want the data to land in a specific dataset - not mandatory",
        "imsOrgId": "XXX@AdobeOrg",
        "schemaRef": {
            "id": "XXX",
            "contentType": "application/vnd.adobe.xed-full+json;version=1"
        },
        "source": {
            "name": "Journeys"
        }
    },
    "body": {
        "xdmMeta": {
            "schemaRef": {
                "id": "XXX",
                "contentType": "application/vnd.adobe.xed-full+json;version=1"
            }
        },
        "xdmEntity": {
            "_instance_name": {
                "person": {
                    "firstName": "string",
                    "lastName": "string",
                    "gender": "string",
                    "birthYear": 10,
                    "emailAddress": "string"
                }
            },
            "identityMap": {
                "Email": [
                {
                    "id": "string"
                    }
                ]
            },
            "_id": "string",
            "timestamp": "2018-05-29T00:00:00.000Z",
            "_experience": {
                "campaign": {
                    "orchestration": {
                    "eventID": "XXX"
                    }
                }
            }
        }
    }
}
```

Para facilitar a identificação do local onde colar a parte de &quot;dados&quot;, você pode usar uma ferramenta de visualização JSON, como [https://jsonformatter.curiousconcept.com](https://jsonformatter.curiousconcept.com)

Para solucionar problemas de APIs de assimilação de fluxo, consulte esta [página](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/troubleshooting.html).
