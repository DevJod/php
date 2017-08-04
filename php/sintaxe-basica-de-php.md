---
title:       Sintaxe básica de PHP
description: 
capitulo:    "php-capitulo-1"
ordem:       4
---

## Variáveis

As variáveis no PHP são representadas por um cifrão ($) seguido pelo nome da variável, os nomes de variável são 
case-sensitive. 

```php
<?php
$nome  = "Joana Gabrielle";
$idade = 6;

$num1 = 50;
$num2 = 50;
echo $num1 + $num2;
```


## Escopo de variáveis

https://secure.php.net/manual/pt_BR/language.variables.scope.php



## Operadores

http://php.net/manual/pt_BR/language.operators.php



## Como comentar o código

Duas barras comentam o código linha a linha.

```php
<?php
// comentários
```

O sinal de sharp também comenta linha a linha.

```php
<?php
# comentários
```

Outra forma de comentar linha a linha.

```php
<?php
/* comentários */
```

Mas também podem ser usado para várias linhas.

```php
<?php
/*

comentários
comentários
comentários

*/
```

Este é um exemplo de comentários do tipo dock block, alguns editores ajudam a criar esse bloco, você digita `/**`, 
preciona a tecla enter e o editor completa a estrutra desse comentário.

```php
<?php
/**
 * Comentário do tipo DocBlock
 *
 * comentários
 * comentários
 * comentários
 */
```

Abaixo vemos um alternativa simplificada.

```php
<?php
#
# alternativa 
#
```

## Estruturas de controle

## Laços de repetição

## Requisição de arquivos


## Tipos

O PHP suporta oito tipos primitivos.

- escalares:
    + boolean
    + integer
    + float
    + string
- compostos:
    + array
    + object
    + callable
- especiais:
    + resource
    + NULL


## Arrays

Array é uma estrutura que relaciona valores e chaves, é uma lista de valores armazenados na memória.

```php
<?php
# antigamente
$arr = array("primeiro", "segundo", "terceiro");

# Atualmente
$arr = ["primeiro", "segundo", "terceiro"];
```

Veja come acessar o valor de um array.

```php
<?php
echo $arr[0]; // exibe 'primeiro'
```

O array pode ser numérico...

```php
<?php
$arr = [
    0 => "vermelha",
    1 => "doce",
    2 => "redonda",
    3 => "maçã"
];
```

...ou associativo:

```php
<?php
$arr = [
    "cor"     => "vermelha",
    "sabor"   => "doce",
    "formato" => "redonda",
    "nome"    => "maçã"
];
```

Comumente, percorremos o array com a ajuda do `foreach`, veja:

```php
<?php
foreach($arr as $valor) {
    var_dump($valor);
}
// exibirá: "vermelha", "doce", "redonda", "maçã"
```




## Objetos

```php
<?php
require "Triangulo.php";

$triangulo = new Triangulo();               # instanciamos
$triangulo->a = 3;                          # atribuímos valor
$triangulo->b = 4;                          # idem
$triangulo->c = 5;                          # idem
var_dump(  $triangulo->validarForma()  );   # executamos um método
```


```php
<?php
class Triangulo {

    # suas propriedades
    public $a;
    public $b;
    public $c;

    # seus métodos
    public function validarForma() {
        echo $this->a;
        echo $this->b;
        echo $this->c;
    }
}
```



Leia mais sobre [arrays](/php/criando-e-iterando-um-array-em-php/).