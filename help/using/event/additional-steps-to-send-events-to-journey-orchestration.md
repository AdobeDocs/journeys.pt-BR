---
product: adobe campaign
title: Etapas adicionais para enviar eventos para o Journey Orchestration
description: Saiba mais sobre as etapas adicionais para enviar eventos para o Journey Orchestration
feature: Journeys
role: User
level: Intermediate
exl-id: 11e337c6-5e05-4898-9953-b6b821af8fd1
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 4%

---

# Etapas adicionais para enviar eventos ao [!DNL Journey Orchestration] {#concept_xrz_n1q_y2b}

>[!NOTE]
>
>Ao criar um evento, [!DNL Journey Orchestration] O gera automaticamente uma ID para esse evento. O sistema que envia o evento não deve gerar uma ID, mas usar a disponível na pré-visualização de carga. Consulte [esta página](../event/previewing-the-payload.md).

Para configurar eventos a serem enviados para o **[!UICONTROL Streaming Ingestion APIs]** e para serem utilizados em [!DNL Journey Orchestration], é necessário seguir estas etapas:

1. Obter o URL de entrada das APIs do Adobe Experience Platform (consulte [APIs de assimilação de fluxo](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=pt-BR)).
1. Copie o conteúdo da pré-visualização de carga no **[!UICONTROL Event]** menu. Consulte [esta página](../event/defining-the-payload-fields.md).

Em seguida, é necessário configurar o sistema de dados que envia eventos para as APIs de assimilação de streaming usando a carga útil copiada:

1. Configure uma chamada de API POST para o URL das APIs de assimilação de streaming (chamada de entrada).
1. Usar a carga copiada do [!DNL Journey Orchestration] no corpo (&quot;seção de dados&quot;) da chamada da API para as APIs de assimilação de streaming. Veja um exemplo abaixo
1. Determine onde obter todas as variáveis presentes na carga. Exemplo: se o evento deve transmitir o endereço, a carga colada mostrará &quot;address&quot;: &quot;string&quot;. &quot;string&quot; deve ser substituída pela variável que preencherá automaticamente o valor correto, o email da pessoa para a qual enviar uma mensagem. Observe que na pré-visualização de carga, no campo **[!UICONTROL Header]** preenchemos automaticamente muitos valores para facilitar o trabalho.
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
