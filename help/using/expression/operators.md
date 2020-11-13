---
title: Operadores
description: Saiba mais sobre operadores em expressões avançadas
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: eec6203f63fa6d7ea706595ea866d2b330d284a8
workflow-type: tm+mt
source-wordcount: '618'
ht-degree: 5%

---



# Operadores {#concept_wd5_pj5_dgb}

Há dois tipos de operadores: operadores unários e binários. Há operadores unários à esquerda e operadores unários à direita.

```
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

Esta é a lista dos operadores suportados:

## Lógica

<table>
<thead>
<tr><th>Operador</th><th>Expressão literal</th><th>Exemplo</th></tr>
</thead>
<tbody>
<tr><td>e</td><td><p><pre>&lt;expressão1&gt; e &lt;expressão2&gt;</pre></p>Ambos &lt;expressão1&gt; e &lt;expressão2&gt; devem ser booleanos. O resultado é booleano.</td><td><pre>3.14 &gt; 2 e 3.15 &lt; 1</pre></td></tr>
<tr><td>ou</td><td><p><pre>&lt;expressão1&gt; ou &lt;expressão2&gt;</pre></p><p>Ambos &lt;expressão1&gt; e &lt;expressão2&gt; devem ser booleanos.</p><p> O resultado é booleano.</p></td><td><p><pre>3.14 &gt; 2 ou 3.15 &lt; 1</pre></p></td></tr>
<tr><td>not</td><td><p><pre>not &lt;expressão&gt;</pre></p><p>&lt;expressão&gt; deve ser booleano.</p><p> O resultado é booleano.</p></td><td><pre>não 3,15 &lt; 1</pre></td></tr>
</tbody>
</table>

## Comparação

<table>
<thead>
<tr><th>Operador</th><th>Expressão literal </th><th>Exemplo</th></tr>
</thead>
<tbody><tr><td>é nulo</td><td><p><pre>&lt;expressão&gt; é nulo</pre></p><p>O resultado é booleano.</p><p>Observe que nulo significa que a expressão não tem valor avaliado.</p></td><td><pre>@{BarBeacon.location} é nulo</pre></td></tr>
<tr><td>não é nulo</td><td><p><pre>&lt;expressão&gt; não é nulo</pre></p><p>O resultado é booleano.</p><p>Observe que nulo significa que a expressão não tem valor avaliado.</p></td><td><pre>@ não é nulo</pre></td></tr>
<tr><td>tem nulo</td><td><p><pre>&lt;expressão&gt; tem um valor nulo</pre>&lt;expressão&gt; deve ser uma lista.</p><p>O resultado é booleano.</p><p>Útil para identificar se uma lista contém pelo menos um valor nulo.</p></td><td><p><pre>["foo", "bar", null] tem nulo</pre></p>retorna true<p><pre>["foo", "bar", ""] tem nulo</pre></p> retorna false porque "" não é considerado nulo.</td></tr>
<tr><td>==</td><td><p><pre>&lt;expressão1&gt; == &lt;expressão2&gt;</pre></p><p>As opções &lt;expressão1&gt; e &lt;expressão2&gt; devem ter o mesmo tipo de dados.</p><p> O resultado é booleano.</p></td><td><pre>3.14 == 42</pre><br /><pre>"foo" == "bar"</pre></td></tr>
<tr><td>!=</td><td><p><pre>&lt;expressão1&gt; != &lt;expressão2&gt;</pre></p><p> As opções &lt;expressão1&gt; e &lt;expressão2&gt; devem ter o mesmo tipo de dados.</p><p> O resultado é booleano.</p></td><td><pre>3.14 != 42</pre><br /><pre>"foo"!= "bar"</pre></td></tr>
<tr><td>&gt;</td><td><p><pre>&lt;expressão1&gt; &gt; &lt;expressão2&gt;</pre></p><p>A data e hora pode ser comparada com a data e hora.</p><p>Só é possível comparar Datetimeonly com Datetimeonly.</p><p>Tanto o número inteiro quanto o número decimal podem ser comparados com o número inteiro ou o número decimal.</p><p>Qualquer outra combinação é proibida.</p><p>O resultado é booleano.</p></td><td><pre>3.14 &gt; 42</pre></td></tr>
<tr><td>&gt;=</td><td><p><pre>&lt;expressão1&gt; &gt;= &lt;expressão2&gt;</pre></p><p>A data e hora pode ser comparada com a data e hora.</p><p>Só é possível comparar Datetimeonly com Datetimeonly.</p><p>Tanto o número inteiro quanto o número decimal podem ser comparados com o número inteiro ou o número decimal.</p><p>Qualquer outra combinação é proibida.</p><p>O resultado é booleano.</p></td><td><pre>42 &gt;= 3.14</pre></td></tr>
<tr><td>&lt;</td><td><p><pre>&lt;expressão1&gt; &lt; &lt;expressão2&gt;</pre></p><p>A data e hora pode ser comparada com a data e hora.</p><p>Só é possível comparar Datetimeonly com Datetimeonly.</p><p>Tanto o número inteiro quanto o número decimal podem ser comparados com o número inteiro ou o número decimal.</p><p>Qualquer outra combinação é proibida.</p><p>O resultado é booleano.</p></td><td><pre>42 &lt; 3.14</pre></td></tr>
<tr><td>&lt;=</td><td><p><pre>&lt;expressão1&gt; &lt;= &lt;expressão2&gt;</pre></p><p>A data e hora pode ser comparada com a data e hora.</p><p>Só é possível comparar Datetimeonly com Datetimeonly.</p><p>Tanto o número inteiro quanto o número decimal podem ser comparados com o número inteiro ou o número decimal.</p><p>Qualquer outra combinação é proibida.</p><p>O resultado é booleano.</p></td><td><pre>42 &lt;= 3.14</pre></td></tr>
</tbody>
</table>

## Aritmética

<table>
<thead>
<tr><th>Operador</th><th>Expressão literal </th><th>Exemplo</th></tr>
</thead>
<tbody><tr><td>+</td><td><p><pre>&lt;expressão1&gt; + &lt;expressão2&gt;</pre></p><p>Ambas as expressões devem ser numéricas (números inteiros ou decimais). </p><p>O resultado também é numérico.</p></td><td><p><p><pre>1 + 2</pre></p></p><br /><p>Retorna 3</p></td></tr>
<tr><td>-</td><td><p><pre>&lt;expressão1&gt; - &lt;expressão2&gt;</pre></p><p> Ambas as expressões devem ser numéricas (números inteiros ou decimais).</p><p> O resultado também é numérico.</p></td><td><p><pre>2 - 1</pre></p>Retorna 1</td></tr>
<tr><td>/</td><td><p><pre>&lt;expressão1&gt; / &lt;expressão2&gt;</pre></p><p>Ambas as expressões devem ser numéricas (números inteiros ou decimais). </p><p>O resultado também é numérico.</p><p>&lt;expressão2&gt; não deve ser igual a 0 (retorna 0).</p></td><td><p><pre>4 / 2</pre></p>Retorna 2</td></tr>
<tr><td>*</td><td><p><pre>&lt;expressão1&gt; * &lt;expressão2&gt;</pre></p><p> Ambas as expressões devem ser numéricas (números inteiros ou decimais). </p><p>O resultado também é numérico.</p></td><td><p><pre>3 * 4</pre></p>Retorna 12</td></tr>
<tr><td>%</td><td><p><pre>&lt;expressão1&gt; % &lt;expressão2&gt;</pre></p><p>Ambas as expressões devem ser numéricas (números inteiros ou decimais).</p><p> O resultado também é numérico.</p></td><td><p><pre>3 % 2</pre></p>Retorna 1.</td></tr>
</tbody>
</table>

## Matemática

<table>
<thead>
<tr><th>Operador</th><th>Expressão literal</th><th>Exemplo</th></tr>
</thead>
<tbody><tr><td>é numérico</td><td><p><pre>&lt;expressão&gt; é numérico</pre></p><p>O tipo da expressão é inteiro ou decimal.</p></td><td><pre>@ é numérico</pre></td></tr>
<tr><td>é integer</td><td><p><pre>&lt;expressão&gt; é um número inteiro</pre></p><p>O tipo da expressão é inteiro.</p></td><td><pre>@ é inteiro</pre></td></tr>
<tr><td>é decimal</td><td><p><pre>&lt;expressão&gt; é decimal</pre></p><p>O tipo da expressão é decimal.</p></td><td><pre>@ é decimal</pre></td></tr>
</tbody>
</table>

## String

<table>
<thead>
<tr><th>Operador</th><th>Expressão literal </th><th>Exemplo</th></tr>
</thead>
<tbody><tr><td>+</td><td><p><pre>&lt;string&gt; + &lt;expressão&gt;</pre></p><p><pre>&lt;expressão&gt; + &lt;cadeia&gt;</pre></p><p>Concatena duas expressões. </p><p>Uma expressão deve ser uma cadeia encadeada.</p></td><td><p><pre>"a hora atual é " + (now())</pre></p> Retorna "a hora atual é 2019-09-23T09:30:06.693Z"<p><pre>(now()) + " é a hora atual"</pre></p>Retorna "2019-09-23T09:30:06.693Z é a hora atual"<p><pre>"a" + "b" + "c" + 1234</pre></p> Retorna "abc1234".</td></tr>
</tbody>
</table>

## Data

<table>
<thead>
<tr><th>Operador</th><th>Expressão literal </th><th>Exemplo</th></tr>
</thead>
<tbody>
<tr><td>+</td><td><p><pre>&lt;expressão + &lt;duração&gt;</pre></p><p>Anexe uma duração a dateTime, a dateTimeOnly ou a duração.</p></td><td><p><pre>toDateTime("2011-12-03T15:15:30Z")</pre></p><p><pre> + toDuration("PT15M")</pre></p><p>Retorna 2011-12-03T15:30:30Z</p><p><pre>toDateTimeOnly("2011-12-03T15:15:30")</pre></p><p><pre> + toDuration("PT15M")</pre></p>Retorna 2011-12-03T15:30:30<p><pre>now() + toDuration("PT1H")</pre></p><p>Retorna um dateTime (com fuso horário UTC) uma hora depois do horário atual</p><p><pre>toDuration("PT1H") + toDuration("PT1H")</pre></p><p>Retorna PT2H</p></td></tr>
</tbody>
</table>