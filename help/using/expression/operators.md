---
product: adobe campaign
title: Operadores
description: Saiba mais sobre operadores em expressões avançadas
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: fd86b6ab-76cf-4b35-9e87-f441e914f20b
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 6%

---

# Operadores {#concept_wd5_pj5_dgb}

Há dois tipos de operadores: operadores unários e operadores binários. Há operadores unários à esquerda e operadores unários à direita.

```json
    // left-hand unary operators
    <operator> <operand> // operand is an expression
    not (@{LobbyBeacon.endUserIDs._experience.emailid.id}=="example@adobe.com")

    // right-hand unary operators
    <operand> <operator> // operand is an expression
    @{LobbyBeacon.endUserIDs._experience.emailid.id} is not null

    // binary operators
    <operand1> <operator> <operand2>
    (@{LobbyBeacon.endUserIDs._experience.emailid.id}=="example1@adobe.com") or
    (@{LobbyBeacon.endUserIDs._experience.emailid.id}=="example2@adobe.com")
```

Esta é a lista de operadores compatíveis:

## Lógica  {#logical}

### e

```json
<expression1> and <expression2>
```

Ambos &lt;expression1> e &lt;expression2> deve ser booleano. O resultado é booleano.

Exemplo:

```json
3.14 > 2 and 3.15 < 1
```

### ou



```json
<expression1> or <expression2>
```

Ambos &lt;expression1> e &lt;expression2> deve ser booleano. O resultado é booleano.

Exemplo:

```json
3.14 > 2 or 3.15 < 1
```

### not



```json
not <expression>
```

&lt;expression> deve ser booleano. O resultado é booleano.

Exemplo:

```json
not 3.15 < 1
```

## Comparação {#comparison}

### é nulo



```json
<expression> is null
```

O resultado é booleano.

Observe que null significa que a expressão não tem um valor avaliado.

Exemplo:

```json
@{BarBeacon.location} is null
```

### não é nulo



```json
<expression> is not null
```

O resultado é booleano.

Observe que null significa que a expressão não tem um valor avaliado.

Exemplo:

```json
@ is not null
```

### tem um valor nulo



```json
<expression> has null
```

&lt;expression> deve ser uma lista. O resultado é booleano.

Útil para identificar se uma lista contém pelo menos um valor nulo.

Exemplo:

```json
["foo", "bar", null] has null --  returns true.
```

```json
["foo", "bar", ""] has null -- returns false because "" is not considered as null.
```

### ==



```json
<expression1> == <expression2>
```

Ambos &lt;expression1> e &lt;expression2> deve ter o mesmo tipo de dados. O resultado é booleano.

Exemplo:

```json
3.14 == 42
```

```json
"foo" == "bar"
```

### !=



```json
<expression1> != <expression2>
```

Ambos &lt;expression1> e &lt;expression2> deve ter o mesmo tipo de dados. O resultado é booleano.

Exemplo:

```json
3.14 != 42
```

```json
"foo" != "bar"
```

### >



```json
<expression1> > <expression2>
```

A Datetime pode ser comparada com a Datetime.

O Datetimeonly pode ser comparado com Datetimeonly.

Tanto o número inteiro como o número decimal podem ser comparados com o número inteiro ou o número decimal.

Qualquer outra combinação é proibida.

O resultado é booleano.

Exemplo:

```json
3.14 > 42
```

### >=



```json
<expression1> >= <expression2>
```

A Datetime pode ser comparada com a Datetime.

O Datetimeonly pode ser comparado com Datetimeonly.

Tanto o número inteiro como o número decimal podem ser comparados com o número inteiro ou o número decimal.

Qualquer outra combinação é proibida.

O resultado é booleano.

Exemplo:

```json
42 >= 3.14
```

### &lt;



```json
<expression1> < <expression2>
```

A Datetime pode ser comparada com a Datetime.

O Datetimeonly pode ser comparado com Datetimeonly.

Tanto o número inteiro como o número decimal podem ser comparados com o número inteiro ou o número decimal.

Qualquer outra combinação é proibida.

O resultado é booleano.

Exemplo:

```json
42 < 3.14
```

### &lt;=



```json
<expression1> <= <expression2>
```

A Datetime pode ser comparada com a Datetime.

O Datetimeonly pode ser comparado com Datetimeonly.

Tanto o número inteiro como o número decimal podem ser comparados com o número inteiro ou o número decimal.

Qualquer outra combinação é proibida.

O resultado é booleano.

Exemplo:

```json
42 <= 3.14
```

## Aritmética {#arithmetic}

### +



```json
<expression1> + <expression2>
```

Ambas as expressões devem ser numéricas (número inteiro ou decimal).

O resultado também é numérico.

Exemplo:

```json
1 + 2 -- returns 3
```

### -



```json
<expression1> - <expression2>
```

Ambas as expressões devem ser numéricas (número inteiro ou decimal).

O resultado também é numérico.

Exemplo:

```json
2 - 1 -- returns 1
```

### /



```json
<expression1> / <expression2>
```

Ambas as expressões devem ser numéricas (número inteiro ou decimal).

O resultado também é numérico.

&lt;expression2> não deve ser igual a 0 (retorna 0).

Exemplo:

```json
4 / 2 -- returns 2
```

### *



```json
<expression1> * <expression2>
```

Ambas as expressões devem ser numéricas (número inteiro ou decimal).

O resultado também é numérico.

Exemplo:

```json
3 * 4 -- returns 12
```

### %



```json
<expression1> % <expression2>
```

Ambas as expressões devem ser numéricas (número inteiro ou decimal).

O resultado também é numérico.

Exemplo:

```json
3 % 2 -- returns 1.
```

## Matemática {#math}

### é numérico



```json
<expression> is numeric
```

O tipo da expressão é inteiro ou decimal.

Exemplo:

```json
@ is numeric
```

### é inteiro



```json
<expression> is integer
```

O tipo da expressão é integer.

Exemplo:

```json
@ is integer
```

### é decimal



```json
<expression> is decimal
```

O tipo da expressão é decimal.

Exemplo:

```json
@ is decimal
```

## String {#string}

### +



```json
<string> + <expression>
```

```json
<expression> + <string>
```

Concatena duas expressões.

Uma expressão deve ser uma string encadeada.

Exemplo:

```json
"the current time is " + (now()) -- returns "the current time is 2019-09-23T09:30:06.693Z"
```

```json
(now()) + " is the current time" -- returns "2019-09-23T09:30:06.693Z is the current time"
```

```json
"a" + "b" + "c" + 1234 -- returns "abc1234".
```

## Data  {#date}

### +



```json
<expression> + <duration>
```

Anexe uma duração a dateTime, a dateTimeOnly ou a duração.

Exemplo:

```json
toDateTime("2011-12-03T15:15:30Z") + toDuration("PT15M") -- returns 2011-12-03T15:30:30Z
```

```json
toDateTimeOnly("2011-12-03T15:15:30") + toDuration("PT15M") -- returns 2011-12-03T15:30:30
```

```json
now() + toDuration("PT1H") -- returns a dateTime (with UTC time zone) one hour later from current time
```

```json
toDuration("PT1H") + toDuration("PT1H") -- returns  PT2H
```
