# MenuExpress

**MenuExpress** é um aplicativo Android nativo para cardápio digital e pedidos de delivery. O projeto consiste em um aplicativo mobile (Kotlin) que consome uma API RESTful (Node.js) para autenticação de usuários, listagem de produtos e gerenciamento de carrinho de compras em tempo real.

## Telas e Funcionalidades

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

## Tecnologias Utilizadas

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

## Estrutura do Projeto

O projeto é dividido em duas partes principais:

1.  **Android App:** O código fonte do aplicativo.
2.  **Backend:** A pasta `menu-express-backend` contendo o servidor e os arquivos JSON.

## Como Rodar o Projeto

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

## Endpoints da API

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

## Imagens do Projeto

<img width="108" height="240" alt="Screenshot_20251124_020937" src="https://github.com/user-attachments/assets/0fbff9cf-a074-4d3c-939a-4f142c356da9" />
<img width="108" height="240" alt="Screenshot_20251124_021019" src="https://github.com/user-attachments/assets/bb8599ab-42c9-4692-ab72-52d18443fbbf" />
<img width="108" height="240" alt="Screenshot_20251124_021036" src="https://github.com/user-attachments/assets/f8ce2b4e-b204-40d6-ba93-5e8300c09eb6" />
<img width="108" height="240" alt="Screenshot_20251124_022220" src="https://github.com/user-attachments/assets/924496d0-ff39-48c8-9840-398aacf560d2" />
<img width="108" height="240" alt="Screenshot_20251124_021825" src="https://github.com/user-attachments/assets/e4824878-3b03-479f-b325-24a333e0dcd1" />
<img width="108" height="240" alt="Screenshot_20251124_021938" src="https://github.com/user-attachments/assets/bd545f58-0c5b-4cae-b2c0-a9927c024217" />
<img width="108" height="240" alt="Screenshot_20251124_022022" src="https://github.com/user-attachments/assets/ded4f2be-7f95-40e0-a6c2-c1a965df6d88" />
<img width="108" height="240" alt="Screenshot_20251124_022143" src="https://github.com/user-attachments/assets/52ddcf21-79d1-42c9-9af4-b992e3d75080" />


---
Desenvolvido por **Henrico Justino**
