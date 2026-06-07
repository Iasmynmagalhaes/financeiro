# Sintonia Financeira 💑💰

Um aplicativo web de controle financeiro desenvolvido para a gestão do dia a dia do casal. O **Sintonia Financeira** permite registrar receitas, despesas e investimentos de forma colaborativa, facilitando o acompanhamento do orçamento familiar e o acerto de contas com sincronização em nuvem e em tempo real.

## ✨ Funcionalidades

* **Sincronização em Tempo Real:** Integração nativa com Firebase Firestore. Qualquer lançamento ou edição feita aparece instantaneamente em ambos os dispositivos.
* **Dashboard Interativo:** Gráficos dinâmicos e visuais que detalham as despesas por categoria e a proporção de gastos de cada responsável.
* **Calculadora de Acerto de Contas:** Sistema automático que soma o total de contas compartilhadas e exibe a cota ideal (50/50) para um fechamento de mês justo.
* **Gestão de Categorias Personalizadas:** Adição e exclusão flexível de categorias para despesas, receitas e investimentos diretamente pela aba de configurações.
* **Extrato Completo:** Histórico de transações detalhado com filtros por tipo de fluxo e interface rápida para remoção de registros.
* **Design Responsivo e Moderno:** Interface com estilo de aplicativo nativo (mobile-first), garantindo uma experiência fluida tanto em smartphones quanto em computadores.

## 🛠️ Tecnologias Utilizadas

* **Estrutura e Lógica:** HTML5 e JavaScript (Vanilla).
* **Estilização:** [Tailwind CSS](https://tailwindcss.com/) (via CDN).
* **Gráficos:** [Chart.js](https://www.chartjs.org/) (via CDN).
* **Banco de Dados:** [Firebase Cloud Firestore](https://firebase.google.com/products/firestore) (Sincronização em nuvem).

## 🚀 Como Acessar e Hospedar

Como a aplicação é estruturada em um modelo *Serverless* (sem servidor) e em arquivo único, a execução é extremamente rápida:

1. **Uso Local:** Basta baixar o repositório e abrir o arquivo `index.html` em qualquer navegador de internet.
2. **Hospedagem Online Gratuita:** Pode ser hospedado em questão de minutos de forma pública e estável utilizando o [GitHub Pages](https://pages.github.com/) (diretamente nas configurações deste repositório) ou serviços como o [Netlify](https://www.netlify.com/).

## ⚙️ Estrutura de Configuração do Banco de Dados

Este projeto já está apontado para um projeto Firebase ativo. Caso o código seja clonado (Fork) para a criação de um novo ambiente isolado, é necessário substituir as chaves do banco:

1. Crie um projeto gratuito no console do Firebase.
2. Ative o banco de dados **Firestore** no painel lateral.
3. Nas configurações do projeto, registre um App Web e copie as chaves geradas (`firebaseConfig`).
4. Substitua o objeto de configuração nas linhas finais do script no arquivo `index.html`.

---
Desenvolvido com ❤️ por Iasmyn e Mateus.
