🧾 Divisor de Contas (v2.1)

Um aplicativo multiplataforma, desenvolvido com **Flutter**, para gerenciar e dividir despesas compartilhadas com amigos. O aplicativo utiliza o **Firebase** para autenticação de usuários e armazenamento de dados em tempo real no **Cloud Firestore**.

---

## Contribuições

Este projeto foi desenvolvido em equipe e contou com a colaboração de:

* **Gabryel Kopp**
* **Murilo**
* **Nicolas Crisostimo**

Sobre a divisão de tarefas, **Murilo** ficou responsável mais pela arquitetura inicial e pela implementação das telas de Autenticação (Login e Cadastro), garantindo a base segura para o aplicativo.  
**Gabryel** e **Nicolas** ficaram responsáveis por desenvolver as demais telas e funcionalidades principais do aplicativo, incluindo a gestão de dívidas, o lançamento de despesas, a visualização dos gráficos de análise e a gestão de categorias.  
Porém, durante todo o processo, todos os membros da equipe contribuíram de alguma forma e acompanharam o desenvolvimento para garantir que fosse algo que todos aprovassem.

---

## Histórico de Versões

**v1.0 (Entrega 1):**
* Versão inicial do projeto.
* Armazenamento de dados local (offline) usando arquivos CSV.
* Funcionalidades de CRUD de Dívidas e Despesas.
* Tela de gráficos (pizza e barras) com dados locais.
* Sistema de autenticação local (login/cadastro) baseado em CSV.

**v2.0 (Entrega 2):**
* **Migração completa para o Firebase:**
  * Substituição do sistema de autenticação local pelo Firebase Authentication.
  * Substituição do armazenamento CSV pelo Cloud Firestore, garantindo dados em tempo real.
* **CRUD de Usuário e Perfil:**
  * Adição da Tela de Perfil.
  * Funcionalidade para alterar nome de usuário (atualizando em todas as dívidas).
  * Funcionalidade para alterar senha (com reautenticação de segurança).
  * Funcionalidade para excluir a conta (com reautenticação).
* **Gerenciamento de Tema:**
  * Adição do serviço de tema (ThemeService) com Provider.
  * O usuário pode escolher entre os modos Claro, Escuro ou Padrão do Sistema.
  * A escolha do tema é salva localmente no dispositivo (SharedPreferences).

**v2.1 (Polimento):**
* Integração total do sistema de temas com a Tela de Gráficos (Análise).
* Os textos dos eixos, legendas e as cores das barras agora se adaptam ao tema claro/escuro, garantindo legibilidade.
* Correção de bugs de layout (Right Overflow) na tela de detalhes da dívida.

---

## ✨ Funcionalidades (v2.1)

* **Autenticação com Firebase:** Sistema completo de login, cadastro, alteração de senha e exclusão de conta usando Firebase Authentication.  
* **Banco de Dados em Nuvem (Firestore):** Dados de usuários, dívidas e despesas salvos no Cloud Firestore com sincronização em tempo real.  
* **CRUD de Perfil:** O usuário pode alterar seu nome (que atualiza em todas as dívidas) e sua senha.  
* **Gestão de Tema:** Escolha entre os modos Claro, Escuro e Padrão do Sistema.  
* **Gestão de Dívidas:** Crie dívidas compartilhadas entre você e um amigo (buscando pelo e-mail).  
* **Cálculo de Saldo Automático:** O saldo da dívida é recalculado no Firestore a cada nova despesa e exibido em tempo real na tela principal.  
* **Visualização com Gráficos:** Analise gastos com gráficos de pizza (por categoria) e barras (por mês), totalmente adaptados ao tema do app.  
* **Gestão de Categorias:** Crie e personalize categorias para organizar suas despesas.  
* **Exclusão de Dados:** Remova despesas individuais (arrastando para o lado) ou dívidas inteiras (com diálogo de confirmação).  

---

## 🚀 Tecnologias e Pacotes

* **Flutter & Dart**
* **firebase_core:** Para inicializar o Firebase.  
* **firebase_auth:** Para gerenciar a autenticação de usuários.  
* **cloud_firestore:** Para o banco de dados NoSQL em nuvem.  
* **provider:** Para gerenciamento de estado (especificamente o ThemeService).  
* **shared_preferences:** Para salvar a preferência de tema do usuário.  
* **fl_chart:** Para a criação dos gráficos.  
* **intl:** Para formatação de datas e valores monetários.  

---

## 🏗️ Estrutura do Projeto

O projeto segue uma arquitetura de camadas inspirada no padrão **MVVM (Model-View-ViewModel)**, com uma clara separação de responsabilidades:

* `/lib/models`: Contém as classes de dados (`User`, `Debt`, `Expense`) com métodos `toMap()` e `fromMap()` para serialização no Firestore.  
* `/lib/services`: Contém a lógica de negócios e o gerenciamento de estado (`AuthService`, `DataService`, `ThemeService`). É o cérebro da aplicação.  
* `/lib/screens`: Contém os widgets que compõem a interface do usuário (UI).  

---

## ⚙️ Como Executar o Projeto

Siga os passos abaixo para executar o projeto em sua máquina local.

**Pré-requisitos:**
* SDK do Flutter instalado.  
* Uma conta do Firebase.  
* As Ferramentas de CLI do Firebase:  
  ```bash
  npm install -g firebase-tools
  dart pub global activate flutterfire_cli


**Passos:**

1.  Clone o repositório:
    ```bash
    git clone [https://github.com/NicolasCrisostimo/Bill_Splitter_App.git]
    ```

2.  Acesse a pasta do projeto:
    ```bash
    cd nome-do-repositorio
    ```

3.  Configure o Firebase (Passo Crítico):
   - Crie um projeto no Console do Firebase.
   - Ative os seguintes serviços:
   - Authentication (método de login: E-mail/Senha)
   - Cloud Firestore (inicie em "Modo de Teste")
   - No terminal, execute
``` bash
    cd nome-do-repositorio
```

4. Instale as dependências:

``` bash
    flutter pub get
```


5. Execute o aplicativo:

``` bash
    flutter run
```


---

## Telas

* Tela de Login
* Tela de Cadastro
* Tela Principal
* Tela de Detalhes da Dívida
* Tela de Gráficos
* Tela de Perfil v(2.0)

---

## Melhorias Futuras

* Implementar regras de segurança no Firestore para proteger os dados.
* Adicionar funcionalidade de recuperação de senha.
* Permitir o upload de foto de perfil (usando Firebase Storage).
* Permitir a divisão de despesas em grupos com mais de duas pessoas.
* Implementar notificações push (via Firebase Messaging) para avisar sobre novas despesas.
