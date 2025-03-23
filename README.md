# Guia de compreensão do código

Durante o projeto, foi utilizado alguns métodos e trechos de códigos, sendo a maioria padrão do **React**, e para não esquecer da função de cada, vão estar escritos logo abaixo os mais importantes.

## Trechos de códigos

### export default function nomeDaFunção()
O `export` faz com que a função possa ser acessada fora do arquivo em que foi criada, já o `default` avisa os outros arquivos que estão acessando essa função que ela é a função principal (main) do arquivo.

### (Array(9).fill(null));
Cria uma array com 9 espaços para guardar elementos, onde logo em seguida são preenchidos com `null`, utilizando o comando `.fill(null)`.

**OBS: O contexto do código é que ele foi utilizado em um useState, então é por isso que possui parenteses no início e no fim.**

### () => handleClick(0)
As *Arrow functions* do JS são uma maneira alternativa de criar funções de maneira mais rápida e curta. 


## Métodos React / Outros métodos

### Elemento JSX
Um elemento JSX é uma combinação de código JavaScript e HTML.
Exemplo:
```
<button className="square">X</button>;
```
### Fragmentos React || *<> / </>*
Componentes em react precisam retornar apenas um elemento JSX, então ao tentar retonar múltiplos, vai ocorrer um erro. Para arrumar isso, é necessário utilizar os *React Fragments* para "embrulhar" vários elementos JSX, como no exemplo a seguir:
```
return (
    <>
        <button className="square">X</button>
        <button className="square">X</button>
    </>
);
```
### Dados através de propriedades || *Props*
Quando um componente é utilizado diversas vezes porém necessita atualizar alguma propriedade sua, é possível passar propriedades ao chamar o componente.
```
function Square({ value }) {
    return <button className="square">{value}</button>;
}

// ...
 <div className="board-row">
    <Square value="1" />
    <Square value="2" />
    <Square value="3" />
  </div>
```
### Lembrar das alterações || *useState*
O React possui uma função especial chamada *useState* que você chama nos componentes para que eles "se lembrem" de coisas. É necessário importa-lo no topo do arquivo para que seja utilizado.
```
import { useState } from 'react';
```
E para utilizar o useState, é feito o código a seguir:
```
const [value, setValue] = useState(null);
```
o `value` armazena o valor, enquanto o `setValue` é uma função utilizada para alterar o valor. Dentro dos parenteses do useState, é passado o valor inicial da variável `value`, que nesse caso é `null`.