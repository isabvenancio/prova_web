## Aula 03 - HTML Parte 1

### O que é
HTML = arquivo de texto com tags de marcação
 - as tags dizem pro navegador como exibir a página
 - dá pra criar num editor de texto simples (notepad)
 - HTML5 é a versão mais atual
 - as especificações são publicadas pelo W3C

### Estrutura básica
Elementos organizados hierarquicamente por tags
 - tags ficam entre parênteses angulares (< e >)
 - elementos podem ter atributos e conteúdo
 - atributo = nome + valor

```html
<!DOCTYPE html>
<html>
<body>
    <h1>Este é um cabeçalho</h1>
    <p>Isto é um parágrafo</p>
</body>
</html>
```

### `<head>`
Informações gerais sobre o documento (metadados)
```html
<head>
    <meta name="keywords" content="HTML, CSS">
    <meta name="description" content="Aula de HTML">
    <meta charset="UTF-8">
    <meta name="author" content="Felippe">
    <meta http-equiv="refresh" content="30">   <!-- recarrega a página a cada 30s -->
    <link rel="stylesheet" href="Estilo.css">  <!-- liga o arquivo CSS -->
    <title>Título da Página</title>
</head>
```

### `<body>`
O conteúdo da página vai dentro do `<body>`

### `<h1>` ... `<h6>`
Cabeçalhos (títulos) da página, do `<h1>` (maior) ao `<h6>`
 - o navegador coloca automaticamente um espaço (margem) antes e depois de cada título
 - usar só pra cabeçalhos, NÃO pra deixar o texto grande ou em negrito
 - os motores de busca usam os h1...h6 pra indexar a estrutura e o conteúdo da página
 - `<h1>` é o principal, seguido dos outros

### `<p>`
Define parágrafos
 - o navegador coloca uma linha em branco antes e depois
 - espaços e quebras de linha a mais dentro do código são ignorados pelo navegador

### `<br>`
Quebra de linha
```html
<p>
Este é <br>
um pará-<br>
grafo com <br>
quebra de linhas
</p>
```

### `<hr>`
Régua horizontal: deixa uma linha marcando a página (dá pra colocar várias)
```html
<h1>Este é o cabeçalho 1</h1>
<p>Algum texto aqui</p>
<hr>
```

### Símbolos
Pra inserir certos caracteres usa o código do caractere (pelo nome, hexadecimal ou decimal)
 - lista: https://www.w3schools.com/charsets/ref_utf_math.asp

```html
<p>
  &starf; &bigstar; &#x02605; &#9733; <br>   <!-- estrela -->
  &phone; &#x0260E; &#9742; <br>             <!-- telefone -->
  &female; &#x02640; &#9792; <br>            <!-- feminino -->
  &sung; &#x0266A; &#9834; <br>              <!-- nota musical -->
</p>
```

### Comentários
```html
<!-- Este é um comentário -->
<p>Este é um parágrafo.</p>
```


## Aula 04 - HTML Parte 2

### Formatação de texto
```html
<b>Negrito</b>
<strong>Importante</strong>
<i>Itálico</i>
<em>Enfatizado</em>
<mark>Destacado</mark>
<small>Texto pequeno</small>
<del>Texto excluído</del>
<ins>Texto inserido</ins>
<sub>Subscrito</sub>
<sup>Sobrescrito</sup>
```

Na prática
```html
<p><b>Este texto é negrito</b></p>
<p><i>Este texto é itálico</i></p>
<p>Este é <sub>subscrito</sub> e <sup>sobrescrito</sup></p>
```

### Hiperlinks `<a>`
Texto ou imagem q você clica e vai pra outro documento
 - atributo href → endereço de destino

```html
<a href="url">Link de Texto</a>
<a href="http://www.uem.br">UEM</a>
```

 - link local (mesmo site) → URL relativa (sem http://www...)
 - link de e-mail → mailto:

```html
<a href="pagina2.html">Página 2</a>
<a href="mailto:ffsilva2@uem.br">Contato</a>
```

### Âncora
Link pra uma seção específica da página
 - coloca um atributo id no elemento de destino e usa #id no href

```html
<a href="#secao1">Visite a dica da seção 1</a>
...
<h3 id="secao1">Seção 1</h3>
```

### Atributo target
Onde abrir o documento do link
 - `_blank` → abre em nova janela ou aba

```html
<a href="http://www.uem.br/" target="_blank">Link UEM</a>
```

### Imagens `<img>`
 - src → caminho da imagem
 - alt → texto alternativo
 - width e height → largura e altura

```html
<img src="montanha.jpg" alt="Montanha" width="128" height="128">

<!-- imagem em outra pasta -->
<img src="./imagens/montanha.jpg" alt="Montanha">

<!-- imagem de outro site -->
<img src="https://pokemmo.com/build/images/trailer-thumbnail.0fcf88ca.jpg" alt="PokeMMO" width="128" height="128">

<!-- imagem como link -->
<a href="https://pokemmo.com/pt-BR/">
    <img src="montanha.jpg" alt="Montanha" width="128" height="128">
</a>
```


## Aula 05 - HTML Parte 3

### Listas
Não ordenada `<ul>` (com marcadores), cada item é um `<li>`
```html
<ul>
  <li>Chocolate</li>
  <li>Café</li>
  <li>Leite</li>
</ul>
```

Ordenada `<ol>` (numerada), cada item é um `<li>`
 - atributo type define o tipo de marcador (ex: "A" → A, B, C)

```html
<ol type="A">
  <li>Chocolate</li>
  <li>Café</li>
  <li>Leite</li>
</ol>
```

### `<iframe>`
Mostra uma página web dentro de outra
 - height e width definem o tamanho

```html
<iframe src="https://www.uem.br/" width="200" height="200"></iframe>
```

### Tabelas `<table>`
 - `<tr>` → linha
 - `<td>` → célula de dados
 - `<th>` → célula de título (cabeçalho)

```html
<table>
  <tr>
    <th>Nome</th>
    <th>Sobrenome</th>
    <th>Idade</th>
  </tr>
  <tr>
    <td>Felippe</td>
    <td>Fernandes</td>
    <td>25</td>
  </tr>
</table>
```

colspan e rowspan (atributos de th e td)
 - colspan → quantas COLUNAS a célula ocupa
 - rowspan → quantas LINHAS a célula ocupa

```html
<!-- colspan: "Telefone" ocupa 2 colunas -->
<table border="1">
  <tr>
    <th>Nome</th>
    <th colspan="2">Telefone</th>
  </tr>
  <tr>
    <td>Bill Gates</td>
    <td>44 0800 1234</td>
    <td>4002 8922</td>
  </tr>
</table>

<!-- rowspan: "Telefone:" ocupa 2 linhas -->
<table border="1">
  <tr>
    <th>Nome:</th>
    <td>Bill Gates</td>
  </tr>
  <tr>
    <th rowspan="2">Telefone:</th>
    <td>44 0800 1234</td>
  </tr>
  <tr>
    <td>4002 8922</td>
  </tr>
</table>
```

Cabeçalho, corpo e rodapé: `<thead>`, `<tbody>` e `<tfoot>` → melhoram a semântica da tabela
```html
<table border="1">
  <thead>
    <tr>
      <th>Marca</th>
      <th>Ano</th>
    </tr>
  </thead>
  <tfoot>
    <tr>
      <td colspan="2">Atualização: 07/2023</td>
    </tr>
  </tfoot>
  <tbody>
    <tr>
      <td>Golzinho Bola</td>
      <td>2023</td>
    </tr>
  </tbody>
</table>
```

`<caption>` → título da tabela
```html
<table border="1">
  <caption>Compras</caption>
  <tr>
    <th>Mês</th>
    <th>Cartão</th>
  </tr>
  <tr>
    <td>Janeiro</td>
    <td>R$100</td>
  </tr>
</table>
```

### `<div>`
Elemento de bloco usado como recipiente (container) pra outros elementos
 - atributo style → estilo CSS
 - atributo id → identificação única do elemento

```html
<div id="idconteudo" style="background-color:black; color:white; padding:10px;">
  <h2>Inglaterra</h2>
  <p>Sed ut perspiciatis unde omnis iste natus</p>
</div>
```


## Aula 06 - HTML Parte 4

### Formulário `<form>`
Coleta dados do usuário. Contém campos de entrada, caixas de seleção, botões de rádio, botões de envio etc
```html
<form>
  ... elementos do formulário ...
</form>
```

### Tipos de `<input>`
text → campo de texto
```html
Nome:<br>
<input type="text" name="nome"><br>
Sobrenome:<br>
<input type="text" name="sobrenome">
```

password → campo de senha (esconde o q é digitado)
```html
Usuário:<br>
<input type="text" name="usu"><br>
Senha:<br>
<input type="password" name="sen">
```

radio → botão de rádio (escolhe UMA opção; os do mesmo grupo têm o mesmo name)
 - checked → já vem marcado

```html
<input type="radio" name="sex" value="masculino" checked> Masculino <br>
<input type="radio" name="sex" value="feminino"> Feminino
```

checkbox → escolhe ZERO OU MAIS opções
```html
<input type="checkbox" name="veiculo" value="Bike"> Eu tenho uma bike <br>
<input type="checkbox" name="veiculo" value="Carro"> Eu tenho um carro
```

submit → botão pra enviar o formulário
```html
Nome:<input type="text" name="nome"><br>
Sobrenome:<input type="text" name="sobrenome">
<input type="submit" value="Enviar">
```

number → só valor numérico
 - min e max → limites
 - step → intervalo entre os valores válidos (com min=1 e step=2: 1, 3, 5) (o slide diz q é "a largura em caracteres do campo", mas isso é o atributo size)

```html
Quantidade (entre 1 e 5):
<input type="number" name="quantidade" min="1" max="5" step="2">
```

date → campo de data (no Chrome aparece um calendário)
```html
Data: <input type="date" name="data">
```

color → seletor de cores
```html
Selecione uma cor: <input type="color" name="favcolor">
```

range → valor dentro de uma faixa (barrinha deslizante)
```html
1 <input type="range" name="points" min="0" max="10"> 10
```

### `<select>`
Lista drop-down
 - `<option>` → cada opção
 - selected → opção pré-selecionada

```html
<select name="animes">
  <option value="naruto" selected>Naruto</option>
  <option value="onepiece">One Piece</option>
  <option value="pokemon">Pokemon</option>
  <option value="onepunch">One Punch Man</option>
</select>
```

### `<textarea>`
Campo de texto com várias linhas (rows = linhas, cols = colunas)
```html
<textarea name="message" rows="10" cols="30"></textarea>
```

### `<button>`
Define um botão
 - diferença pro `<input>`: dentro do `<button>` dá pra colocar conteúdo (texto ou imagens)

```html
<button type="button" onclick="alert('Olá!')">Clique!</button>
```

### `<fieldset>`
Agrupa elementos relacionados do formulário
 - `<legend>` → legenda do grupo
 - disabled → desativa o campo

```html
<form>
  <fieldset>
    <legend>Pessoal:</legend>
    Nome: <input type="text"><br>
    Email: <input type="text"><br>
    Empresa: <input type="text" disabled><br>
  </fieldset>
</form>
```

### `<datalist>`
"Autocomplete" pra um `<input>` (o list do input aponta pro id do datalist)
```html
<input list="browsers">
<datalist id="browsers">
  <option value="Internet Explorer">
  <option value="Firefox">
  <option value="Chrome">
  <option value="Opera">
  <option value="Safari">
</datalist>
```

### Atributo action
Define o q acontece quando o formulário é enviado (normalmente manda pra uma página/servidor web)
```html
<form action="acao.php">
  Nome:<br>
  <input type="text" name="nome">
  Sobrenome:<br>
  <input type="text" name="sobrenome">
  <input type="submit" value="Enviar">
</form>
```

### Atributo method
Método HTTP usado pra enviar o formulário: GET ou POST
```html
<form action="acao.php" method="GET">
<form action="acao.php" method="POST">
```
 - GET → os dados ficam visíveis no endereço (URL) da página
 - POST → os dados não aparecem no endereço, por isso é mais seguro (mas só não ficam na URL; pra criptografar precisa de HTTPS)
 - pra ser enviado, cada campo precisa ter o atributo name (campo sem name não vai junto)