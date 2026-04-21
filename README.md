# Test de Perfomance da Api do Banco com K6

Repositório com teste de performance automaziados desenvolvidos com uma ferramneta [Grafana K6] (https://k6.io/)
e escritos em JavaScript, voltados para a API do sistema Bancário.

Repositório: [github.com/araujodutra/banco-api-performance.git
banco-api-performance] (https://github.com/araujodutra/banco-api-performance.git
 banco-api-performance) 
---

## 📌 Introdução
Este projeto tem como objetivo realizar **testes de performance** em uma API bancária, garantindo que os serviços suportem cargas simultâneas e mantenham estabilidade, tempo de resposta adequado e confiabilidade.

Os testes são desenvolvidos utilizando o **k6**, uma ferramenta moderna e eficiente para testes de carga, com scripts escritos em **JavaScript**.

---

## 🛠 Tecnologias Utilizadas
- **JavaScript **
- **k6** – Ferramenta para testes de carga e performance
- **Node.js** (opcional, para suporte e organização do projeto)
``

## 📁 Estrutura do Repositório
```
banco-api-performance/
│
├── fixtures/            # Dados de entrada para os testes (ex: usuários, payloads)
├── helpers/             # Funções utilitárias reutilizadas para interação com a API
├── tests/               # Casos de teste organizados por módulo da API
├── config/              # Arquivo de configuração de váriaveis de ambiente
├── utils/               # Funções utilitárias reutilizadas
├── package.json         # Dependências do projeto
└── README.md            # Documentação do projeto
```

---

## 🎯 Objetivo de Cada Grupo de Arquivos

- **fixturess/**  
  Dados de entrada para os testes (ex: usuários, payloads)
- **helpers/**  
  Funções utilitárias reutilizadas para interação com a API
  **tests/**
  Casos de teste organizados por módulo da API
  **utils/**  
  Funções reutilizáveis, 
- **config/**  
  Arquivo de configuração de váriaveis de ambiente

---

## ⚙️ Instalação e Execução

### 1. Clonar o repositório
```bash
git clone https://github.com/araujodutra/banco-api-performance.git
 banco-api-performance
```

### 2. Configurar variável de ambiente


Altere o arquivo 'config/config.local.json' e defina a URL base da API a ser testada.
```. jso
{
    "baseUrl": "http://localhost:3000"
}
```
Essas variáveis serão usadas dinamicamente nos testes para montar as requisições.

## 3 ▶️ Execute um teste


```bash
k6 run tests/login.test.js
```
Certifique-se de passar a variável de ambiente`BASE_URL`, caso não esteja usando 
`config.local.json`ou uma aborg=dagem de carregaento automático:

```bash
k6 run tests/autenticacao/login.test.js -e
BASE_URL=http://localhost:3000
```

### 4. Acompanhamento em tempo Real Relatótio
````bash
K6_WEB_DASHBOARD=true \
K6_WEB_DASHBOARD_EXPORT=html-report.html\
k6 run tests/autenticacao/login.test.js \
-e BASE_URL=http://localhost:3000 
````
Após a execução, o relatório estará salvo como 
`html-report.html`.

### 💡 Observações importantes
- A variável `BASE_URL` é obrigatória para execução dos testes.
- O dashboard do k6 será exibido automaticamente no navegador durante a execução.
- Ao final do teste, será gerado um arquivo:
  ```
  html-report.html
  ```
  contendo o relatório completo da execução.
