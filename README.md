
TypeDoc: `Markdown` <br>
Titulo: `Padronização escrita Survey123 connect` <br>
Ultima atualização: `27/03/2025` <br>

<img src="logo_login_form.png" alt="Exemplo foto" width="300">

# <center>Introdução</center>
Existem muitas opções de escrita, seja em tamanho ou estilo da letra, para a <strong>AGT</strong> segue um exemplo de padronização.

- <strong>ARIAL - TAMANHO 12</strong><br>
- <strong>NOMENCLATURA - camelCase</strong><br>

**VARIÁVEIS INTERNAS**|**VARIÁVEIS EXTERNAS**
|--|--|
Para variáveis internas ou do próprio survey - <code style="color : #0070C0">AZUL</code> e fonte branca se o preenchimento da linha for da mesma, isso será de **padrão** nos projetos.| Para variáveis externas (Ex: **Criadas apartir de um banco e feitas para o projeto - <code style="color: #FF0000">VERMELHA</code> e fonte branca caso a linha seja preenchida da cor mencionada.**
Exemplo: [link](https://postimg.cc/K1Qj3v5z) | Exemplo: [link](https://postimg.cc/qNpg7CyS)

## Exemplos Práticos
Segue um exemplo de um formulário com as normas;

|type| name | label | hint |
|----|------|-------|------|
begin group | 	grupoInit| dados | 	<code style="color : #0070C0"># VAR INTERNA</code>
note  |	noteAgro	| noteAgro |	<code style="color: #0070C0"># VAR INTERNA </code>
text  |	testeAgro	| testeAgro |	<code style="color: #0070C0"># VAR INTERNA</code>
end group|||		<code style="color:#0070C0"># VAR INTERNA </code>


|type| name | label | hint |
|----|------|-------|------|
begin group | 	grupoInit| dados | 	<code style="color : #0070C0"># VAR INTERNA</code>
note  |	noteAgro	| noteAgro |	<code style="color: #0070C0"># VAR INTERNA </code>
text  |	testeAgro	| testeAgro |	<code style="color: #0070C0"># VAR INTERNA</code>
end group|||		<code style="color:#0070C0"># VAR INTERNA </code>
|||     
|begin group|grupoMedian	|grupoMedianaUser|	<code style="color: #0070C0"># VAR INTERNA</code>
text|	testeAgroDois|	testeAgroDois|	<code style="color: #FF0000"># VAR BANCO</code>
end group|	|	|	<code style="color: #0070C0"># VAR INTERNA</code>

#### outra opção de escrita valida
![Exemplo foto](https://github.com/tomleme/doc_survey123/blob/main/exemple1.png)

## Boas Práticas
- Usar nomes descritivos e claros
- Evitar abreviação.
- Manter em todo o documento a nomenclatura

## Erros comuns
- Usar nomes genéricos como `teste`, `variavel1`
- Misturar nomenclaturas
- Não validar a escrita

## Externo
- [camelCase](https://www.techtarget.com/whatis/definition/CamelCase#:~:text=What%20is%20CamelCase?,has%20the%20first%20letter%20capitalized.)
- [Survey](https://doc.arcgis.com/pt-br/survey123/desktop/create-surveys/xlsformessentials.htm)</center>
<table><tr style="background-color:#0070C0; color: white;">
<td>Código cor azul:  #0070C0</td>
</table>
<table><tr style="background-color:#FF0000; color: white">
<td>Código cor vermelha: #FF0000</td>
</table>

<center>************************************************************************************************</center>

# <center><strong>Página Inicial Survey</strong></center>

## Estrutura do Formulário

Para começar a criação de um formulário básico no Survey123 Connect, utilizamos uma estrutura simples composta por diversos tipos de campos. Vamos precisar dos seguintes componentes principais:

- <strong>Note</strong>: Campo para exibir texto informativo, sem necessidade de interação do usuário, clique [aqui](https://doc.arcgis.com/pt-br/survey123/desktop/create-surveys/xlsformnotes.htm) para saber mais.

- <strong>Text</strong>: Campo para solicitar o preenchimento de texto pelo usuário, clique [aqui](https://support.esri.com/en-us/knowledge-base/how-to-add-placeholder-text-for-text-questions-in-arcgi-000031399) para saber mais.

- <strong>Integer</strong>: Campo destinado à entrada de números inteiros, clique [aqui](https://doc.arcgis.com/en/survey123/desktop/create-surveys/xlsformessentials.htm) para saber mais.

## Exemplo de Estrutura:

Abaixo, apresentamos um exemplo da estrutura básica de um formulário no Survey123 Connect. A tabela a seguir detalha os tipos de campos, seus nomes, rótulos e outras propriedades:

| type | name | label | hint | appearence |
|------|------|-------|------|------------|
begin group | pagInicial | | | field-list
note | espaco1 | | | 	label
note | bemVindo | 	Bem-vindo!Por favor, preencha o campo abaixo: | |  field-list
note | espaco | | | label
integer | matricula | Digite a Matrícula: | |  field-list
text | nome | Nome | |  hidden
text | unidade | Unidade | | hidden
note | espaco2 | | | label
note | mensagem | | | label
end group | | | 

## Explicação dos Campos

- Notes: Usamos três campos de tipo note para criar espaçamentos entre os textos e melhorar a legibilidade.
<br>
- Campo <strong>'bem_vindo'</strong>: Utiliza uma tag HTML <strong><code>&lt;h1&gt;</code></strong> para destacar o texto "Bem-vindo!" em um tamanho maior e em negrito. O texto subsequente será exibido normalmente após a quebra de linha, realizada pela tag <strong><code>&lt;h1&gt;Texto&lt;/h1&gt;</code></strong>.
<br>
- Campo <strong>'matricula'</strong>: Usamos um campo integer para capturar a matrícula do colaborador.
<br>
- Campos <strong>'nome'</strong> e <strong>'unidade'</strong>: São campos text ocultos (usando a propriedade <strong>hidden</strong>) para buscar e exibir as informações associadas à matrícula inserida, utilizando a função <strong>pulldata</strong>.

## Detalhes sobre as Tags HTML

- <code><strong>&lt;h1&gt;Seu Texto Aqui&lt;/h1&gt;</strong></code>: A tag <code><strong>&lt;h1&gt;</strong></code> define um texto em tamanho grande e em negrito. Se quiser adicionar uma quebra de linha, adicione a barra no final da tag <code><strong>(&lt;h1&gt;Texto&lt;/h1&gt;&lt;br/&gt;)</strong></code>, que separará as seções de texto subsequentes.
<br>
- <code><strong>&lt;b&gt;Seu Texto Aqui&lt;/b&gt;</strong></code>: A tag <code><strong>&lt;b&gt;</strong></code> coloca o texto em negrito.

## Fórmulas Utilizadas

#### 1. A função pulldata
Utilizada para buscar informações de uma tabela externa <strong>(csv utf-8)</strong> com base em um valor chave, neste caso, a matrícula. A fórmula segue o formato:

|Exemplos|
|-|
<strong>pulldata('Nome da Tabela', 'Coluna a ser recuperada', 'Valor chave para busca', 'Campo de destino no Survey')</strong>
<strong>pulldata('DDS', 'Funcionario', 'Matricula', ${matricula})</strong>

- <b>'DDS'</b>: Nome da tabela onde os dados estão armazenados.
- <b>'Funcionario'</b>: Nome da coluna que contém os dados que queremos buscar.
- <b>'Matricula'</b>: O campo chave utilizado para localizar o valor correto.
- <b>${matricula}</b>: O valor inserido no campo "matricula" que será usado para realizar a busca na tabela.

#### 2. Função concat
Para montar a mensagem de boas-vindas, usamos a função <strong>concat</strong> para juntar o nome e a unidade do colaborador, retornados pela função <strong>pulldata</strong>. A fórmula fica assim:
|Exemplo|
|-|
<code>concat('Olá, ', &#36;{nome}, '! Você trabalha na Unidade ', &#36;{unidade}, '. Siga para a próxima página.')</code>

#### 3. Validação de Campos
|Exemplo|
|-|
&#36;{nome} != ' ' and ${unidade} != ' '

###### Explicação dos Componentes:
- <b>${nome}</b>: Variável que armazena o valor do campo "nome".
- !=: Operador "diferente de". A validação será verdadeira se os campos não estiverem vazios.
- and: Operador lógico "E". A validação será verdadeira apenas se ambos os campos tiverem valores.
- ‘ ’: Espaço em branco, utilizado para verificar se o campo está vazio. Se a validação não funcionar, tente usar <strong>" "</strong> (aspas simples) para valores nulos.

clique [aqui](#externo) para saber mais sobre essas funções.

## Conclusão
A adoção e compartilhamento das normas aqui apresentadas vai garantir consistência e clareza nos próximos projetos realizados na empresa.
