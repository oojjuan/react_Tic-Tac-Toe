# Guia de compreensão do código

Durante o projeto, foi utilizado alguns métodos e trechos de códigos, sendo a maioria padrão do **React**, e para não esquecer da função de cada, vão estar escritos logo abaixo os mais importantes.

## Trechos de códigos

### export default function nomeDaFunção()
O `export` faz com que a função possa ser acessada fora do arquivo em que foi criada, já o `default` avisa os outros arquivos que estão acessando essa função que ela é a função principal (main) do arquivo.

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