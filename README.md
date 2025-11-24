# 🍔 MenuExpress

**MenuExpress** é um aplicativo Android nativo para cardápio digital e pedidos de delivery. O projeto consiste em um aplicativo mobile (Kotlin) que consome uma API RESTful (Node.js) para autenticação de usuários, listagem de produtos e gerenciamento de carrinho de compras em tempo real.

## 📱 Telas e Funcionalidades

* **Splash Screen:** Tela de carregamento inicial com a logo.
* **Autenticação:**
    * Login de usuários.
    * Cadastro de novos usuários.
* **Cardápio (Home):** Listagem de produtos com imagens carregadas via URL.
* **Detalhes do Produto:** Visualização ampliada do produto com descrição e preço.
* **Carrinho de Compras:**
    * Adicionar itens.
    * Listar itens selecionados.
    * **Remover itens individualmente** (Funcionalidade de exclusão).
    * **Finalizar Pedido** (Limpa o carrinho simulando uma compra).
* **Botão Flutuante (FAB):** Acesso rápido ao carrinho na tela principal.

## 🛠 Tecnologias Utilizadas

### Mobile (Android)
* **Linguagem:** Kotlin
* **Arquitetura:** MVC (Model-View-Controller)
* **Comunicação HTTP:** Retrofit 2 & Gson
* **Carregamento de Imagens:** Glide
* **Layout:** XML (ConstraintLayout, RelativeLayout, LinearLayout)
* **Componentes:** RecyclerView, FloatingActionButton, CardView
* **Build System:** Gradle

### Back-End (API)
* **Runtime:** Node.js
* **Framework:** Express.js
* **Banco de Dados:** JSON Files (Simulação de banco de dados NoSQL usando sistema de arquivos `fs`)
* **Imagens:** Servidor de arquivos estáticos (`/assets`)

## 📂 Estrutura do Projeto

O projeto é dividido em duas partes principais:

1.  **Android App:** O código fonte do aplicativo.
2.  **Backend:** A pasta `menu-express-backend` contendo o servidor e os arquivos JSON.

## 🚀 Como Rodar o Projeto

Para executar este projeto em sua máquina local, siga os passos abaixo:

### Pré-requisitos
* Android Studio instalado.
* Node.js instalado.
* Celular Android ou Emulador configurado.

### Passo 1: Configurar o Back-End

1.  Navegue até a pasta do servidor:
    ```bash
    cd menu-express-backend
    ```
2.  Instale as dependências (Express, Cors, etc):
    ```bash
    npm install
    ```
3.  Descubra o seu endereço IP local (IPv4):
    * Windows: Digite `ipconfig` no terminal.
    * Linux/Mac: Digite `ifconfig`.
4.  Abra o arquivo `data/foods.json` e atualize as URLs das imagens com o seu IP:
    * Exemplo: `"image": "http://192.168.X.X:3000/assets/1.jpg"`
5.  Inicie o servidor:
    ```bash
    npm start
    ```
    *O servidor rodará na porta 3000.*

### Passo 2: Configurar o App Android

1.  Abra o projeto no **Android Studio**.
2.  Vá até o arquivo `network/ApiClient.kt`.
3.  Atualize a constante `BASE_URL` com o mesmo IP que você usou no passo anterior:
    ```kotlin
    private const val BASE_URL = "[http://192.168.](http://192.168.)X.X:3000/"
    ```
4.  Sincronize o projeto com o Gradle (**File > Sync Project with Gradle Files**).
5.  Execute o app em seu emulador ou dispositivo físico (**Run 'app'**).

## 🔌 Endpoints da API

A API roda localmente e disponibiliza as seguintes rotas:

| Método | Rota | Descrição |
| :--- | :--- | :--- |
| `GET` | `/foods` | Retorna a lista completa do cardápio. |
| `POST` | `/login` | Autentica um usuário existente. |
| `POST` | `/register` | Cadastra um novo usuário. |
| `GET` | `/cart/:email` | Retorna os itens do carrinho de um usuário. |
| `POST` | `/cart/add` | Adiciona um item ao carrinho. |
| `POST` | `/cart/remove` | Remove um item específico do carrinho. |
| `POST` | `/cart/clear` | Limpa todo o carrinho (Finalizar Pedido). |

## 📸 Imagens do Projeto

*(Aqui você pode adicionar prints da tela do seu app funcionando)*

---
Desenvolvido por **Henrico Justino**
