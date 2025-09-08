# 💸 Controle Financeiro Pessoal em C++ 💸

[![C++](https://img.shields.io/badge/language-C++-blue.svg)](https://isocpp.org/)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)
[![Status](https://img.shields.io/badge/status-em%20desenvolvimento-yellow.svg)]()

---

## 📑 Índice
- [Sobre o Projeto](#-sobre-o-projeto)
- [Funcionalidades Principais](#-funcionalidades-principais)
- [Tecnologias Utilizadas](#-tecnologias-utilizadas)
- [Como Executar o Projeto](#-como-executar-o-projeto)
- [Categorias de Despesas](#-categorias-de-despesas)
- [Telas da Aplicação](#-telas-da-aplicação)
- [Autor](#-autor)

---

## 🎯 Sobre o Projeto
Este é um sistema de **Controle Financeiro Pessoal** robusto e intuitivo, desenvolvido inteiramente em **C++**.  

Através de uma interface de console limpa e direta, o sistema permite que você **cadastre, visualize, filtre e remova suas despesas**, tudo de forma organizada.  

📌 As despesas são salvas em arquivo (`despesas.txt`), garantindo **persistência dos dados** entre usos.  

O projeto foi estruturado com **Programação Orientada a Objetos (POO)**, utilizando classes bem definidas (`Despesa` e `ControleFinanceiro`) que tornam o código **limpo, organizado e de fácil manutenção**.

---

## ✨ Funcionalidades Principais
- 🖋️ **Adicionar Despesas**: Informe descrição, valor, data e categoria.
- 📋 **Listar Todas as Despesas**: Visualização detalhada de todos os registros.
- 🗑️ **Remover Despesas**: Exclua facilmente uma despesa específica.
- 💰 **Calcular Gasto Total**: Veja quanto já foi gasto em todas as despesas.
- 🔍 **Filtrar por Categoria**: Visualize gastos em categorias específicas (como "Alimentação", "Lazer", etc.).
- 📅 **Filtrar por Mês e Ano**: Descubra quanto gastou em períodos específicos.
- 💾 **Persistência de Dados**: Dados salvos automaticamente no `despesas.txt`.
- 🖥️ **Interface de Console Limpa**: Com limpeza de tela após cada operação para melhor experiência.

---

## 🛠️ Tecnologias Utilizadas
- **C++** → Linguagem principal
- **POO (Programação Orientada a Objetos)** → Estrutura modular e organizada
- **Manipulação de Arquivos (fstream)** → Persistência de dados
- **Biblioteca Padrão do C++** → `iostream`, `vector`, `string`, `sstream`, `iomanip`

---

## 🚀 Como Executar o Projeto

### 1️⃣ Clone o repositório
```bash
git clone https://github.com/JoaoGuilhermmy/Controle-de-gastos_C-.git
``` 

### 2️⃣ Acesse a pasta do projeto
```bash
cd Controle-de-gastos_C-
```

### 3️⃣ Compile o código
```bash
g++ main.cpp Controle.cpp Despesas.cpp -o ControleFinanceiro.exe
```

### 4️⃣ Execute o programa
```bash
Linux:
./ControleFinanceiro.exe
```

```bash
Windows:
ControleFinanceiro.exe
```

### 📂 Categorias de Despesas
| Código | Categoria         |
| ------ | ----------------- |
| 1      | Alimentação       |
| 2      | Locomoção         |
| 3      | Educação          |
| 4      | Lazer             |
| 5      | Saúde             |
| 6      | Contas e Serviços |
| 7      | Outros            |

### 📸 Telas da Aplicação
```
-------------- Controle Financeiro --------------
Escolha uma opção:
1 - Adicionar despesa
2 - Listar despesas
3 - Calcular total de despesas
4 - Remover despesa
5 - Mostrar despesas com filtro
6 - Filtrar por mês
7 - Sair
Digite sua opção:
``` 
### Adicionando uma Despesa
```
-------------- Cadastro da Despesa --------------
Digite a descrição da despesa: Jantar com amigos
Digite o valor da despesa: 150.75
Digite a data da despesa: (dd/mm/aaaa): 07/09/2025
Escolha qual categoria sua despesa se encaixa:
1 - Alimentação
2 - Locomoção
3 - Educação
4 - Lazer
5 - Saúde
6 - Contas e Serviços
7 - Outros
```
### Listando Despesas
```
-----------------------------------------------------
         ***Lista de Despesas***
-----------------------------------------------------
Descrição: Almoco    | Valor: R$25.50 | Data: 05/09/2025 | Categoria: Alimentação
Descrição: Uber      | Valor: R$15.00 | Data: 06/09/2025 | Categoria: Locomoção

Ou em formato de tabela:

```markdown
| Descrição |   Valor  | Data       | Categoria   |
| --------- | -------: | ---------- | ----------- |
| Almoço    | R$ 25.50 | 05/09/2025 | Alimentação |
| Uber      | R$ 15.00 | 06/09/2025 | Locomoção   |
```

### ⚡ O projeto já está funcional e concluído, mas novas ideias e sugestões de melhorias são sempre bem-vindas!

## 👨‍💻 Autor
<p align="center"> Feito com ❤️ por <b>João Guilhermmy</b> </p>













