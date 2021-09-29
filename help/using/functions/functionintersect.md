---
product: adobe campaign
title: interseção
description: Saiba mais sobre a interseção de funções
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 19a4b7f8-5636-4b8f-b81f-28ff7da99671
source-git-commit: f2f5cc29f5079419662439f1cb1dee8fcb1b1ab9
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 10%

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

```
intersect(
    ["sports", "news", "documentary"],
    ["sports", "movies", "documentary"]
)
```

Retorna [&quot;esportes&quot;, &quot;notícias&quot;]

```
intersect(
    #{ExperienceDataPlatform.profile.interests},
    ["sports", "news", "documentary"]
)
```

Retorna itens comuns entre atributos de perfil e uma determinada lista de categorias.

```
intersect(
        	#{ExperienceDataPlatform.profile.interests},
            @{myEvent.sport_interests}
)
```

Retorna itens comuns entre atributos de perfil e determinado campo de evento.