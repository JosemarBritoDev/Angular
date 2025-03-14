Aqui será exibido todos os comentarios de codigos utilizados 

***Exibindo dados com Expressões***
Expressões são pedaços de códigos que retornam valores. Esses valores serão exibidos na tela.

Assim como vimos anteriormente ao iniciar uma aplicação Angular.
<div>
    {{ 5 + 2 }}
</div>

Expressões são inseridas na Template entre chaves duplas ( {{ }} ). Podemos passar funções, variáveis, cálculos, etc.
<div ng-init="a = 5" >
    {{ a }}
</div>

A diretiva “ng-init” nos permite declarar uma variável. Declaramos uma variável “a” com o valor 5. Como passamos “a” na expressão, o valor da variável será exibido na tela.

Importante
Usamos o “ng-init” aqui apenas para nossos exemplos. Para um código mais limpo, prefira evitar declarar variáveis e colocar lógica na Template.


***ng-if: inserindo e removendo elementos***
A diretiva “ng-if” recebe um valor “true” ou “false”. Se o valor for verdadeiro, o elemento com a diretiva será renderizado normalmente.

Se o valor for falso, o elemento será removido do DOM.
<div ng-init="isVisible = true" >
    <span ng-if="isVisible" >TreinaWeb</span>
</div>

Com o código acima, o texto será exibido normalmente. Mude o valor da variável “isVisible” para “false” e teremos o seguinte resultado:
<div ng-init="isVisible = false">
    <!-- ngIF: isVisible -->
</div>
O nosso <span> foi removido, e no lugar foi colocado um comentário. Isso serve para o Angular depois saber onde deve inserir o elemento novamente caso o valor da variável mude para “true” novamente.

***ng-show & ng-hide: exibindo e escondendo elementos***
As diretivas “ng-show” e “ng-hide” servem para exibir ou esconder um elemento. A diferença entre eles é que o “ng-show” exibe um elemento se a variável passada para ele for verdadeira, e o “ng-hide” se ela for falsa. Ou seja, um é o oposto do outro.

<div ng-init="isVisible = true" >
    <span ng-show="isVisible" >TreinaWeb 1</span>
    <span ng-hide="isVisible" >TreinaWeb 2</span>
</div>

Diferença de ng-show e ng-if

Quando uma condição for falsa, o “ng-show” insere uma classe CSS no elemento, fazendo-o ficar escondido (display: none). Por estar apenas escondido, o elemento continua existindo, assim como seus binds, listeners, etc.

Quando uma condição for false, o ng-if remove o elemento, destruindo também seus binds, listeners e eventos. Quando a condição se torna verdadeira o elemento é criado novamente.

Para evitar ter muitos binds e listeners, prejudicando a performance da aplicação, prefira o ng-if. Caso tenha poucos binds em sua aplicação e necessite apresentar e esconder muitos elementos a toda hora, prefira o ng-show, poupando que o Angular necessite criar os elementos a toda hora.