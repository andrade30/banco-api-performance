# Testes de Performance - Banco API

## 📌 Introdução

Este repositório contém testes de **performance e carga** desenvolvidos com **JavaScript** utilizando a ferramenta **k6**, com o objetivo de validar o comportamento, a estabilidade e o desempenho das APIs do projeto Banco sob diferentes cenários de uso.

Os testes simulam múltiplos usuários e volumes de requisições, permitindo identificar gargalos, limites de capacidade e possíveis pontos de melhoria antes da aplicação chegar a produção.

---

## 🛠 Tecnologias Utilizadas

- k6 – Ferramenta de testes de performance
- JavaScript (ES6+)
- Node.js
- Git / GitHub

---

## 📂 Estrutura do Repositório

banco-api-performance/
├── tests/
│   ├── login.test.js
│   ├── transferencias.test.js
│   └── ...
├── helpers/
│   ├── Funções utilitárias reutilizáveis para a interação com a API
│   ├── ...
├── utils/
│   ├── Funções utilitárias reutilizáveis
│   ├── ...
├── fixtures/
│   └── Dados de entrada para testes ex:payloads.json
├── config/
│   └── Arquivo de configuração de variáveis de ambiente
├── README.md

---

## 📁 Objetivo de Cada Grupo de Arquivos

### tests/
Contém os scripts principais de teste, cada arquivo representa um cenário ou funcionalidade da API.

### helpers/
Funções utilitárias reutilizáveis para a interação com a API

### utils/
Funções utilitárias reutilizáveis

### fixtures/
Dados estáticos e massas de teste.

### config/
Configurações globais dos testes.

---

## 🎯 Objetivo do Projeto

- Validar performance das APIs
- Identificar gargalos
- Simular cenários reais
- Gerar relatórios técnicos

---

## ⚙️ Instalação e Execução

### Pré-requisitos
- Node.js
- k6

### Clonar o repositório
git clone https://github.com/andrade30/banco-api-performance.git

### Variável de ambiente obrigatória
{
    "baseUrl": "http://localhost:3000"
}

### Execução simples
k6 run tests/login.test.js

Certifique-se de passar a variável de ambiente `BASE_URL`, caso não esteja usando um `config.local.json` ou uma abordagem de carregamento automático:

```bash
k6 run tests/autenticacao/login.test.js -e BASE_URL=http://localhost:3000
```

### Execução com dashboard e exportação de relatório
K6_WEB_DASHBOARD=true 
K6_WEB_DASHBOARD_EXPORT=html-report.html 
k6 run tests/login.test.js
-e BASE_URL=http://localhost:3000

Após a execução, o relatório estará salvo como `html-report.html`.
