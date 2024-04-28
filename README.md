# Tutilabs 🚀

### 📄 Documentação

Este teste foi desenvolvido como parte do processo seletivo para a Tutilabs. Consiste em uma aplicação web com funcionalidades específicas e regras a serem seguidas. 


<details>
<summary><strong>Instalação 🛠️</strong></summary>

### 🛠️ Instalação 
Para rodar o projeto, primeiro clone este repositório usando o comando:

```
git clone https://github.com/seu-usuario/nome-do-projeto.git
```
Em seguida, instale as dependências usando o gerenciador de pacotes de sua escolha. Recomendo o uso do npm:
  
```
npm install
```

Logo após, execute o projeto localmente:

```
npm run serve
```

ou construa a imagem com Docker:

```
docker build -t tutilabs-app .
```

e execute o container:

```
 docker run -p 8080:8080 -d tutilabs-app
```
      
</details>

<details>
<summary><strong>Tecnologias Utilizadas 🔧</strong></summary>
    
### 🔧 Tecnologias

- Vue.js
- Typescript
- Visual Studio Code
- Git e GitHub

O projeto foi desenvolvido com a biblioteca Vue.js. Para o desenvolvimento, utilizei o Visual Studio Code como IDE e o Git para controle de versão e o GitHub como repositório remoto.
</details>

<details>
<summary><strong>Funcionalidades 🎯</strong></summary>

### 🎯 Funcionalidades

-  **Sorria e Acene:** Ícone de mão com animação infinita de acenar.
-  **Morpheus Pills:** Filtros front-end e back-end, com front-end selecionado por padrão.
-  **Olho de Sauron:** Visualização das tecnologias utilizadas em Tutilabs ao clicar nos filtros.
-  **Coração de Mãe:** Navegação lateral de três em três elementos da lista de stacks.
-  **Sherlock Holmes:** Exibição de informações ao clicar em uma tecnologia.

</details>

<details>
<summary><strong>Estrutura do Projeto 📂</strong></summary>

A estrutura do projeto é <u>organizada</u> da seguinte maneira:

  - `public/`: contém arquivos estáticos acessíveis publicamente.

- `src/`:  contém todo o código-fonte da aplicação.

  - `assets/`  - contém os recursos estáticos da aplicação.
    - `images/` - contém imagens utilizadas na aplicação.

  - `components/` - contém os componentes da aplicação.
    - `Header.vue` - contém o componente que é exibe a logo da Tutilabs e o criador do protótipo.
    - `Navbar.vue` - contém o componente de Apresentação do Teste.
    - `StackBox.vue` - contém o componente de ferramentadas usadas na Tutilabs.

  `App.vue` - arquivo principal que renderiza a aplicação.

  `main.ts` - arquivo que inicializa a aplicação.

</details>

