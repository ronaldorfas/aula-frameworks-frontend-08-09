[aulas_08_e_09_react.md](https://github.com/user-attachments/files/35056700/aulas_08_e_09_react.md)
# aula-frameworks-frontend-08-09# 📚 Frameworks Front-end — Aulas 08 e 09
## Projeto React | Material de estudo e espaço para o projeto

**Professor:** Prof. Me. Deivison S. Takatu  
**Curso/Unidade:** Frameworks Front-end  
**Material organizado a partir dos PDFs das Aulas 08 e 09.**

---

# 🧭 Sumário

- [🎯 Visão geral](#-visão-geral)
- [📘 Aula 08 — Projeto React](#-aula-08--projeto-react)
  - [1. Revisão de JavaScript](#1-revisão-de-javascript)
  - [2. JSX](#2-jsx)
  - [3. Componentes](#3-componentes)
  - [4. Props](#4-props)
  - [5. DOM e Virtual DOM](#5-dom-e-virtual-dom)
  - [6. Listas e Keys](#6-listas-e-keys)
  - [7. Renderização condicional](#7-renderização-condicional)
  - [8. Atividade da Aula 08](#8-atividade-da-aula-08)
- [📗 Aula 09 — Projeto React 02](#-aula-09--projeto-react-02)
  - [1. State e useState](#1-state-e-usestate)
  - [2. Formulários](#2-formulários)
  - [3. useEffect](#3-useeffect)
  - [4. Consumo de APIs](#4-consumo-de-apis)
  - [5. React Router](#5-react-router)
  - [6. Atividade da Aula 09](#6-atividade-da-aula-09)
- [🧩 Integração dos conteúdos](#-integração-dos-conteúdos)
- [🛠️ Espaço para o projeto](#️-espaço-para-o-projeto)
- [✅ Checklist de desenvolvimento](#-checklist-de-desenvolvimento)
- [🔗 Links complementares](#-links-complementares)
- [📝 Anotações pessoais](#-anotações-pessoais)

---

# 🎯 Visão geral

As Aulas 08 e 09 desenvolvem os fundamentos necessários para construir uma aplicação com React.

| Aula | Foco | Conteúdos principais |
|---|---|---|
| **08 — Projeto React** | Estruturação da interface | Revisão de JavaScript, JSX, componentes, props, DOM/Virtual DOM, listas, keys e renderização condicional |
| **09 — Projeto React 02** | Interatividade, dados e navegação | State/useState, formulários, useEffect, consumo de APIs e React Router |

A proposta das atividades é desenvolver uma aplicação React que reúna os conceitos estudados e publicar o projeto em um repositório público no GitHub, acompanhado de um README.

---

# 📘 Aula 08 — Projeto React

## 1. Revisão de JavaScript

Antes de trabalhar com React, é importante compreender os recursos de JavaScript utilizados na construção da aplicação.

### 1.1 Onde o JavaScript pode ser utilizado?

- **No HTML:** por meio da tag `<script>`.
- **Em arquivo externo:** vinculado pelo atributo `src` da tag `<script>`. Essa organização facilita a manutenção de projetos maiores.
- **Em eventos:** atributos como `onclick` e `onblur` permitem responder às ações do usuário.

O JavaScript permite criar interatividade, manipular o DOM, desenvolver animações, aplicar efeitos visuais e consumir dados de servidores.

### 1.2 Variáveis

JavaScript permite declarar variáveis em diferentes pontos do código. Os identificadores são *case sensitive*: `nome`, `Nome` e `NOME` são nomes diferentes.

- `var`: possui escopo de função.
- `let`: possui escopo de bloco (`{ }`).
- `const`: utilizada para declarar uma referência que não será reatribuída.

```js
const nome = "João";
let idade = 20;
const estudante = true;

console.log(nome);
console.log(idade);
console.log(estudante);

console.log(typeof nome);
console.log(typeof idade);
console.log(typeof estudante);

console.log(`Olá, ${nome}! Você tem ${idade} anos.`);
```

### 1.3 Tipos de dados

| Tipo | Exemplo / significado |
|---|---|
| `String` | `"Olá"` — texto |
| `Number` | `10`, `3.14` — números |
| `Boolean` | `true` ou `false` |
| `Undefined` | valor não definido |
| `Null` | ausência intencional de valor |
| `Object` | `{ nome: "Ana", idade: 20 }` |
| `Array` | `[10, 20, 30]` |
| `Symbol` | identificador único |
| `BigInt` | números inteiros muito grandes |

O operador `typeof` permite verificar o tipo de um valor.

### 1.4 Operadores

**Aritméticos**

| Operador | Função |
|---|---|
| `+` | Soma |
| `-` | Subtração |
| `*` | Multiplicação |
| `/` | Divisão |
| `%` | Resto da divisão |
| `**` | Exponenciação |
| `++` / `--` | Incremento / decremento |

**Comparação**

| Operador | Função |
|---|---|
| `==` | Compara valores, permitindo conversão de tipo |
| `===` | Compara valor e tipo |
| `!=` | Verifica se os valores são diferentes |
| `!==` | Verifica se valor ou tipo são diferentes |
| `>` / `<` | Maior que / menor que |
| `>=` / `<=` | Maior ou igual / menor ou igual |

**Lógicos**

- `&&` — E: todas as condições devem ser verdadeiras.
- `||` — OU: pelo menos uma condição deve ser verdadeira.
- `!` — NÃO: inverte o resultado lógico.

**Atribuição**

- `=` atribui um valor.
- `+=`, `-=`, `*=`, `/=` e `%=` executam uma operação e atribuem o resultado.

```js
const nota1 = 8;
const nota2 = 7;
const media = (nota1 + nota2) / 2;

console.log("Média:", media);
console.log("Aprovado:", media >= 7);
console.log("Notas iguais:", nota1 === nota2);
```

### 1.5 Condicionais

As condicionais executam diferentes blocos de código de acordo com uma condição booleana.

```js
const nota = 8;

if (nota >= 9) {
  console.log("Excelente");
} else if (nota >= 7) {
  console.log("Aprovado");
} else {
  console.log("Reprovado");
}

const resultado = nota >= 7 ? "Aprovado" : "Reprovado";
console.log(resultado);
```

- `if`: testa uma condição.
- `else if`: testa outra condição quando a anterior não é atendida.
- `else`: executa o caminho alternativo.
- Operador ternário: `condicao ? valorSeVerdadeiro : valorSeFalso`.

### 1.6 Estruturas de repetição

Permitem executar um bloco de código várias vezes.

- `for`: utilizado quando sabemos ou controlamos a quantidade de repetições.
- `while`: repete enquanto uma condição for verdadeira.
- `do...while`: executa o bloco pelo menos uma vez e depois verifica a condição.
- `break`: interrompe a repetição.
- `continue`: encerra a iteração atual e passa para a próxima.

```js
for (let i = 1; i <= 10; i++) {
  console.log(i);
}

for (let i = 1; i <= 10; i++) {
  if (i % 2 === 0) {
    console.log("Número par:", i);
  }
}
```

### 1.7 Funções

Funções são blocos de código que executam uma tarefa. Podem receber parâmetros e devolver resultados com `return`. Ajudam a organizar o código e evitar repetição.

```js
function somar(a, b) {
  return a + b;
}

const resultado = somar(10, 20);

const multiplicar = (a, b) => a * b;

console.log(resultado);
console.log(multiplicar(5, 4));
```

Também aparecem na revisão algumas funções e métodos úteis:

- `console.log()` — mostra mensagens no console.
- `alert()`, `prompt()` e `confirm()` — interação básica com o usuário.
- `document.getElementById()` e `document.querySelector()` — selecionam elementos HTML.
- `addEventListener()` — adiciona eventos.
- `innerHTML` e `textContent` — alteram conteúdo de elementos HTML.

### 1.8 Arrays

Arrays armazenam vários valores em uma única variável. Os elementos ficam em sequência e são acessados por índices.

```js
const frutas = ["Maçã", "Banana", "Laranja"];
const notas = [7, 8, 5, 9, 10];

console.log(frutas[0]);
console.log(notas.length);

notas.forEach((nota, indice) => {
  console.log(indice, nota);
});

const aprovados = notas.filter((nota) => nota >= 7);
console.log(aprovados);
```

- `length`: quantidade de elementos.
- `forEach()`: executa uma função para cada item.
- `filter()`: cria uma coleção com os itens que atendem a uma condição.

### 1.9 Objetos

Objetos agrupam informações relacionadas em propriedades e comportamentos em métodos.

```js
const aluno = {
  nome: "Carlos",
  idade: 20,
  curso: "ADS",

  apresentar() {
    console.log(`Meu nome é ${this.nome} e curso ${this.curso}.`);
  }
};

console.log(aluno.nome);
aluno.apresentar();
```

- **Propriedades:** armazenam dados.
- **Acesso:** permite consultar ou alterar propriedades.
- **Métodos:** funções associadas ao objeto.
- `this`: referencia o próprio objeto dentro de seus métodos.

### 1.10 DOM e manipulação com JavaScript

O DOM (*Document Object Model*) representa a estrutura de uma página web em forma de árvore. O JavaScript pode localizar elementos e alterar seu conteúdo.

Métodos e propriedades citados na aula:

- `getElementById()` — seleciona pelo identificador.
- `querySelector()` — seleciona o primeiro elemento que corresponde a um seletor CSS.
- `querySelectorAll()` — seleciona todos os elementos correspondentes.
- `textContent` — altera o texto.
- `value` — altera o valor de um campo.
- `classList` — adiciona, remove ou alterna classes CSS.
- `createElement()` — cria um elemento.
- `appendChild()` — adiciona um elemento ao documento.

```js
const botao = document.querySelector("#botao");
const texto = document.querySelector("#mensagem");

botao.addEventListener("click", () => {
  texto.textContent = "Olá! O conteúdo foi alterado.";
});
```

---

## 2. JSX

### 2.1 O que é JSX?

JSX é uma extensão de sintaxe para JavaScript que permite escrever estruturas semelhantes a HTML dentro do JavaScript. É utilizado para descrever interfaces dos componentes React.

```jsx
const titulo = <h1>Olá, React!</h1>;
```

### 2.2 Por que utilizar JSX?

- Facilita a leitura da estrutura da interface.
- Combina elementos visuais e expressões JavaScript.
- Organiza interfaces dentro de componentes.
- Relaciona dados ao conteúdo exibido.
- É transformado em JavaScript antes da execução.

### 2.3 Expressões JavaScript no JSX

Utilizamos chaves `{ }` para inserir expressões JavaScript.

```jsx
const nome = "João";
const saudacao = <h1>Olá, {nome}!</h1>;

const a = 10;
const b = 5;
const resultado = <p>Soma: {a + b}</p>;
```

### 2.4 Diferenças entre JSX e HTML

- Utiliza `className` em vez de `class`.
- Utiliza `htmlFor` em vez de `for`.
- Elementos sem conteúdo devem ser fechados, como `<img />`.
- O componente deve retornar um elemento raiz ou utilizar Fragment.
- Valores JavaScript são inseridos entre chaves `{ }`.

```jsx
function LinkDocumentacao() {
  return (
    <a href="https://react.dev" className="link">
      Documentação do React
    </a>
  );
}
```

---

## 3. Componentes

### 3.1 O que é um componente?

Componentes são unidades independentes e reutilizáveis da interface. Em React, normalmente são funções JavaScript que retornam elementos React, geralmente utilizando JSX.

Exemplos de partes que podem ser componentes em uma loja virtual:

- Cabeçalho;
- Busca;
- Produto;
- Rodapé.

### 3.2 Por que dividir uma interface?

- Uma página pode ter menu, busca, cartões e rodapé.
- Colocar tudo em um único componente dificulta a leitura.
- Dividir a página facilita a organização.
- Cada parte pode ser reutilizada em outras páginas.

### 3.3 Criando e utilizando componentes

- Crie uma função com nome iniciado em letra maiúscula.
- Utilize `return` para definir o que será exibido.
- Use `<NomeDoComponente />` para exibir o componente.
- Combine componentes para montar uma página.

```jsx
function Cabecalho() {
  return <h1>Catálogo React</h1>;
}

function Rodape() {
  return <footer>Material de estudo</footer>;
}

function App() {
  return (
    <main>
      <Cabecalho />
      <p>Explore os principais conceitos.</p>
      <Rodape />
    </main>
  );
}
```

### 3.4 Árvore de componentes

Uma aplicação pode ser representada como uma árvore hierárquica. O componente principal contém componentes filhos, que também podem conter outros componentes.

Exemplo de organização:

```text
App
├── Cabecalho
├── BarraDePesquisa
├── ListaDeConceitos
│   ├── CardConceito
│   └── CardConceito
└── Rodape
```

A reutilização evita repetir estruturas semelhantes e ajuda a manter a consistência visual.

---

## 4. Props

### 4.1 O que são Props?

Props é a abreviação de *properties* (propriedades). São dados recebidos por um componente e permitem enviar informações de um componente pai para um componente filho.

As props permitem reutilizar um mesmo componente com conteúdos diferentes.

```jsx
function CardConceito({ titulo, descricao }) {
  return (
    <article>
      <h2>{titulo}</h2>
      <p>{descricao}</p>
    </article>
  );
}
```

### 4.2 Utilizando Props

```jsx
<CardConceito
  titulo="JSX"
  descricao="Sintaxe para descrever interfaces."
/>

<CardConceito
  titulo="Props"
  descricao="Entradas recebidas por componentes."
/>
```

A estrutura do componente permanece igual; os dados exibidos mudam.

### 4.3 Fluxo de dados

- Em uma arquitetura comum, os dados fluem do componente pai para o filho.
- O componente pai organiza e fornece as informações.
- O componente filho recebe as props e apresenta os dados.
- Esse fluxo explícito facilita compreender a origem das informações.

### 4.4 Tipos de valores em Props

- Strings;
- Números;
- Booleanos (`true` ou `false`);
- Arrays e objetos;
- Funções;
- Elementos React.

---

## 5. DOM e Virtual DOM

### 5.1 O que é o DOM?

DOM (*Document Object Model*) é a representação estruturada do documento HTML disponibilizada pelo navegador. Permite que o JavaScript consulte e modifique elementos da página.

Exemplo:

```js
document.querySelector("h1").textContent = "Olá!";
```

### 5.2 O que é o Virtual DOM?

Virtual DOM é um termo utilizado para descrever uma representação da interface em memória.

- O React utiliza descrições de elementos para determinar como a interface deve se apresentar.
- O desenvolvedor descreve o resultado esperado.
- O React coordena o processo de atualização da interface.

### 5.3 DOM x Virtual DOM

| DOM | Virtual DOM |
|---|---|
| Representa a estrutura do documento no navegador. | Representação da interface utilizada pelo React. |
| Pode ser consultado e modificado por JavaScript. | Ajuda o React a coordenar atualizações da interface. |
| Reflete a estrutura do documento renderizado. | Representa como a interface deve se apresentar. |

### 5.4 Como funciona a atualização da interface?

1. **Mudança:** ocorre uma interação ou atualização de dados.
2. **Renderização:** o React executa novamente os componentes relevantes para calcular a nova descrição da interface.
3. **Reconciliação:** o React compara a nova descrição com a anterior.
4. **Atualização:** as alterações necessárias são aplicadas ao ambiente de renderização, como o DOM do navegador.

Nem toda nova renderização exige alterações no DOM. A reconciliação considera a estrutura e a identidade dos elementos.

---

## 6. Listas e Keys

### 6.1 Por que renderizar listas?

Aplicações frequentemente exibem listas de alunos, produtos, tarefas e conceitos. Esses dados normalmente são armazenados em arrays.

O método `map()` transforma cada item de um array em um elemento da interface.

```jsx
const nomes = ["João", "Maria", "Ana"];

const itens = nomes.map((nome) => (
  <li>{nome}</li>
));
```

### 6.2 O que é `key`?

`key` é uma propriedade especial utilizada pelo React para identificar elementos entre irmãos em uma lista.

- Ajuda a reconhecer itens mantidos, adicionados, removidos ou reordenados.
- Deve ser informada ao renderizar listas.
- Normalmente utiliza um identificador associado a cada item.
- Chaves estáveis facilitam a associação dos itens quando a lista é alterada.

```jsx
const alunos = [
  { id: 101, nome: "Ana" },
  { id: 102, nome: "Bruno" },
  { id: 103, nome: "Caio" }
];

function ListaAlunos() {
  return (
    <ul>
      {alunos.map((aluno) => (
        <li key={aluno.id}>{aluno.nome}</li>
      ))}
    </ul>
  );
}
```

### 6.3 Listas, filtros e atualização

- `filter()` seleciona os itens que atendem a uma condição.
- `map()` transforma os itens selecionados em elementos JSX.
- As chaves devem continuar associadas aos mesmos itens após a filtragem.
- Quando uma lista está em estado, prefira produzir novos arrays em vez de modificar diretamente o array existente.

```jsx
const conceitos = ["JSX", "Props", "State", "Hooks"];

function ConceitosBasicos() {
  const basicos = conceitos.filter((item) => item !== "Hooks");

  return (
    <ul>
      {basicos.map((item) => (
        <li key={item}>{item}</li>
      ))}
    </ul>
  );
}
```

---

## 7. Renderização condicional

### 7.1 O que é?

Permite mostrar, ocultar ou alterar partes da interface conforme uma condição. Utiliza expressões e operadores JavaScript dentro do JSX.

As condições podem depender de props, estado ou dados recebidos pela aplicação.

### 7.2 Utilizando `if` e `return`

É indicada quando as partes da interface são substancialmente diferentes.

```jsx
function MensagemAcesso({ autenticado }) {
  if (autenticado) {
    return <p>Bem-vindo de volta!</p>;
  }

  return <p>Entre para continuar.</p>;
}
```

### 7.3 Dados, listas e estado vazio

Uma lista pode apresentar os resultados ou uma mensagem quando estiver vazia.

```jsx
function ListaResultados({ resultados }) {
  if (resultados.length === 0) {
    return <p>Nenhum resultado encontrado.</p>;
  }

  return (
    <ul>
      {resultados.map((resultado) => (
        <li key={resultado.id}>{resultado.nome}</li>
      ))}
    </ul>
  );
}
```

### 7.4 Operador ternário e carregamento

O operador ternário pode apresentar mensagens diferentes conforme o estado.

```jsx
function ResultadoBusca({ carregando }) {
  return (
    <div>
      {carregando
        ? <p>Buscando...</p>
        : <p>Busca finalizada.</p>}
    </div>
  );
}
```

Em aplicações maiores, carregamento, erro e sucesso podem precisar de tratamentos distintos.

---

## 8. Atividade da Aula 08

### 🎯 Proposta apresentada no material

Desenvolver uma aplicação React que utilize os conceitos estudados na aula:

- JSX;
- Componentes;
- Props;
- Virtual DOM;
- Listas;
- Renderização condicional.

**Entrega solicitada:**

- Criar um repositório público no GitHub.
- Criar um README contendo a descrição, as funcionalidades e os conceitos utilizados.

### 📌 Registro da atividade

**Ideia da aplicação:**

> Escreva aqui a ideia escolhida.

**Funcionalidades planejadas:**

- [ ] 
- [ ] 
- [ ] 

**Conceitos da Aula 08 que serão utilizados:**

- [ ] JSX
- [ ] Componentes
- [ ] Props
- [ ] Listas com `map()`
- [ ] `key` nos itens
- [ ] `filter()` (se aplicável)
- [ ] Renderização condicional

---

# 📗 Aula 09 — Projeto React 02

## 1. State e useState

### 1.1 O que é State?

State é uma informação que o componente guarda, como um contador ou uma mensagem. Permite atualizar a interface conforme as ações do usuário.

Quando o estado muda, o React renderiza novamente o componente para atualizar a tela.

### 1.2 Por que uma variável comum não basta?

- Variáveis comuns guardam valores, mas não atualizam a tela automaticamente.
- Alterar uma variável não faz o React renderizar o componente novamente.
- Quando o componente é executado novamente, as variáveis locais são recriadas.
- O state guarda valores entre renderizações e atualiza a interface quando eles mudam.

Exemplo de variável comum:

```jsx
function Contador() {
  let valor = 0;

  function incrementar() {
    valor = valor + 1;
  }

  return (
    <button onClick={incrementar}>
      Valor: {valor}
    </button>
  );
}
```

Nesse exemplo, clicar no botão altera a variável, mas não solicita uma nova renderização.

### 1.3 O que são Hooks?

Hooks são funções especiais que permitem utilizar recursos do React em componentes funcionais.

- Permitem trabalhar com estado e outros recursos da aplicação.
- Seus nomes começam com `use`, como `useState` e `useEffect`.
- Devem ser utilizados no início do componente ou de outros Hooks, seguindo as regras do React.

### 1.4 Conhecendo `useState`

`useState` permite guardar informações que podem mudar durante o uso do componente.

Retorna dois elementos:

1. O valor atual do estado.
2. A função utilizada para atualizá-lo.

Recebe um valor inicial e deve ser importado do React.

```jsx
import { useState } from "react";

function Contador() {
  const [contador, setContador] = useState(0);

  return (
    <section>
      <p>Valor: {contador}</p>
      <button onClick={() => setContador(contador + 1)}>
        Incrementar
      </button>
    </section>
  );
}
```

**Leitura do exemplo:**

- `contador`: valor atual.
- `setContador`: função de atualização.
- `useState(0)`: estado iniciado em zero.
- Ao clicar, `setContador()` atualiza o valor e o React atualiza a interface.

---

## 2. Formulários

### 2.1 Para que servem?

Formulários permitem que o usuário informe dados para a aplicação. Em React, utilizam campos HTML, eventos e estado.

Podem ser usados em:

- Cadastros;
- Buscas;
- Login;
- Preferências.

O envio pode validar os dados e exibir uma mensagem ao usuário.

### 2.2 Campos controlados

São campos cujo valor é controlado pelo estado do React.

- A propriedade `value` define o valor exibido no campo.
- O evento `onChange` atualiza o estado conforme o usuário digita.

```jsx
import { useState } from "react";

function CampoNome() {
  const [nome, setNome] = useState("");

  return (
    <label>
      Nome
      <input
        value={nome}
        onChange={(evento) => setNome(evento.target.value)}
      />
    </label>
  );
}
```

### 2.3 Como atualizar um campo?

Fluxo de atualização:

**Digitação → evento `onChange` → leitura de `e.target.value` → atualização do estado.**

```jsx
const [nome, setNome] = useState("");

<input
  value={nome}
  onChange={(e) => setNome(e.target.value)}
/>
```

### 2.4 Envio do formulário

- `onSubmit` executa uma função quando o formulário é enviado.
- A função pode validar os dados ou exibir uma mensagem.
- `preventDefault()` evita o recarregamento da página.
- O envio pode ser tratado diretamente pelo React.

```jsx
function enviar(e) {
  e.preventDefault();
  alert("Formulário enviado!");
}

function Formulario() {
  return (
    <form onSubmit={enviar}>
      <button type="submit">Enviar</button>
    </form>
  );
}
```

### 2.5 Para que serve `preventDefault()`?

Impede que o navegador execute uma ação padrão. Em formulários, evita o recarregamento automático da página e permite que o React controle o que acontece após o envio.

```js
function enviar(e) {
  e.preventDefault(); // Evita recarregar a página
  alert("Enviado com sucesso!");
}
```

---

## 3. useEffect

### 3.1 O que são efeitos?

Efeitos permitem executar ações fora da renderização da interface. São usados quando o componente precisa interagir com recursos externos.

Exemplos apresentados na aula:

- Alterar o título da aba;
- Utilizar temporizadores;
- Buscar dados de APIs.

### 3.2 O que é `useEffect`?

`useEffect` é um Hook utilizado para sincronizar um componente com sistemas externos.

Recebe uma função que contém o efeito e pode receber uma lista de dependências para controlar quando ele precisa ser executado novamente.

```jsx
import { useEffect } from "react";

useEffect(() => {
  document.title = "Aula React";
}, []);
```

O array vazio `[]` indica, nos exemplos da aula, que o efeito será executado na montagem do componente.

### 3.3 Dependências do efeito

O efeito pode utilizar valores do componente. A lista de dependências deve refletir os valores utilizados pelo efeito.

```jsx
useEffect(() => {
  document.title = titulo;
}, [titulo]);
```

Quando `titulo` muda, o efeito é executado novamente.

### 3.4 Limpeza de um efeito

Alguns efeitos criam recursos que precisam ser liberados. A função de limpeza é retornada pelo próprio `useEffect`.

Ela evita que eventos ou temporizadores continuem ativos indevidamente. A limpeza ocorre antes de uma nova configuração do efeito quando suas dependências mudam e quando o componente deixa de ser utilizado.

```jsx
useEffect(() => {
  window.addEventListener("resize", atualizar);

  return () => {
    window.removeEventListener("resize", atualizar);
  };
}, []);
```

**Conceito-chave:** tudo o que for configurado e precisar ser encerrado deve ter uma limpeza adequada.

---

## 4. Consumo de APIs

### 4.1 O que é uma API?

API (*Application Programming Interface*) permite a comunicação entre sistemas.

Em aplicações React, possibilita buscar e enviar dados para serviços externos.

Exemplos de dados que podem ser consumidos:

- Produtos;
- Usuários;
- Publicações;
- Indicadores.

### 4.2 Buscando dados com `fetch`

- `fetch()` realiza requisições HTTP.
- A resposta é assíncrona: precisamos aguardar seu retorno.
- `response.json()` interpreta os dados JSON.
- `response.ok` permite identificar respostas HTTP bem-sucedidas.

```js
const response = await fetch(url);

if (!response.ok) {
  throw new Error("Erro");
}

const dados = await response.json();
```

### 4.3 O papel do useEffect na busca

`useEffect` pode iniciar uma busca quando o componente é exibido. O array vazio `[]` indica que o efeito será executado na montagem do componente.

`useState` armazena os dados recebidos e atualiza a interface quando eles mudam.

```jsx
useEffect(() => {
  async function carregar() {
    const resposta = await fetch(url);
    const dados = await resposta.json();
    setPublicacoes(dados);
  }

  carregar();
}, []);
```

### 4.4 Enviando dados com POST

O método `POST` permite enviar informações para uma API.

- `method`: define o método HTTP.
- `headers`: informa o formato do conteúdo.
- `JSON.stringify()`: transforma o objeto JavaScript em JSON.
- É importante verificar se a resposta foi bem-sucedida.

```js
await fetch("/api/publicacoes", {
  method: "POST",
  headers: {
    "Content-Type": "application/json"
  },
  body: JSON.stringify({
    title: "Aprendendo React"
  })
});
```

### 4.5 Erros e cuidados importantes

- Trate erros de rede e verifique o status HTTP.
- Considere carregamento, estado vazio e indisponibilidade do serviço.
- Evite requisições repetidas por dependências incorretas no `useEffect`.
- Não exponha chaves secretas no código do navegador.
- Respeite autenticação, limites de uso e políticas de CORS.

```js
try {
  const resposta = await fetch(url);

  if (!resposta.ok) {
    throw new Error("Erro na consulta");
  }

  const dados = await resposta.json();
} catch (erro) {
  console.error(erro);
}
```

---

## 5. React Router

### 5.1 Por que precisamos de roteamento?

Uma aplicação React pode ter várias telas, como início, catálogo, detalhes e sobre.

O roteamento associa caminhos da URL aos componentes exibidos. Organiza a navegação e evita concentrar toda a lógica em um único componente.

### 5.2 O que é React Router?

É uma biblioteca utilizada para organizar a navegação em React.

- Associa URLs a componentes.
- Permite navegar entre páginas sem recarregar todo o documento a cada clique.

Importações apresentadas:

```jsx
import {
  BrowserRouter,
  Routes,
  Route
} from "react-router-dom";
```

### 5.3 Conceitos fundamentais

- **Rota:** regra que associa um caminho a uma interface.
- **URL:** endereço da página atual.
- **Link:** elemento para navegar entre rotas.
- **Parâmetro:** parte variável do caminho.
- **Rota aninhada:** rota organizada dentro de uma estrutura pai.

### 5.4 Configurando rotas

- `BrowserRouter` envolve a aplicação.
- `Routes` agrupa as rotas disponíveis.
- `Route` define o caminho e o componente correspondente.

```jsx
<BrowserRouter>
  <Routes>
    <Route path="/" element={<Inicio />} />
    <Route path="/sobre" element={<Sobre />} />
  </Routes>
</BrowserRouter>
```

### 5.5 Navegação com Link

O componente `Link` permite navegar entre rotas. A propriedade `to` define o destino. É preferível a um link tradicional quando a navegação ocorre dentro da aplicação React.

```jsx
import { Link } from "react-router-dom";

function Menu() {
  return (
    <nav>
      <Link to="/">Início</Link>
      <Link to="/sobre">Sobre</Link>
    </nav>
  );
}
```

### 5.6 Parâmetros de rota

Parâmetros representam partes variáveis de uma URL e são úteis para páginas de detalhes. `useParams()` permite acessar esses valores.

```jsx
// Rota: /conceitos/:id
const { id } = useParams();

return <h1>Conceito: {id}</h1>;
```

---

## 6. Atividade da Aula 09

### 🎯 Proposta apresentada no material

Desenvolver uma aplicação React que utilize todos os conceitos estudados na aula:

- State e `useState`;
- Formulários;
- `useEffect`;
- Consumo de APIs;
- React Router.

**Entrega solicitada:**

- Criar um repositório público no GitHub.
- Criar um README contendo a descrição, as funcionalidades e os conceitos utilizados.

### 📌 Registro da atividade

**Ideia da aplicação:**

> Escreva aqui a ideia escolhida.

**Funcionalidades planejadas:**

- [ ] 
- [ ] 
- [ ] 

**Conceitos da Aula 09 que serão utilizados:**

- [ ] Estado com `useState`
- [ ] Formulário com campos controlados
- [ ] Evento `onChange`
- [ ] Envio com `onSubmit`
- [ ] `preventDefault()`
- [ ] `useEffect`
- [ ] Busca de dados com `fetch`
- [ ] Tratamento de erros e carregamento
- [ ] Navegação com React Router
- [ ] Parâmetros de rota (se aplicável)

---

# 🧩 Integração dos conteúdos

As duas aulas podem ser entendidas como etapas complementares na construção da aplicação.

| Recurso no projeto | Conceito relacionado |
|---|---|
| Estruturar o conteúdo de uma tela | JSX |
| Separar cabeçalho, cards e rodapé | Componentes |
| Reaproveitar um card com dados diferentes | Props |
| Exibir vários produtos, alunos ou conceitos | Arrays, `map()` e `key` |
| Filtrar itens | `filter()` |
| Mostrar mensagens diferentes conforme a situação | Renderização condicional |
| Atualizar dados na tela após uma interação | State e `useState` |
| Receber informações digitadas pelo usuário | Formulários controlados |
| Executar uma busca ao exibir um componente | `useEffect` e `fetch` |
| Exibir telas diferentes por endereço | React Router |
| Abrir uma tela de detalhes por identificador | Parâmetros de rota |

---

# 🛠️ Espaço para o projeto

> Use esta seção para registrar a ideia, organizar as telas, planejar as funcionalidades e acompanhar a implementação.

## 1. Identificação

**Nome do projeto:**  
`[Preencha aqui]`

**Integrantes:**  
`[Preencha aqui]`

**Repositório GitHub:**  
`[Cole o link aqui]`

**Link da aplicação publicada (se houver):**  
`[Cole o link aqui]`

## 2. Descrição

**Qual problema ou necessidade a aplicação pretende atender?**

> Escreva aqui.

**Qual é o objetivo principal?**

> Escreva aqui.

**Quem utilizará a aplicação?**

> Escreva aqui.

## 3. Funcionalidades

| Funcionalidade | Descrição | Status |
|---|---|---|
| 1. |  | ⬜ Pendente |
| 2. |  | ⬜ Pendente |
| 3. |  | ⬜ Pendente |
| 4. |  | ⬜ Pendente |
| 5. |  | ⬜ Pendente |

## 4. Páginas e navegação

| Página | URL/rota | O que será exibido |
|---|---|---|
| Início | `/` | |
| Listagem | `/...` | |
| Detalhes | `/.../:id` | |
| Sobre | `/sobre` | |

**Desenho ou rascunho da navegação:**

```text
Início
  ├── Listagem
  │     └── Detalhes
  └── Sobre
```

Adapte a estrutura conforme as páginas reais do projeto.

## 5. Componentes planejados

| Componente | Responsabilidade | Props previstas |
|---|---|---|
| `Cabecalho` | | |
| `Menu` | | |
| `Card` | | |
| `Lista` | | |
| `Rodape` | | |

**Outros componentes:**

> Registre aqui.

## 6. Dados e API

**A aplicação utilizará uma API?**  
`[ ] Sim  [ ] Não`

**Nome/serviço da API:**  
`[Preencha aqui]`

**Endpoint(s):**

```text
GET:
POST:
Outros:
```

**Quais dados serão recebidos ou enviados?**

> Escreva aqui.

**Estados que a interface deverá apresentar:**

- [ ] Carregando;
- [ ] Dados carregados;
- [ ] Lista vazia;
- [ ] Erro na requisição.

## 7. Formulários

**Qual formulário será implementado?**

> Escreva aqui.

**Campos:**

| Campo | Tipo | Obrigatório? | Validação/observação |
|---|---|---|---|
| | | | |
| | | | |
| | | | |

**O que deve acontecer após o envio?**

> Escreva aqui.

## 8. Organização dos arquivos

Rascunho de estrutura (adapte à organização escolhida):

```text
src/
├── components/
│   ├── Cabecalho.jsx
│   ├── Card.jsx
│   └── Rodape.jsx
├── pages/
│   ├── Inicio.jsx
│   ├── Listagem.jsx
│   └── Sobre.jsx
├── App.jsx
└── main.jsx
```

## 9. Diário de desenvolvimento

### Etapa 1 — Planejamento
**O que foi feito?**

> 

**Dúvidas ou dificuldades:**

> 

### Etapa 2 — Estrutura e componentes
**O que foi feito?**

> 

**Dúvidas ou dificuldades:**

> 

### Etapa 3 — Estado e formulários
**O que foi feito?**

> 

**Dúvidas ou dificuldades:**

> 

### Etapa 4 — API e navegação
**O que foi feito?**

> 

**Dúvidas ou dificuldades:**

> 

### Etapa 5 — Testes e finalização
**O que foi feito?**

> 

**Dúvidas ou dificuldades:**

> 

## 10. Espaço livre para código e observações

```jsx
// Cole aqui trechos importantes ou exemplos do projeto.
```

**Anotações:**

> 

---

# ✅ Checklist de desenvolvimento

## Aula 08 — Estrutura React

- [ ] Revisar os fundamentos de JavaScript necessários ao projeto.
- [ ] Criar a estrutura inicial da aplicação React.
- [ ] Construir a interface com JSX.
- [ ] Separar a interface em componentes.
- [ ] Utilizar props para passar dados.
- [ ] Renderizar listas com `map()`.
- [ ] Definir `key` estáveis nos itens.
- [ ] Utilizar filtros quando necessário.
- [ ] Implementar renderização condicional.

## Aula 09 — Interatividade e integração

- [ ] Criar estados com `useState`.
- [ ] Atualizar a interface por meio das funções de estado.
- [ ] Implementar formulários controlados.
- [ ] Tratar o envio com `onSubmit` e `preventDefault()`.
- [ ] Utilizar `useEffect` quando houver sincronização com sistemas externos.
- [ ] Consumir dados com `fetch`.
- [ ] Tratar erros e estados de carregamento.
- [ ] Configurar as rotas com React Router.
- [ ] Criar links de navegação.
- [ ] Utilizar parâmetros de rota quando necessário.

## Entrega

- [ ] Revisar a aplicação.
- [ ] Criar repositório público no GitHub.
- [ ] Escrever o README com descrição, funcionalidades e conceitos utilizados.
- [ ] Inserir o link do repositório neste documento.
- [ ] Publicar a aplicação, se fizer parte da entrega definida para o projeto.

---

# 🔗 Links complementares

Links indicados nos materiais das aulas:

| Recurso | Link |
|---|---|
| Conceitos React | https://github.com/deivisontakatu/aula-react |
| Exemplo de projeto | https://github.com/deivisontakatu/projeto-react |
| Aplicação de exemplo | https://projeto-react-five-swart.vercel.app/ |
| Revisão JavaScript (Aula 08) | https://github.com/deivisontakatu/aula-javascript |
| Atividade de revisão | https://wayground.com/ |
| Documentação React (exemplo citado na aula) | https://react.dev |

---

# 📝 Anotações pessoais

## O que aprendi na Aula 08?

> 

## O que aprendi na Aula 09?

> 

## Quais conceitos preciso revisar?

> 

## Quais dúvidas quero levar para a próxima aula?

> 

---

## 📚 Referência do material-base

- **Aula 08:** *Projeto React* — Frameworks Front-end, Prof. Me. Deivison S. Takatu.
- **Aula 09:** *Projeto React 02* — Frameworks Front-end, Prof. Me. Deivison S. Takatu.

*Documento organizado para estudo e acompanhamento do projeto. O conteúdo técnico foi estruturado com base nos tópicos, explicações e exemplos apresentados nos dois materiais.*
