---
title: Etapas adicionais para enviar eventos para a Journey Orchestration
description: Saiba mais sobre as etapas adicionais para enviar eventos para a Journey Orchestration
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1e7765352ec91be50b51633927ab038d3492b71a
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 3%

---



# Additional steps to send events to [!DNL Journey Orchestration] {#concept_xrz_n1q_y2b}

>[!NOTE]
>
>Ao criar um evento, [!DNL Journey Orchestration] gera automaticamente uma ID para esse evento. O sistema que envia o evento não deve gerar uma ID; ele deve usar a que está disponível na pré-visualização de carga. Consulte [](../event/previewing-the-payload.md).

Para configurar eventos a serem enviados para **[!UICONTROL Streaming Ingestion APIs]** e a serem usados em [!DNL Journey Orchestration], siga estas etapas:

1. Obtenha o URL de entrada das APIs da plataforma de dados (consulte APIs [de ingestão de](https://docs.adobe.com/content/help/pt-BR/experience-platform/ingestion/streaming/overview.html)transmissão contínua).
1. Copie a carga da pré-visualização de carga no **[!UICONTROL Event]** menu. Consulte [](../event/defining-the-payload-fields.md).

Em seguida, é necessário configurar o sistema de dados que envia eventos para as APIs de ingestão de fluxo usando a carga copiada:

1. Configure uma chamada POST API para o URL das APIs de ingestão de transmissão (chamado de entrada).
1. Use a carga copiada [!DNL Journey Orchestration] no corpo (&quot;seção de dados&quot;) da chamada da API para APIs de ingestão de fluxo. Veja abaixo um exemplo
1. Determine onde obter todas as variáveis presentes na carga. Exemplo: se o evento tiver que indicar o endereço, a carga colada mostrará o &quot;endereço&quot;: &quot;string&quot;. &quot;string&quot; deve ser substituída pela variável que preencherá automaticamente o valor correto, o e-mail da pessoa para quem enviar uma mensagem. Observe que na pré-visualização de carga, na **[!UICONTROL Header]** seção, preenchemos automaticamente muitos valores esperados para facilitar seu trabalho.
1. Selecione &quot;application/json&quot; como um tipo de corpo.
1. Passe sua ID ORG IMS no cabeçalho usando a chave &quot;x-gw-ims-org-id&quot;. Para o valor, use sua ID ORG IMS (&quot;XXX@AdobeOrg&quot;).

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

Para solucionar problemas de APIs de ingestão de fluxo, consulte esta [página](https://docs.adobe.com/content/help/en/experience-platform/ingestion/streaming/troubleshooting.html).
