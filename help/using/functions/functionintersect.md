---
product: adobe campaign
title: interseção
description: Saiba mais sobre a interseção de funções
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 19a4b7f8-5636-4b8f-b81f-28ff7da99671
source-git-commit: a9a129b1949d64c4a412d3ea4002b32e3563ea96
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 12%

---

# interseção{#intersect}

Retorna os valores comuns nas duas listas de entrada. Se uma das duas listas for nula, retornará uma lista vazia.

## Categoria

Lista

## Sintaxe da função

`intersect(<parameters>)`

## Parâmetros

| Parâmetro | Tipo |
|-----------|------------------|
| lista 1 | listar |
| lista 2 | listar |

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

Devoluções [&quot;esportes&quot;, &quot;notícias&quot;]

```json
intersect(
    #{ExperienceDataPlatform.profile.interests},
    ["sports", "news", "documentary"]
)
```

Retorna itens comuns entre atributos de perfil e uma determinada lista de categorias.

```json
intersect(
    #{ExperienceDataPlatform.profile.interests},
        @{myEvent.sport_interests}
)
```

Retorna itens comuns entre atributos de perfil e determinado campo de evento.
