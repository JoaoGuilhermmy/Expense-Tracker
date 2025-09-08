💸 Controle Financeiro Pessoal em C++ 💸
🎯 Sobre o Projeto
Este é um sistema de Controle Financeiro Pessoal robusto e intuitivo, desenvolvido inteiramente em C++. Se você busca uma maneira simples e eficiente de gerenciar suas despesas diárias, esta é a ferramenta perfeita!

Através de uma interface de console limpa e direta, o sistema permite que você cadastre, visualize, filtre e remova suas despesas, tudo de forma organizada. Os dados são salvos localmente em um arquivo de texto (despesas.txt), garantindo que suas informações persistam entre os usos e que você tenha total controle sobre elas.

O projeto foi estruturado utilizando conceitos de Programação Orientada a Objetos (POO), com classes bem definidas (Despesa e ControleFinanceiro) que garantem um código limpo, organizado e de fácil manutenção.

✨ Funcionalidades Principais
O sistema oferece um conjunto completo de ferramentas para gerenciar suas finanças:

🖋️ Adicionar Despesas: Cadastre novas despesas de forma rápida, informando descrição, valor, data e associando a uma categoria pré-definida.

📋 Listar Todas as Despesas: Tenha uma visão completa e detalhada de todos os seus gastos registrados.

🗑️ Remover Despesas: Removeu um lançamento por engano? Selecione uma despesa específica da lista e apague-a facilmente.

💰 Calcular Gasto Total: Com um único comando, obtenha a soma total de todas as suas despesas cadastradas.

🔍 Filtrar por Categoria: Analise seus gastos de forma mais profunda! Visualize apenas as despesas de uma categoria específica (como "Alimentação", "Lazer", "Saúde", etc.) e veja o total gasto nela.

📅 Filtrar por Mês e Ano: Quer saber quanto gastou em um período específico? Filtre todas as despesas por um determinado mês e ano (formato mm/aaaa) e veja o balanço do período.

💾 Persistência de Dados: Suas despesas são salvas automaticamente em um arquivo despesas.txt ao sair e carregadas ao iniciar o programa. Você nunca perde seus dados!

🖥️ Interface de Console Limpa: Interações claras e diretas, com limpeza de tela após cada operação para uma melhor experiência de usuário.

🛠️ Tecnologias Utilizadas
C++: Linguagem principal do projeto, escolhida por sua performance e robustez.

Programação Orientada a Objetos (POO): O código é modular e organizado em classes para facilitar a manutenção e escalabilidade.

Manipulação de Arquivos (fstream): Para salvar e carregar os dados das despesas, garantindo a persistência das informações.

Biblioteca Padrão do C++: Uso de iostream, vector, string, sstream, iomanip, entre outras, para as operações fundamentais.

🚀 Como Executar o Projeto
Para compilar e executar este projeto, você precisará de um compilador C++, como o g++ (MinGW) no Windows ou o GCC no Linux.

Clone o repositório:

Bash

git clone https://github.com/JoaoGuilhermmy/Controle-de-gastos_C-.git
Navegue até o diretório do projeto:

Bash

cd Controle-de-gastos_C-
Compile os arquivos-fonte:
Use o seguinte comando no seu terminal para compilar todos os arquivos .cpp e gerar o executável:

Bash

g++ main.cpp Controle.cpp Despesas.cpp -o ControleFinanceiro.exe
Observação: A flag -o define o nome do arquivo de saída (o executável).

Execute o programa:
Após a compilação bem-sucedida, execute o programa com o comando:

Bash

./ControleFinanceiro.exe
Ou, no Windows:

Bash

ControleFinanceiro.exe
Pronto! Agora você já pode começar a gerenciar suas finanças. Um arquivo despesas.txt será criado no mesmo diretório para armazenar seus dados.

📸 Telas da Aplicação
#### Menu Principal
         -------------- Controle Financeiro --------------
Escolha uma opcao:
1 - Adicionar despesa
2 - Listar despesas
3 - Calcular total de despesas
4 - Remover despesa
5 - Mostrar depesas com filtro
6 - Filtrar por mês
7 - Sair
Digite sua opção:

#### Adicionando uma Despesa:
         -------------- Cadastro da Despesa --------------
Digite a descrição da despesa: Jantar com amigos
Digite o valor da despesa: 150.75
Digite a data da despesa: (dd/mm/aaaa): 07/09/2025
Escolha qual categoria sua despesa se encaixa:
1 - Alimentacao
2 - Locomoção
3 - Educação
4 - Lazer
5 - Saúde
6 - Contas e Serviços
7 - Outros

#### Listando Despesas
-----------------------------------------------------
         ***Lista de Despesas***
-----------------------------------------------------


  ----------------------------
  Descrição:        Almoco
  Valor:         R$25.50
  Data:          05/09/2025
  Categoria:     Alimentacao
  ----------------------------
  Descrição:        Uber
  Valor:         R$15.00
  Data:          06/09/2025
  Categoria:     Locomoção
  ----------------------------
Feito com ❤️ por João Guilhermmy 
