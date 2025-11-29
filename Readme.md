# 🚴‍♂️ Sistema de Gerenciamento BiciCreta

Um sistema em C++ para gerenciamento de aluguel de bicicletas, clientes e funcionários. Desenvolvido como trabalho acadêmico, focado em manipulação de arquivos, structs e lógica de negócios.

## 📋 Funcionalidades

### 👥 Gerenciamento de Usuários

  * **Cadastro:** Adição de novos usuários com diferentes níveis de permissão (Administrador, Funcionário, Cliente).
  * **Edição:** Alteração de dados cadastrais (Nome, Idade, Email, Senha, Cargo e Status).
  * **Listagem:** Visualização de usuários ativos, inativos ou filtrados por cargo.
  * **Persistência:** Todos os dados são salvos em arquivo (`dadosCadastros.txt`).

### 🚲 Gerenciamento de Bicicletas

  * **Cadastro:** Registro de novas bicicletas com modelo e descrição.
  * **Controle de Aluguel:** Sistema para alugar bicicletas para clientes específicos e registrar devoluções.
  * **Status:** Controle de bicicletas disponíveis, alugadas ou em manutenção (inativas).
  * **Histórico:** Vínculo direto entre a bicicleta e o ID do cliente locatário.

-----

## 🛠️ Tecnologias Utilizadas

  * **Linguagem:** C++
  * **Armazenamento:** Arquivos de texto (`.txt`) com formatação customizada (`|` como separador).
  * **Compatibilidade:** Código híbrido compatível com **Linux** e **Windows** (funções de limpeza de tela e timer adaptadas).

-----

## 🚀 Como Compilar e Executar

### Execução Pré-Compilada
  * Existem executaveis static dentro do diretório `.\Executaveis` que podem ser executados no windows e linux
  * Basta executar os arquivos

### Pré-requisitos para compilar

  * Compilador C++ (G++ ou MinGW).
  * Terminal/Console.

### 🐧 No Linux (G++)

Para compilar o projeto gerando um executável estático (que roda em qualquer distribuição Linux):
(Uma pasta com o nome `Executaveis` deve existir na raiz do projeto)

```bash
g++ clientes.cpp bicicletas.cpp Menu.cpp  -o ./Executaveis/BiciCreta_Linux -static-libgcc -static-libstdc++
```

Para executar:

```bash
./Executaveis/BiciCreta_Linux
```

### 🪟 No Windows (MinGW)

Se você estiver compilando **do Linux para Windows** (Cross-compilation):
(Uma pasta com o nome `Executaveis` deve existir na raiz do projeto)

```bash
x86_64-w64-mingw32-g++ clientes.cpp bicicletas.cpp Menu.cpp -o ./Executaveis/BiciCreta_Win.exe -static
```

Se estiver compilando **diretamente no Windows**:
(Uma pasta com o nome `Executaveis` deve existir na raiz do projeto)

```cmd
g++ clientes.cpp bicicletas.cpp Menu.cpp -o ./Executaveis/BiciCreta.exe
```

-----

## 📂 Estrutura do Projeto

```text
.
├── Menu.cpp            # Arquivo principal (Main), menus e lógica de navegação.
├── clientes.cpp        # Funções CRUD de usuários e login.
├── bicicletas.cpp      # Funções CRUD de bicicletas e sistema de aluguel.
├── cadastros.h         # Arquivo de Cabeçalho (Structs, Constantes e Protótipos).
├── arquivos/           # Pasta onde os dados são salvos.
│   ├── dadosCadastros.txt
│   └── bicicletas.txt
├── Executaveis/        # Pasta onde os Executaveis são salvos.
│   ├── BiciCreta_Linux
│   └── BiciCreta_Win.exe
└── README.md           # Documentação do projeto.
```

## 📝 Formato dos Dados

O sistema utiliza arquivos de texto para persistência. É importante manter a integridade desses arquivos.

**Usuários (`dadosCadastros.txt`):**
`ID|Nome|Idade|Email|Cargo|Senha|Status`

  * *Cargo:* 0=Adm, 1=Func, 2=Cliente
  * *Status:* 1=Ativo, 0=Inativo

**Bicicletas (`bicicletas.txt`):**
`ID|Modelo|Descrição|ID_Locatário|Status`

  * *ID\_Locatário:* 0 se estiver livre, ID do cliente se estiver alugada.

-----

## 👨‍💻 Autor

**EidenFox**

  * [EidenFox](https://github.com/EidenFox)

-----

*Projeto desenvolvido para a disciplina de Startup Model Advanced - SENAC Paraná.*