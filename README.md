# Teens HTML & CSS I

Turma Teens { Reprograma }| Online | Formulários e Tabelas HTML e Responsividade.

Plano de aula desenvolvido para a <b>segunda semana</b> do curso. As aulas acontecerão nos dias 10 (sábado) e 14 (quarta-feira) de julho 2021.

<hr>

<div align="center">
  <img alt="escrito hello world na cor roxa no fundo branco" src="https://media.giphy.com/media/MeJgB3yMMwIaHmKD4z/giphy.gif"  width="250">
</div>

## Recapitulando...

- Elemento `div`

O elemento `div`, também conhecido como **elemento de divisão**, é um container genérico para conteúdo de fluxo, que de certa forma não representa nada. Ele pode 
ser utilizado para agrupar elementos para fins de estilos (usando class ou id).

Ele deve ser utilizado **somente** quando não tiver outro elemento de semântica tal como `<article>` ou `<nav>`.
```html
<div>
  <p> Qualquer tipo de conteúdo aqui. Como <p>, <img>.</p>
</div>
```

- Declarando o tipo de documento de um documento HTML

Na parte superior do documento, você precisa informar ao navegador qual versão de HTML sua página está usando. 
HTML é uma linguagem em evolução e é atualizada regularmente. A maioria dos navegadores principais oferece suporte à especificação mais recente, que é HTML5. 
No entanto, as páginas da web mais antigas podem usar versões anteriores do idioma.

É preciso fornecer essas informações ao navegador adicionando a tag `<! DOCTYPE ...>` na **primeira linha**, onde a parte ... é a versão do HTML. 
Para HTML5, você usa `<! DOCTYPE html>`.

> O ! e DOCTYPE maiúsculo é importante, especialmente para navegadores mais antigos. O html não faz distinção entre maiúsculas e minúsculas.

Em seguida, o resto do seu código HTML precisa ser embrulhado em tags html. A abertura <html> vai diretamente abaixo da linha <! DOCTYPE html>, e o fechamento </html> vai no final da página.
```html
<!DOCTYPE html>
<html>

</html>
```

- Head e o Body de um documento HTML

É possível adicionar outro nível de organização no documento HTML dentro das tags `html` com os elementos `head` e `body`. 

- `head`: **Informações** sobre a página. Inclui elementos `metadata` como `link`, `meta`, `title` e `style`
- `body`: **conteúdo** da página (o que é exibido para o usuário).
```html
<!DOCTYPE html>
<html>
  <head>
    <meta />
  </head>
  <body>
    <main>
    </main>
  </body>
</html>
```

## Formulários

Formulários HTML são um dos principais pontos de interação entre um usuário e um web site ou aplicativo. Eles permitem que os usuários enviem dados para o web site. 
Na maior parte do tempo, os dados são enviados para o servidor da web (para processamento).

<div align="center">
  <img alt="fundo branco com escrita em preto de formulário com user, password e senha com botão de submit e reset" src="https://res.cloudinary.com/practicaldev/image/fetch/s--ZwzE9As_--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_66%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/6znlo82yh0q4yitrtsmx.gif" width="400">
</div>

### Criando um formulário

- Elemento `<form>`

O elemento `<form>` é um contêiner para diferentes tipos de elementos de entrada, como: text fields, checkboxes, radio buttons, submit buttons...
```html
<form>
  
</form>
```

- Criando campo de texto com o elemento `input`

Uma forma conveniente para obter informações do usuário são através do `<input>` elementos de entrada. Um elemento `<input>` pode ser exibido de várias maneiras, 
dependendo do ***atributo type***.
```html
<input type="text">
```
 
| Tipo | Descrição |
| --- | ---|
| `<input type="text">` | Exibe um campo de entrada de texto de linha única |
| `<input type="radio">` | Exibe um botão de opção (para selecionar uma das muitas opções) | 
| `<input type="checkbox">`| Exibe uma caixa de seleção (para selecionar zero ou mais de muitas opções) |
| `<input type="submit">`| Exibe um botão de envio (para enviar o formulário) |
| `<input type="button">`| Exibe um botão clicável |

- Campos de Texto

O `<input type="text">` define um campo de entrada de linha única para entrada de texto.
```html
<form>
  <label for="fname">First name:</label>
  <input type="text" id="fname" name="fname" value="Beatriz">
  <label for="lname">Last name:</label>
  <input type="text" id="lname" name="lname" value="Nonato">
</form>
```

O atributo `value` contém o valor default. É opcional exceto para `checkboxes` e `radio buttons`.

O atributo `name` serve para representar uma coleção de valores, enviados através de um formulário, para o servidor. Sempre que realizamos um “submit” de um formulário, o atributo `name` é o identificador dentro de 
uma requisição GET ou POST no servidor.

Observe que cada campo de entrada deve ter um atributo de `name` a ser enviado. Se o atributo `name` for *omitido*, o valor do campo de entrada não será enviado. [Exemplo Prático](https://www.w3schools.com/html/tryit.asp?filename=tryhtml_form_submit_id)

**name** x **id**

**name** é identificador e é usado na ***solicitação http*** enviada pelo navegador para o servidor como um nome de variável associado aos dados contidos no atributo value
do elemento. O **id**, por outro lado, é um identificador ***exclusivo para navegador***, lado do cliente e JavaScript.


- O elemento `<label>`

A tag `<label>` define um rótulo para muitos elementos do formulário.

O elemento `<label>` é útil para usuários de leitores de tela, porque o leitor de tela lerá em voz alta o rótulo quando o usuário focar no elemento de entrada.

O elemento `<label>` também ajuda os usuários que têm dificuldade em clicar em regiões muito pequenas (como radio buttons ou checkboxes), 
porque quando o usuário clica no texto dentro do elemento `<label>`, ele alterna o botão/caixa de seleção.

> É uma boa prática o atributo for da tag `<label>` ser **igual** ao atributo **id** do elemento `<input>` para **vinculá-los**. Isso permite que tecnologias assistivas criem um relacionamento vinculado entre `label`
e o elemento de `input`.

É possível encapsular o `input` nas tags `label`
```html
<label for="indoor"> 
  <input id="indoor" type="radio" name="indoor-outdoor">Indoor 
</label>
```

- Botões de opções

É usado para perguntas em que é necessário que o usuário dê apenas **uma resposta** entre várias opções.

`radio buttons` são um tipo de entrada.

Todos os botões de opção relacionados devem ter o **mesmo atributo de** `name` para criar um grupo de botões de opção. Ao criar um grupo de opções, 
selecionar qualquer botão de opção desmarcará automaticamente os outros botões dentro do mesmo grupo, garantindo que apenas uma resposta seja fornecida 
pelo usuário.
```html
<p>Choose your favorite Web language:</p>

<form>
  <input type="radio" id="html" name="fav_language" value="HTML">
  <label for="html">HTML</label>
  <input type="radio" id="css" name="fav_language" value="CSS">
  <label for="css">CSS</label>
  <input type="radio" id="javascript" name="fav_language" value="JavaScript">
  <label for="javascript">JavaScript</label>
</form> 
```

- Conjunto de caixas de seleção

Os formulários costumam usar `checkboxes` para perguntas que podem ter **mais de uma resposta**.

`checkboxes` são um tipo de entrada.

Todas as entradas de `checkboxes` relacionadas devem ter o mesmo atributo de `name`.
```html
<p>The <strong>input type="checkbox"</strong> defines a checkbox:</p>

<form action="/url-where-you-want-to-submit-form-data">
  <input type="checkbox" id="vehicle1" name="vehicle1" value="Bike">
  <label for="vehicle1"> I have a bike</label>
  <input type="checkbox" id="vehicle2" name="vehicle2" value="Car">
  <label for="vehicle2"> I have a car</label>
  <input type="checkbox" id="vehicle3" name="vehicle3" value="Boat">
  <label for="vehicle3"> I have a boat</label>
</form> 
```

O atributo `action` envia os dados a um servidor usando nada mais do que HTML puro. Pra isso acontecer é necessário especificar o atributo de `action` no elemento de formulário.

> É considerada a melhor prática definir explicitamente o relacionamento entre uma entrada de caixa de seleção e seu rótulo correspondente, definindo o atributo for no elemento label para corresponder ao atributo id do elemento de entrada associado.

- Seleção por padrão com botões de radio e caixas de seleção

É possível definir que os `inputs` `radio` e `checkboxes` venham marcados como **padrão** (default). Basta usar o atributo `checked`
```html
<input type="radio" name="test-name" checked>
```

- Atributo `value` com radio buttons e checkboxes

Quando um formulário é enviado, os dados são enviados ao servidor e incluem `inputs` para as opções selecionadas. Os `inputs` do tipo `radio` e `checkboxes` relatam seus valores a partir do atributo de `value`.
```html
<label for="indoor">
  <input id="indoor" value="indoor" type="radio" name="indoor-outdoor">Indoor
</label>
<label for="outdoor">
  <input id="outdoor" value="outdoor" type="radio" name="indoor-outdoor">Outdoor
</label>
```

Aqui, tenho dois inputs de radio. Quando o usuário envia o formulário com a opção indoor selecionada, os dados do formulário incluirão a linha: indoor-outdoor = indoor. Isso vem dos atributos de name e value do input "indoor". Porque é enviado pro formulário name / value dos dados.

Se o atributo value for *omitido*, os dados do formulário enviarão o valor default que é on. Nesse cenário o usuário clicou na opção indoor e enviou o formulário, os dados do formulário seriam indoor-outdoor = on, o que não é útil. Portanto, o atributo de `value` precisa ser definido como algo para identificar a opção.

- Adicionar um botão de envio a um formulário

Clicar neste botão enviará os dados do formulário para o URL especificado com o atributo de action do formulário.
```html
<button type="submit">this button submits the form</button>
```

Aplicando o botão submit no formulário
```html
<form>
  <label for="fname">First name:</label>
  <input type="text" id="fname" name="fname" value="Beatriz">
  <label for="lname">Last name:</label>
  <input type="text" id="lname" name="lname" value="Nonato">
  <input type="submit" value="Submit">
</form>
```

- Exigir campo com o atributo `required`

Há uma forma de exigir campos específicos do formulário para que o usuário não possa enviar o formulário antes de preenchê-los. Basta adicionar o atributo `required`.
```html
<input type="text" required>
```

- Adicionando texto de espaço reservado a um campo de texto com o atributo `placeholder`

O texto de espaço reservado `placeholder` é o que é exibido em seu elemento de entrada antes de o usuário inserir qualquer coisa.
```html
<input type="text" placeholder="this is placeholder text">
```
<hr>

#### Links para estudo

- Mais sobre formulários

[Meu primeiro formulário](https://developer.mozilla.org/pt-BR/docs/Learn/Forms/Your_first_form)

[Formulários](https://www.w3schools.com/tags/tag_form.asp)

[Formulários com HTML e CSS - Vídeo](https://www.youtube.com/watch?v=wwqOJ2o84S4)

- Gifs

[Giphy](https://giphy.com/)

- Icones

[Humaaans](https://www.humaaans.com/)

[The Noun Project](https://thenounproject.com/)

<h4 align="center">Bons estudos !!!<h4>

<div align="center">
	<img alt="gato preto digitando no notebook" src="https://media1.tenor.com/images/cf8298a83e3aa087cdf4c6987077ea03/tenor.gif?itemid=5705738" width="280">
<div>

