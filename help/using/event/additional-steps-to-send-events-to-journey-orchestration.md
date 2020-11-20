---
product: adobe campaign
solution: Journey Orchestration
title: Etapas adicionais para enviar evento
description: Saiba mais sobre as etapas adicionais para enviar evento
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 7%

---



# Additional steps to send events to [!DNL Journey Orchestration] {#concept_xrz_n1q_y2b}

>[!NOTE]
>
>Ao criar um evento, [!DNL Journey Orchestration] gera automaticamente uma ID para esse evento. O sistema que envia o evento não deve gerar uma ID; ele deve usar a que está disponível na pré-visualização de carga. Consulte [esta página](../event/previewing-the-payload.md).

Para configurar eventos a serem enviados para **[!UICONTROL Streaming Ingestion APIs]** e a serem usados em [!DNL Journey Orchestration], siga estas etapas:

1. Obtenha o URL de entrada das APIs do Adobe Experience Platform (consulte APIs [de ingestão de](https://docs.adobe.com/content/help/pt-BR/experience-platform/ingestion/streaming/overview.html)transmissão contínua).
1. Copie a carga da pré-visualização de carga no **[!UICONTROL Event]** menu. Consulte [esta página](../event/defining-the-payload-fields.md).

Em seguida, é necessário configurar o sistema de dados que envia eventos para as APIs de ingestão de fluxo usando a carga copiada:

1. Configure uma chamada de API POST para o URL das APIs de ingestão de transmissão (chamada de entrada).
1. Use a carga copiada [!DNL Journey Orchestration] no corpo (&quot;seção de dados&quot;) da chamada da API para APIs de ingestão de fluxo. Veja abaixo um exemplo
1. Determine onde obter todas as variáveis presentes na carga. Exemplo: se o evento tiver que indicar o endereço, a carga colada mostrará o &quot;endereço&quot;: &quot;string&quot;. &quot;string&quot; deve ser substituída pela variável que preencherá automaticamente o valor correto, o e-mail da pessoa para quem enviar uma mensagem. Observe que na pré-visualização de carga, na **[!UICONTROL Header]** seção, preenchemos automaticamente muitos valores esperados para facilitar seu trabalho.
1. Selecione &quot;application/json&quot; como um tipo de corpo.
1. Transmita a ID de empresa do IMS no cabeçalho usando a chave &quot;x-gw-ims-org-id&quot;. Para o valor, use a ID de empresa IMS (&quot;XXX@AdobeOrg&quot;).

Este é um exemplo de um evento de APIs de ingestão de transmissão:

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

Para facilitar a identificação do local onde a parte &quot;dados&quot; deve ser colada, é possível usar uma ferramenta de visualização JSON, como [https://jsonformatter.curiousconcept.com](https://jsonformatter.curiousconcept.com)

Para solucionar problemas de APIs de ingestão de fluxo, consulte esta [página](https://docs.adobe.com/content/help/pt-BR/experience-platform/ingestion/streaming/troubleshooting.html).
