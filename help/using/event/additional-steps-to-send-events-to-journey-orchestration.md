---
product: adobe campaign
title: Etapas adicionais para enviar eventos para o Journey Orchestration
description: Saiba mais sobre as etapas adicionais para enviar eventos para o Journey Orchestration
feature: Jornadas
role: Business Practitioner
level: Intermediate
exl-id: 11e337c6-5e05-4898-9953-b6b821af8fd1
source-git-commit: fb6bdb60ac70a94a62956a306bedee9cb607e2a2
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 2%

---

# Etapas adicionais para enviar eventos para [!DNL Journey Orchestration] {#concept_xrz_n1q_y2b}

>[!NOTE]
>
>Ao criar um evento, [!DNL Journey Orchestration] gera automaticamente uma ID para esse evento. O sistema que envia o evento não deve gerar uma ID, mas deve usar a disponível na pré-visualização de carga. Consulte [esta página](../event/previewing-the-payload.md).

Para configurar eventos a serem enviados para **[!UICONTROL Streaming Ingestion APIs]** e serem usados em [!DNL Journey Orchestration], siga estas etapas:

1. Obtenha o URL de entrada das APIs do Adobe Experience Platform (consulte [APIs de assimilação de fluxo](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html)).
1. Copie a carga da pré-visualização de carga no menu **[!UICONTROL Event]**. Consulte [esta página](../event/defining-the-payload-fields.md).

Em seguida, é necessário configurar o sistema de dados que envia eventos para as APIs de assimilação de streaming usando a carga útil copiada:

1. Configure uma chamada POST API para o URL das APIs de assimilação de fluxo (chamada de entrada).
1. Use a carga copiada de [!DNL Journey Orchestration] no corpo (&quot;seção de dados&quot;) da chamada da API para APIs de assimilação de fluxo. Veja abaixo um exemplo
1. Determine onde obter todas as variáveis presentes na carga útil. Exemplo: se o evento tiver que transmitir o endereço, a carga colada mostrará &quot;endereço&quot;: &quot;string&quot;. &quot;string&quot; deve ser substituída pela variável que preencherá automaticamente o valor correto, o email da pessoa para a qual enviar uma mensagem. Observe que, na pré-visualização de carga, na seção **[!UICONTROL Header]** , preenchemos automaticamente muitos valores esperados para facilitar seu trabalho.
1. Selecione &quot;application/json&quot; como um tipo de corpo.
1. Passe a IMS Organization ID no cabeçalho usando a chave &quot;x-gw-ims-org-id&quot;. Para o valor , use sua IMS Organization ID (&quot;XXX@AdobeOrg&quot;).

Veja um exemplo de um evento de APIs de assimilação de fluxo:

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

Para facilitar a identificação do local onde colar a parte &quot;dados&quot;, você pode usar uma ferramenta de visualização JSON, como [https://jsonformatter.curiousconcept.com](https://jsonformatter.curiousconcept.com)

Para solucionar problemas de APIs de assimilação de fluxo, consulte esta [página](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/troubleshooting.html).
