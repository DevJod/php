---
title:       Sintaxe básica de PHP
description:
capitulo:    "começando"
ordem:       5
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



## Examinando o valor de uma variável

Para ver o que uma variável contém podemos utilizar a função `print_r()`.

```php
<?php
print_r($minha_variavel);
```

Mas você irá notar que ainda não está legível como você gostaria, então tente incluir umas tags HTML:

```php
<?php
echo "<pre>";
print_r($minha_variavel);
echo "</pre>";
```

Aí sim você verá o resultado bem formatado. Mas tudo isso de linha só para exibir o valor de uma variável ?
Você pode utilizar uma função, por exemplo:

```php
<?php
function my_print_r($minha_variavel) {
    echo "<pre>";
    print_r($minha_variavel);
    echo "</pre>";
}
```

... ou utilizar o `var_dump()`. Háaaaa, então porque você não me apresentou logo esse cara ? É porque o `print_r()` é uma
função interna, ela acompanha o PHP. O `var_dump()` também é uma função interna, mas para ele funcionar (adequadamente)
você precisará ter a extensão [x-debug]() devidamente instalado.

```php
<?php
var_dump($minha_variavel);
```

- var_dump: exibe tipo e valor, precisa ter o `x-debug instalado
- print_r: exibe valor, fica melhor com a tag `<pre>`

Talvez você queira dar uma olha neste artigo [Debugando código em PHP ](/php/debugando-codigo/)



## Funções

Funções são uma seção nomeada de código, um pequeno (normalmente pequeno) trecho de código que pode ser chamado de diversos ponto do código.

Quando o programador precisar executar um mesmo código (mesmo que ligeiramente diferente) várias vezes ele, então, poderá utilizar-se de funções.

As funções introduzem o conceito de reusabilidade, ou seja, "escrever código para depois".

```php
<?php
function somar_dois_numeros($param1, $param2) {
    return $param1 + $param2;
}

echo somar_dois_numeros(5, 3);
```

Leia mais sobre [funções](/php/funcoes/).



## Operadores Aritiméticos

```php
<?php
$a + $b; 	# Adição         : Soma de $a e $b.
$a - $b; 	# Subtração      : Diferença entre $a e $b.
$a * $b; 	# Multiplicação  : Produto de $a e $b.
$a / $b; 	# Divisão        : Quociente de $a e $b.
$a % $b; 	# Módulo         : Resto de $a dividido por $b.
$a ** $b; 	# Exponencial    : Resultado de $a elevado a $b.
```

Estes operadores funcionam exatamente como o da aritmética básica da escola.

Talvez você queira ver a precedência dos operadores [php.net/Precedência de Operadores](http://php.net/manual/pt_BR/language.operators.precedence.php)



## Operadores de Incremento/Decremento

```php
<?php
++$a; # Pré-incremento - Incrementa $a em um, e então retorna $a.
$a++; # Pós-incremento - Retorna $a, e então incrementa $a em um.
--$a; # Pré-decremento - Decrementa $a em um, e então retorna $a.
$a--; # Pós-decremento - Retorna $a, e então decrementa $a em um.
```



## Operadores Lógicos

```php
<?php
($a && $b);  # verdadeiro se $a e $b forem verdadeiros.
($a || $b);  # verdadeiro se $a ou $b forem verdadeiros.
($a xor $b); # verdadeiro se $a ou $b forem verdadeiros, mas se ambos forem verdadeiro, então é falso.
```



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

Bloco if-else.

```php
<?php
if (expressao-condicional) {
    ... executar codigo
    ... executar codigo
    ... executar codigo
} else {
    ... executar codigo
    ... executar codigo
    ... executar codigo
}
```

Bloco if-elseif-else

```php
<?php
if (expressao-condicional) {
    ... executar codigo
    ... executar codigo
    ... executar codigo
} else if (expressao-condicional) {
    ... executar codigo
    ... executar codigo
    ... executar codigo
} else
    ... executar codigo
    ... executar codigo
    ... executar codigo
}
```

Operador ternário

```php
<?php
$resultado = (expressao-condicional) ? "caso-true" : " caso-false" ;
```



## Laços de repetição

Laço `foreach()`:

```php
<?php
foreach(['primeiro', 'segundo', 'terceiro'] as $value) {
    echo $value;
}
// Exibe... 'primeiro', 'segundo' e 'terceiro'
```

Laço `for()`:

```php
<?php
for($i = 0; $i < 5, $i++){
    echo $i;
}
// exibe 0, 1, 2, 3, e 4
```

Laço `while()`:

```php
<?php
$i = 0;
while ($i > 5) {
    echo $i;
    $i++;
}
// exibe 0, 1, 2, 3, e 4
```


## Requisição de arquivos

Para incluir outros scripts em seu scritp atual você pode utilizar o `include` ou `require`.

O `include` inclui um arquivo sem se preocupar se o arquivo existe ou não.

O `require` inclui um arquivo e lançará um erro se ele não existir, por tanto, ele é requerido, exigido!

O complemento `_once` significa que o script deve ser inserido uma única vez, ou seja, se você chamar um script que 
chama outros scripts, e estes, por sua vez, chamam a si mesmo, então você receberá um erro. Um errro por que o script
foi inserido duas vezes ? Não, mas imagine que temos uma função chamada `foo()`, quando o mesmo script for chamado pela
segunda vez, ele reclamará que não pode redefinir `foo()`.


```php
<?php
include "arquivo.php";       # inclui o arquivo
include_once "arquivo.php";  # inclui o arquivo uma única vez
require "arquivo.php";       # requer um arquivo
require_once "arquivo.php";  # requer um arquivo uma única vez
```
Tanto `include` como `require` são funções, alguns desenvolvedores preferem a forma de função, veja:

```php
<?php
require('arquivo.php');
```

Sim, mas e agora qual eu devo usar ?

Use o `require_once`, ele é o mais restritivo e o mais utilizado também.


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



## Strings

Uma string pode ser especificada com aspas duplas e aspas simples.

Aspas duplas: o conteúdo é interpretado.
 
```php
<?php
$nome = "Joana";
echo "Seu nome é $nome"; // Seu nome é Joana
```

Você pode concatenar strings com o o ponto `.`

```php
<?php
$nome = "Joana" . "Gabrielle";

# ou 
$nome      = "Joana";
$sobrenome = "Gabrielle";
echo $nome . $sobrenome;
```

Aspas simples: o conteúdo NÂO é interpretado.
 
```php
<?php
$nome = "Joana";
echo 'Seu nome é $nome'; // Seu nome é $nome
```

Há outras duas formas: heredoc e nowdoc, talvez você queira ver a documentação sobre 
[strings](http://php.net/manual/pt_BR/language.types.string.php).



## Arrays

Array é uma estrutura que relaciona valores e chaves, é uma lista de valores armazenados na memória.

```php
<?php
# Como se criava array antigamente
$arr = array("primeiro", "segundo", "terceiro");

# Como se cria um array atualmente
$arr = ["primeiro", "segundo", "terceiro"];
```

Veja como acessar o valor de um array.

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

Normalmente, percorremos o array com a ajuda do `foreach`, veja:

```php
<?php
foreach($arr as $valor) {
    var_dump($valor);
}
// exibirá: "vermelha", "doce", "redonda", "maçã"
```

Leia mais sobre [arrays](/php/criando-e-iterando-um-array-em-php/).



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

Leia mais sobre [objetos](/php/programacao-orientada-a-objetos/).



