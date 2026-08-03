Aqui está um exemplo de um botão criado apenas com um ícone:
<!-- Botão só com ícone -->
<button>
    <img src="lupa.svg" alt="">
</button>

Sem o uso de ARIA Label, o leitor de tela pode não fornecer informações suficientes ao usuário. Para resolver isso, podemos adicionar o ARIA Label ao botão, como mostrado abaixo:
<button aria-label="Pesquisar">
    <img src="lupa.svg" alt="">
</button>
Com o ARIA Label, deixamos claro que é um botão de pesquisa, permitindo que o leitor de tela leia "pesquisar" e entenda a função do botão.

***

Exemplificando o uso de ARIA Labeled By e ARIA Described By
Temos o ARIA Labeled By, cujo intuito é usar o conteúdo de outro elemento visível como rótulo. Podemos utilizá-lo quando o texto já está na página e queremos reaproveitá-lo, como no caso de um formulário de pesquisa com uma seção de dados pessoais.

Veja um exemplo de um formulário sem a conexão semântica adequada:
<h2 id="titulo">Cadastro</h2>
<form>
    <input type="text" placeholder="Digite seu nome">
</form>
Ao usar o ARIA Labeled By, conectamos o form ao título existente, permitindo que o leitor de tela leia "formulário de cadastro, campo, nome":
<h2 id="titulo">Cadastro</h2>
<form aria-labelledby="titulo">
    <label for="nome">Nome</label>
    <input id="nome" type="text" placeholder="Digite seu nome">
</form>

***

or último, o ARIA Described By fornece uma explicação extra sobre o elemento, usado quando precisamos dar instruções adicionais para um campo ou botão.

Considere o exemplo a seguir, onde a informação adicional não está associada ao campo de entrada:
<label for="senha">Senha</label>
<input id="senha" type="password">
<small>Mínimo 8 caracteres</small>

Ao adicionar o ARIA Described By ao input, associamos o texto auxiliar ao campo, permitindo que o leitor de tela entenda que o input de senha requer no mínimo oito caracteres:
<label for="senha">Senha</label>
<input id="senha" type="password" aria-describedby="ajuda-senha">
<small id="ajuda-senha">Mínimo 8 caracteres</small>