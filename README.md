# 🃏 Consumo de APIs com JavaScript

> Atividade prática de desenvolvimento web: construção de uma interface que consome uma API externa de forma assíncrona.

---

## 🎯 Objetivo

Desenvolver uma interface web que consuma uma API externa de forma assíncrona, aplicando conceitos de **manipulação do DOM** e **requisições HTTP** (Fetch API).

---

## 📋 Requisitos Técnicos

| # | Requisito | Descrição |
|---|-----------|-----------|
| 1 | **Frontend** | Implementação utilizando HTML5 e CSS3, valorizando boas práticas de design e responsividade. |
| 2 | **JavaScript** | Utilização de ES6+ (`Promises`, `async/await`) para realizar o consumo da API. |
| 3 | **Funcionalidade** | Ao interagir com um botão, a interface deve realizar uma requisição à API e renderizar dinamicamente o conteúdo na tela. |
| 4 | **Tratamento de Erros** | Implementação de mecanismos básicos para tratar falhas de rede ou erros na requisição (`try/catch`). |

---

## 🔌 API de Referência

**Endpoint:**

```
https://official-joke-api.appspot.com/random_joke
```

**Exemplo de resposta:**

```json
{
  "type": "general",
  "setup": "Why did the chicken cross the road?",
  "punchline": "To get to the other side.",
  "id": 42
}
```

**Exemplo de consumo com `async/await`:**

```js
const API_URL = "https://official-joke-api.appspot.com/random_joke";

async function buscarPiada() {
  try {
    const resposta = await fetch(API_URL);

    if (!resposta.ok) {
      throw new Error(`Erro na requisição: ${resposta.status}`);
    }

    const piada = await resposta.json();
    renderizarPiada(piada);
  } catch (erro) {
    console.error(erro);
    exibirMensagemDeErro("Não foi possível carregar a piada. Tente novamente.");
  }
}
```

---

## 📁 Estrutura do Projeto

```
.
├── index.html      # Estrutura da página
├── style.css       # Estilos e responsividade
├── script.js       # Consumo da API e manipulação do DOM
└── README.md
```

---

## ▶️ Como Executar

1. Clone ou baixe este repositório.
2. Abra o arquivo `index.html` no navegador.
3. Clique no botão para carregar uma nova piada.

> 💡 Alternativa: rode um servidor local com `npx serve .` ou pela extensão *Live Server* do VS Code.

---

## ✅ Checklist de Entrega

- [ ] HTML5 semântico
- [ ] CSS3 com layout responsivo
- [ ] Requisição assíncrona com `fetch` + `async/await`
- [ ] Renderização dinâmica no DOM
- [ ] Tratamento de erros com `try/catch`

---

## 👤 Autor

**Hendrick** — UFRR
