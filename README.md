# 📚 Projeto 05 – Desenvolvimento Web III: Calculadora de Média com Node.js Nativo

Aplicação web desenvolvida utilizando **Node.js sem frameworks** (usando módulos nativos como `http`, `url` e `fs`), capaz de receber as notas $P_1$ e $P_2$ através de parâmetros na URL (*query strings*), processar a média final e renderizar páginas HTML dinâmicas com base na situação do aluno (**Aprovado** ou **Reprovado**).

---

## 📌 Sumário
- [Funcionalidades](#-funcionalidades)
- [Regras de Negócio](#-regras-de-negócio)
- [Estrutura do Projeto](#-estrutura-do-projeto)
- [Pré-requisitos](#-pré-requisitos)
- [Como Executar o Projeto](#-como-executar-o-projeto)
- [Exemplos de Uso](#-exemplos-de-uso)
- [Tratamento de Erros](#-tratamento-de-erros)
- [Autores](#-autores)

---

## ✨ Funcionalidades
- Recebimento de notas $P_1$ e $P_2$ via query string (`/media?p1=X&p2=Y`).
- Cálculo da média aritmética simples.
- Renderização dinâmica dos arquivos HTML em `public/`:
  - `aprovado.html` para média maior ou igual a 6.0.
  - `reprovado.html` para média menor que 6.0.
- Exibição de $P_1$, $P_2$, Média Final e Situação diretamente na interface HTML.
- Tratamento para parâmetros ausentes, entradas inválidas (textos ou números fora do escopo) e rotas/páginas inexistentes (Erro 404).

---

## 📏 Regras de Negócio

$$\text{Média} = \frac{P_1 + P_2}{2}$$

| Média Final | Situação | Página Retornada |
| :--- | :--- | :--- |
| $\ge 6.0$ | **APROVADO** | `public/aprovado.html` |
| $< 6.0$ | **REPROVADO** | `public/reprovado.html` |

---

## 📁 Estrutura do Projeto

```text
.
├── public/
│   ├── aprovado.html     # Layout exibido quando o aluno é aprovado
│   └── reprovado.html    # Layout exibido quando o aluno é reprovado
├── app.js                # Servidor Node.js nativo e tratamento das rotas
├── package.json          # Configurações do projeto e scripts
├── package-lock.json     # Mapeamento de dependências
└── README.md             # Documentação do repositório
