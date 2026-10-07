---
product: adobe campaign
title: interseção
description: Saiba mais sobre a interseção de funções
feature: Journeys
role: Developer
level: Experienced
exl-id: 19a4b7f8-5636-4b8f-b81f-28ff7da99671
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '81'
ht-degree: 12%
---
# interseção{#intersect}

Retorna os valores comuns nas duas listas de entrada. Se uma das duas listas for nula, retorna uma lista vazia.

## Categoria

Lista

## Sintaxe da função

`intersect(<parameters>)`

## Parâmetros

| Parâmetro | Tipo |
|-----------|------------------|
| lista 1 | list |
| lista 2 | list |

## Assinaturas e tipos retornados

`intersect(listString,listString)`: listString
`intersect(listDecimal,listDecimal)`: listDecimal
`intersect(listInteger,listInteger)`: listInteger
`intersect(listDateTime,listDateTime)`: listDateTime
`intersect(listDateTimeOnly,listDateTimeOnly)`: listDateTimeOnly
`intersect(listDateOnly,listDateOnly)`: listDateOnly
`intersect(listDuration,listDuration)`: listDuration
`intersect(listBoolean,listBoolean)`: listBoolean

Retorna uma lista.

## Exemplos

```json
intersect(
    ["sports", "news", "documentary"],
    ["sports", "movies", "documentary"]
)
```

Retorna [&quot;esportes&quot;, &quot;notícias&quot;]

```json
intersect(
    #{ExperienceDataPlatform.profile.interests},
    ["sports", "news", "documentary"]
)
```

Retorna itens comuns entre atributos de perfil e determinada lista de categorias.

```json
intersect(
    #{ExperienceDataPlatform.profile.interests},
        @{myEvent.sport_interests}
)
```

Retorna itens comuns entre os atributos de perfil e o campo de evento especificado.
