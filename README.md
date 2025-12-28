# 💰 Sistema de Controle Financeiro em C++

<div align="center">

![C++](https://img.shields.io/badge/C++-17-blue?style=for-the-badge&logo=cplusplus)
![Windows](https://img.shields.io/badge/Windows-Compatible-0078D6?style=for-the-badge&logo=windows)
![Status](https://img.shields.io/badge/Status-Stable-green?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)

**Gerenciador de despesas pessoais desenvolvido em C++ com persistência de dados e interface de console**

[📖 Sobre](#sobre-o-projeto) • [🚀 Instalação](#instalação) • [💡 Funcionalidades](#funcionalidades) • [🏗️ Arquitetura](#arquitetura)

---

**[🇺🇸 English Version](README.en.md)**

</div>

---

## 📋 Sobre o Projeto

Este é um **sistema de controle financeiro pessoal** desenvolvido em C++ que permite gerenciar despesas de forma simples e eficiente através de interface de console. O sistema oferece categorização, filtragem por período, cálculos automáticos e **persistência de dados em arquivo texto**.

### 🎯 Objetivos

- Demonstrar domínio de **C++ moderno** e STL (Standard Template Library)
- Implementar **gerenciamento de arquivos** para persistência de dados
- Criar uma aplicação prática de **programação orientada a objetos**
- Oferecer uma solução simples e eficaz para controle de despesas pessoais
- Aplicar boas práticas de modularização e separação de responsabilidades

### ✨ Características Principais

- 📁 **Persistência Automática** - Dados salvos em arquivo de texto
- 🏷️ **7 Categorias Predefinidas** - Organização inteligente de despesas
- 🔍 **Filtragem Avançada** - Por categoria ou período (mês/ano)
- 💵 **Cálculos Automáticos** - Total geral e por filtros
- 🖥️ **Interface Console** - Menu interativo e intuitivo
- 🔄 **Carregamento Automático** - Despesas carregadas ao iniciar

---

## ✨ Funcionalidades

### 📊 Gerenciamento de Despesas

#### ➕ Adicionar Despesa
- Descrição detalhada da despesa
- Valor em reais (R$)
- Data no formato DD/MM/AAAA
- Categorização automática
- Validação de entrada
- Salvamento imediato em arquivo

#### 📋 Listar Todas as Despesas
- Visualização formatada e organizada
- Exibição de todos os campos
- Layout responsivo no console
- Informações claras e legíveis

#### 🗑️ Remover Despesa
- Listagem numerada de despesas
- Seleção por índice
- Confirmação de remoção
- Opção de cancelamento (digite 0)
- Atualização automática do arquivo

### 🏷️ Sistema de Categorias

O sistema inclui **7 categorias predefinidas**:

| Categoria | Descrição | Exemplos |
|-----------|-----------|----------|
| 🍔 **Alimentação** | Gastos com comida | Mercado, restaurantes, delivery |
| 🚗 **Locomoção** | Transporte | Combustível, Uber, passagens |
| 📚 **Educação** | Investimento em conhecimento | Cursos, livros, mensalidade |
| 🎮 **Lazer** | Entretenimento | Cinema, jogos, viagens |
| 💊 **Saúde** | Cuidados médicos | Remédios, consultas, exames |
| 🏠 **Contas e Serviços** | Despesas fixas | Água, luz, internet, aluguel |
| 📦 **Outros** | Despesas diversas | Compras variadas |

### 🔍 Filtros e Relatórios

#### Filtrar por Categoria
- Seleção de categoria específica
- Exibição de todas as despesas da categoria
- Cálculo do total gasto na categoria
- Formatação clara dos resultados

#### Filtrar por Mês/Ano
- Busca por período específico (MM/AAAA)
- Listagem de todas as despesas do período
- Total de gastos no mês
- Identificação rápida de padrões de consumo

#### Calcular Total Geral
- Soma automática de todas as despesas
- Exibição formatada em reais (R$)
- Visão geral do orçamento

---

## 🏗️ Arquitetura

### Estrutura do Projeto

```
controle-financeiro/
├── Despesa.h           # Classe de modelo de dados
├── Despesas.cpp        # Implementação da classe Despesa
├── Controle.h          # Classe controladora principal
├── Controle.cpp        # Lógica de negócio e persistência
├── main.cpp            # Ponto de entrada e interface de menu
└── despesas.txt        # Arquivo de persistência (gerado automaticamente)
```

### Diagrama de Classes

```
┌─────────────────────────────────────────┐
│           ControleFinanceiro            │
├─────────────────────────────────────────┤
│ - despesas: vector<Despesa>             │
│ - categorias: vector<string>            │
├─────────────────────────────────────────┤
│ + ControleFinanceiro()                  │
│ + adicionardespesa()                    │
│ + listardespesas()                      │
│ + removerdespesa()                      │
│ + calcular()                            │
│ + filtrardespesas()                     │
│ + filtrar_mes()                         │
│ + salvarcontrole()                      │
│ + carregarcontrole()                    │
└──────────────┬──────────────────────────┘
               │
               │ 1..*
               │
               ▼
┌─────────────────────────────────────────┐
│              Despesa                    │
├─────────────────────────────────────────┤
│ - descricao: string                     │
│ - valor: double                         │
│ - data: string                          │
│ - categoria: string                     │
├─────────────────────────────────────────┤
│ + Despesa(desc, val, data, cat)         │
│ + getDescricao(): string                │
│ + getValor(): double                    │
│ + getData(): string                     │
│ + getCategoria(): string                │
└─────────────────────────────────────────┘
```

### Padrões de Projeto

| Padrão | Aplicação | Benefício |
|--------|-----------|-----------|
| **MVC (Model-View-Controller)** | Separação de responsabilidades | Manutenibilidade |
| **Encapsulation** | Classe Despesa com getters | Segurança dos dados |
| **Repository Pattern** | Métodos de persistência em arquivo | Abstração de dados |

### Fluxo de Dados

```
┌─────────────┐
│    main()   │  ← Ponto de entrada
└──────┬──────┘
       │
       ▼
┌────────────────────────────┐
│  ControleFinanceiro        │
│  (Instância única)         │
└──────┬─────────────────────┘
       │
       ├─── carregarcontrole()
       │    ├─ Abre despesas.txt
       │    ├─ Parse linha por linha
       │    └─ Cria objetos Despesa
       │
       ├─── Menu Interativo
       │    ├─ Adicionar despesa
       │    ├─ Listar despesas
       │    ├─ Calcular total
       │    ├─ Remover despesa
       │    ├─ Filtrar por categoria
       │    └─ Filtrar por mês
       │
       └─── salvarcontrole()
            ├─ Serializa despesas
            └─ Salva em despesas.txt
```

---

## 🚀 Instalação

### Pré-requisitos

- 💻 **Sistema Operacional:** Windows (usa `windows.h` para funções específicas)
- 🔧 **Compilador C++:** MinGW-w64, MSVC ou similar com suporte a C++11+
- 📝 **IDE (Opcional):** Code::Blocks, Visual Studio, VS Code, Dev-C++

### Compilação via MinGW (Recomendado)

#### 1️⃣ Instalar MinGW

Baixe e instale o MinGW-w64:
- [MinGW-w64 Download](https://sourceforge.net/projects/mingw-w64/)
- Durante a instalação, selecione a arquitetura compatível com seu sistema

#### 2️⃣ Clone o repositório

```bash
git clone https://github.com/seu-usuario/controle-financeiro-cpp.git
cd controle-financeiro-cpp
```

#### 3️⃣ Compilar o projeto

```bash
# Compilar todos os arquivos
g++ -std=c++17 -o controle_financeiro.exe main.cpp Despesas.cpp Controle.cpp

# Ou com otimização
g++ -std=c++17 -O2 -o controle_financeiro.exe main.cpp Despesas.cpp Controle.cpp
```

#### 4️⃣ Executar

```bash
controle_financeiro.exe
```

### Compilação via Visual Studio

#### Método 1: Projeto Console

1. Abra o Visual Studio
2. `File` → `New` → `Project`
3. Selecione "Console App" (C++)
4. Adicione todos os arquivos `.h` e `.cpp` ao projeto
5. Pressione `F5` para compilar e executar

#### Método 2: Via Developer Command Prompt

```bash
cl /EHsc /std:c++17 main.cpp Despesas.cpp Controle.cpp
```

### Compilação via Code::Blocks

1. Abra o Code::Blocks
2. `File` → `New` → `Project` → `Console application`
3. Adicione os arquivos ao projeto
4. `Build` → `Build and Run` (F9)

---

## 💻 Como Usar

### Menu Principal

Ao executar o programa, você verá o seguinte menu:

```
-------------- Controle Financeiro --------------
Escolha uma opcao:
1 - Adicionar despesa
2 - Listar despesas
3 - Calcular total de despesas
4 - Remover despesa
5 - Mostrar despesas com filtro
6 - Filtrar por mês
7 - Sair
Digite sua opção:
```

### Exemplos de Uso

#### 📝 Adicionar uma Despesa

```
Opção: 1

-------------- Cadastro da Despesa --------------
Digite a descrição da despesa: Almoço no restaurante
Digite o valor da despesa: 45.50
Digite a data da despesa (dd/mm/aaaa): 15/12/2024

Escolha qual categoria sua despesa se encaixa:
1 - Alimentacao
2 - Locomoção
3 - Educação
4 - Lazer
5 - Saúde
6 - Contas e Serviços
7 - Outros
[Escolha]: 1

✓ Despesa salva com sucesso!
```

#### 📋 Listar Despesas

```
Opção: 2

-----------------------------------------------------
         ***Lista de Despesas***
-----------------------------------------------------

----------------------------
Descrição: Almoço no restaurante
Valor: R$45.50
Data: 15/12/2024
Categoria: Alimentacao
----------------------------
Descrição: Gasolina
Valor: R$200.00
Data: 14/12/2024
Categoria: Locomoção
----------------------------
```

#### 🗑️ Remover Despesa

```
Opção: 4

-----------------------------------------------------
         ***Lista de Despesas***
-----------------------------------------------------

Despesa #1
Descrição: Almoço no restaurante
Valor: R$45.50
Data: 15/12/2024
Categoria: Alimentacao
----------------------------
Despesa #2
Descrição: Gasolina
Valor: R$200.00
Data: 14/12/2024
Categoria: Locomoção
----------------------------

Digite o número da despesa que deseja remover (digite 0 para cancelar): 1

✓ Despesa removida com sucesso!
```

#### 🔍 Filtrar por Categoria

```
Opção: 5

Escolha qual categoria você deseja filtrar:
1 - Alimentacao
2 - Locomoção
3 - Educação
4 - Lazer
5 - Saúde
6 - Contas e Serviços
7 - Outros
: 1

----------------------------
Descrição: Almoço no restaurante
Valor: 45.50
Data: 15/12/2024
Categoria: Alimentacao
----------------------------
Descrição: Supermercado
Valor: 320.00
Data: 10/12/2024
Categoria: Alimentacao
----------------------------

Total de despesas: R$365.50
```

#### 📅 Filtrar por Mês

```
Opção: 6

Digite o mes e o ano (no formato mm/aaaa): 12/2024

--- Despesas do Periodo: 12/2024 ---

----------------------------------------
  Descricao: Almoço no restaurante
  Valor: R$ 45.50
  Data: 15/12/2024

----------------------------------------
  Descricao: Gasolina
  Valor: R$ 200.00
  Data: 14/12/2024

----------------------------------------
  Gasto Total no Periodo: R$ 245.50
```

#### 💰 Calcular Total

```
Opção: 3

Total de despesas: R$1.245.80
```

### Fluxo de Trabalho Típico

```
1. Inicie o programa
   ↓
2. Programa carrega despesas.txt automaticamente
   ↓
3. Adicione suas despesas diárias (opção 1)
   ↓
4. Consulte gastos por categoria (opção 5)
   ↓
5. Verifique total do mês (opção 6)
   ↓
6. Remova despesas duplicadas ou incorretas (opção 4)
   ↓
7. Saia do programa (opção 7)
   ↓
8. Despesas são salvas automaticamente!
```

---

## 📁 Persistência de Dados

### Formato do Arquivo `despesas.txt`

O sistema utiliza um arquivo de texto simples com formato CSV (valores separados por ponto e vírgula):

```
Almoço no restaurante;45.50;15/12/2024;Alimentacao
Gasolina;200.00;14/12/2024;Locomoção
Curso online;149.90;10/12/2024;Educação
```

**Estrutura:**
```
[descrição];[valor];[data];[categoria]
```

### Funcionamento da Persistência

#### Carregamento (ao iniciar)
```cpp
void ControleFinanceiro::carregarcontrole() {
    // 1. Abre despesas.txt
    // 2. Lê linha por linha
    // 3. Faz parsing usando stringstream
    // 4. Cria objetos Despesa
    // 5. Adiciona ao vector despesas
}
```

#### Salvamento (ao sair ou modificar)
```cpp
void ControleFinanceiro::salvarcontrole() {
    // 1. Abre/cria despesas.txt
    // 2. Itera sobre vector de despesas
    // 3. Serializa cada despesa no formato CSV
    // 4. Escreve no arquivo
    // 5. Fecha o arquivo
}
```

### Vantagens do Formato Texto

✅ **Portabilidade** - Fácil transferência entre sistemas
✅ **Legibilidade** - Pode ser editado manualmente se necessário
✅ **Simplicidade** - Não requer bibliotecas externas
✅ **Backup fácil** - Copiar arquivo é suficiente
✅ **Debug facilitado** - Inspeção visual dos dados

---

## 🔧 Tecnologias e Recursos

### Bibliotecas STL Utilizadas

| Biblioteca | Uso | Funcionalidade |
|------------|-----|----------------|
| `<vector>` | Armazenamento dinâmico | Lista de despesas e categorias |
| `<string>` | Manipulação de texto | Descrições, datas, categorias |
| `<fstream>` | Entrada/saída de arquivo | Persistência de dados |
| `<sstream>` | String streams | Parsing do arquivo CSV |
| `<iostream>` | Input/output console | Interface do usuário |
| `<iomanip>` | Formatação de saída | Alinhamento e precisão decimal |
| `<limits>` | Limites numéricos | Limpeza de buffer de entrada |
| `<windows.h>` | API Windows | Sleep() e SetConsoleOutputCP() |

### Recursos Avançados de C++

#### 1. **Auto Type Deduction**
```cpp
for (const auto &despesa : despesas) {
    // Iteração moderna com auto
}
```

#### 2. **Range-based For Loops**
```cpp
for (auto &cat : categorias) {
    std::cout << cat << std::endl;
}
```

#### 3. **String Streams para Parsing**
```cpp
std::stringstream ss(linha);
std::getline(ss, descricao, ';');
```

#### 4. **Vector com Objetos Complexos**
```cpp
std::vector<Despesa> despesas;
despesas.push_back(Despesa(desc, val, data, cat));
```

#### 5. **Const Correctness**
```cpp
void listardespesas() const;  // Método não modifica estado
```

### Conceitos de POO Aplicados

- ✅ **Encapsulamento** - Atributos privados com getters públicos
- ✅ **Abstração** - Interface clara e métodos bem definidos
- ✅ **Separação de Responsabilidades** - Despesa (modelo) e ControleFinanceiro (controle)
- ✅ **Composição** - ControleFinanceiro contém vector de Despesa
- ✅ **Imutabilidade** - Objetos Despesa não têm setters

---

## 🎨 Recursos da Interface

### Formatação Avançada

```cpp
// Precisão decimal para valores monetários
std::cout << std::fixed << std::setprecision(2);

// Alinhamento de texto
std::cout << std::left << std::setw(15) << "Descrição: ";

// Resultado: valores sempre com 2 casas decimais
// R$ 45.50 (não R$ 45.5)
```

### Encoding UTF-8

```cpp
SetConsoleOutputCP(CP_UTF8);
// Permite acentuação correta no Windows
// "Educação" em vez de "Educa��o"
```

### Limpeza de Tela

```cpp
void limpatela() const {
    system("cls");  // Limpa console no Windows
}
```

### Delays para Usabilidade

```cpp
Sleep(3000);  // Pausa de 3 segundos
// Permite ao usuário ler mensagens antes de limpar tela
```

---

## 📊 Análises e Relatórios

### Insights Disponíveis

#### 1. **Gasto Total Global**
```
Total acumulado de TODAS as despesas registradas
Útil para: Visão geral do orçamento
```

#### 2. **Gasto por Categoria**
```
Total gasto em Alimentação, Locomoção, etc.
Útil para: Identificar onde vai mais dinheiro
```

#### 3. **Gasto Mensal**
```
Total gasto em um mês específico (ex: 12/2024)
Útil para: Comparação mês a mês, planejamento
```

### Exemplo de Análise

```
Cenário: Usuário quer economizar

1. Lista todas as despesas (opção 2)
   → Identifica despesas dispensáveis

2. Filtra por "Lazer" (opção 5)
   → Total: R$ 450,00 no mês
   → Meta: Reduzir para R$ 300,00

3. Filtra por mês atual (opção 6)
   → Total mensal: R$ 2.100,00
   → Compara com meses anteriores

4. Remove despesas desnecessárias (opção 4)
   → Limpa registros duplicados

Resultado: Controle financeiro eficaz! 💰
```

---

## 🚀 Melhorias Futuras

### Curto Prazo
- [ ] Adicionar categorias customizáveis
- [ ] Implementar edição de despesas existentes
- [ ] Adicionar suporte para receitas/entradas
- [ ] Criar backup automático do arquivo
- [ ] Validação mais robusta de datas

### Médio Prazo
- [ ] Interface gráfica com Qt ou wxWidgets
- [ ] Gráficos de pizza para visualização de categorias
- [ ] Exportação para CSV/Excel
- [ ] Múltiplos usuários com login
- [ ] Sincronização em nuvem

### Longo Prazo
- [ ] Versão mobile (Android/iOS)
- [ ] API REST para acesso remoto
- [ ] Integração com bancos (Open Banking)
- [ ] Machine Learning para previsão de gastos
- [ ] Alertas de orçamento por categoria

---

## 🐛 Solução de Problemas

### Problema: Caracteres estranhos no console

**Sintoma:** Acentos aparecem como `�` ou `?`

**Solução:**
```cpp
// Já incluído no main.cpp
SetConsoleOutputCP(CP_UTF8);
```

### Problema: Arquivo despesas.txt não é criado

**Causa:** Permissões de escrita no diretório

**Solução:**
1. Execute o programa como administrador
2. Ou mova para uma pasta com permissões (ex: Documentos)

### Problema: Compilação falha com erros de "windows.h"

**Causa:** Compilando em Linux/Mac

**Solução:** Remover ou substituir funções específicas do Windows:
```cpp
// Substituir Sleep(3000) por:
#include <thread>
#include <chrono>
std::this_thread::sleep_for(std::chrono::seconds(3));

// Substituir system("cls") por:
system("clear");  // Linux/Mac
```

### Problema: Valores monetários com muitas casas decimais

**Causa:** Falta de formatação de precisão

**Solução:** Já implementado com:
```cpp
std::cout << std::fixed << std::setprecision(2);
```

---

## 🤝 Contribuindo

Contribuições são muito bem-vindas! Este é um projeto educacional perfeito para aprender C++.

### Como Contribuir

1. Faça um Fork do projeto
2. Crie uma branch para sua feature (`git checkout -b feature/MinhaFeature`)
3. Commit suas mudanças (`git commit -m 'Adiciona nova feature'`)
4. Push para a branch (`git push origin feature/MinhaFeature`)
5. Abra um Pull Request

### Ideias para Contribuição

- 🎨 Melhorar interface do console com cores (ANSI codes)
- 📊 Adicionar mais relatórios e estatísticas
- 🔒 Implementar criptografia do arquivo de dados
- 🌍 Adicionar suporte a múltiplos idiomas
- ✅ Criar testes unitários
- 📖 Melhorar documentação do código

---

## 📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

---

## 👨‍💻 Autor

**João Guilhermmy**

- GitHub: https://github.com/JoaoGuilhermmy
- LinkedIn: www.linkedin.com/in/joão-guilhermmy-93661b29b
- Email:  joaoguilhermmy2@gmail.com

---

## 🙏 Agradecimentos

- Comunidade C++ pela excelente documentação
- Stack Overflow pelas soluções de problemas comuns
- Todos que testaram e deram feedback sobre o projeto

---

## 📚 Recursos Adicionais

### Tutoriais Recomendados
- [Learn C++](https://www.learncpp.com/) - Tutorial completo de C++
- [CPlusPlus.com](http://www.cplusplus.com/) - Referência da STL
- [GeeksforGeeks C++](https://www.geeksforgeeks.org/c-plus-plus/) - Exemplos práticos

### Livros Sugeridos
- "C++ Primer" por Stanley B. Lippman
- "Effective Modern C++" por Scott Meyers
- "The C++ Programming Language" por Bjarne Stroustrup

---

<div align="center">

### ⭐ Se este projeto foi útil, considere dar uma estrela!

**Desenvolvido com ❤️ e muito ☕**

### 💡 Projeto educacional para demonstrar conceitos de C++ e POO

</div>
