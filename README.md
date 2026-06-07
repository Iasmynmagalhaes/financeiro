# Sintonia Financeira 💑💰

Um aplicativo web moderno e responsivo de controle financeiro desenvolvido para facilitar a gestão do dia a dia de casais. O **Sintonia Financeira** permite registrar receitas, despesas e investimentos de forma colaborativa, com sincronização em nuvem, painéis visuais e um sistema inteligente de acerto de contas.

A versão atual da aplicação funciona como um serviço real (SaaS): possui **Autenticação Segura** e **Isolamento de Dados**, permitindo que múltiplos casais utilizem o aplicativo, cada um com seu próprio banco de dados privado.

## ✨ Funcionalidades

* 🔐 **Autenticação Segura:** Sistema de login e cadastro integrado (E-mail e Senha) garantindo que apenas usuários autorizados acessem as planilhas.
* 🛡️ **Privacidade de Dados (Multi-Tenant):** Cada conta criada possui seu próprio banco de dados isolado. É impossível que um usuário acesse os dados financeiros de outro.
* ☁️ **Sincronização em Tempo Real:** Integração nativa com o Firebase Firestore. Lançamentos feitos por um parceiro aparecem instantaneamente na tela do outro.
* 📊 **Dashboard Interativo:** Gráficos dinâmicos que detalham as despesas por categoria e mostram quem gastou mais no mês.
* 🧮 **Calculadora de Acerto de Contas:** Sistema automático que soma as contas compartilhadas (marcadas como "Ambos") e exibe a cota ideal (50/50) para um fechamento de mês justo.
* 🏷️ **Gestão de Categorias:** Controle total para criar ou excluir categorias de despesas, receitas e investimentos nas configurações.

## 🛠️ Tecnologias Utilizadas

* **Estrutura e Lógica:** HTML5 e JavaScript (Vanilla).
* **Estilização:** [Tailwind CSS](https://tailwindcss.com/) (via CDN).
* **Gráficos:** [Chart.js](https://www.chartjs.org/) (via CDN).
* **Backend as a Service (BaaS):** 
  * [Firebase Authentication](https://firebase.google.com/docs/auth) (Gerenciamento de usuários).
  * [Firebase Cloud Firestore](https://firebase.google.com/docs/firestore) (Banco de dados em tempo real).

## 🚀 Como Acessar e Hospedar

A aplicação é *Serverless* (sem servidor) e consiste em um arquivo único `index.html`. 

* **Hospedagem Online Gratuita:** Recomendado hospedar via [GitHub Pages](https://pages.github.com/) ou [Netlify](https://www.netlify.com/) para acesso rápido via celular ou computador.

## ⚙️ Estrutura de Configuração (Firebase)

Caso faça um *Fork* deste repositório para criar o seu próprio ambiente, siga os passos abaixo para configurar o backend:

1. Crie um projeto gratuito no [Console do Firebase](https://console.firebase.google.com/).
2. Vá em **Authentication**, ative o método de login **E-mail/senha** e cadastre o seu primeiro usuário.
3. Vá em **Firestore Database** e crie um banco de dados em modo de teste.
4. Substitua as credenciais (`firebaseConfig`) no final do arquivo `index.html` com as chaves do seu projeto.
5. **Segurança Final:** No Firestore, vá na aba de "Regras" (Rules) e aplique o código abaixo para garantir que os dados fiquem 100% privados por usuário:

```javascript
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /contas_usuarios/{userId} {
      allow read, write: if request.auth != null && request.auth.uid == userId;
    }
  }
}
