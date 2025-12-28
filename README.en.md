# 💰 C++ Financial Control System

<div align="center">

![C++](https://img.shields.io/badge/C++-17-blue?style=for-the-badge&logo=cplusplus)
![Windows](https://img.shields.io/badge/Windows-Compatible-0078D6?style=for-the-badge&logo=windows)
![Status](https://img.shields.io/badge/Status-Stable-green?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)

**Personal expense manager developed in C++ with data persistence and console interface**

[📖 About](#about-the-project) • [🚀 Installation](#installation) • [💡 Features](#features) • [🏗️ Architecture](#architecture)

---

**[🇧🇷 Versão em Português](README.md)**

</div>

---

## 📋 About the Project

This is a **personal financial control system** developed in C++ that allows you to manage expenses simply and efficiently through a console interface. The system offers categorization, period filtering, automatic calculations, and **data persistence in text file**.

### 🎯 Objectives

- Demonstrate mastery of **modern C++** and STL (Standard Template Library)
- Implement **file management** for data persistence
- Create a practical application of **object-oriented programming**
- Offer a simple and effective solution for personal expense control
- Apply best practices in modularization and separation of concerns

### ✨ Key Features

- 📁 **Automatic Persistence** - Data saved in text file
- 🏷️ **7 Predefined Categories** - Smart expense organization
- 🔍 **Advanced Filtering** - By category or period (month/year)
- 💵 **Automatic Calculations** - Grand total and by filters
- 🖥️ **Console Interface** - Interactive and intuitive menu
- 🔄 **Auto-loading** - Expenses loaded on startup

---

## ✨ Features

### 📊 Expense Management

#### ➕ Add Expense
- Detailed expense description
- Amount in Brazilian Reais (R$)
- Date in DD/MM/YYYY format
- Automatic categorization
- Input validation
- Immediate file save

#### 📋 List All Expenses
- Formatted and organized visualization
- Display of all fields
- Responsive console layout
- Clear and readable information

#### 🗑️ Remove Expense
- Numbered expense list
- Selection by index
- Removal confirmation
- Cancel option (type 0)
- Automatic file update

### 🏷️ Category System

The system includes **7 predefined categories**:

| Category | Description | Examples |
|----------|-------------|----------|
| 🍔 **Food** | Food expenses | Groceries, restaurants, delivery |
| 🚗 **Transportation** | Transportation | Fuel, Uber, tickets |
| 📚 **Education** | Knowledge investment | Courses, books, tuition |
| 🎮 **Leisure** | Entertainment | Movies, games, travel |
| 💊 **Health** | Medical care | Medicine, appointments, exams |
| 🏠 **Bills & Services** | Fixed expenses | Water, electricity, internet, rent |
| 📦 **Others** | Miscellaneous expenses | Various purchases |

### 🔍 Filters and Reports

#### Filter by Category
- Specific category selection
- Display of all expenses in category
- Calculation of total spent in category
- Clear formatting of results

#### Filter by Month/Year
- Search by specific period (MM/YYYY)
- List of all expenses in period
- Total spending for the month
- Quick identification of consumption patterns

#### Calculate Grand Total
- Automatic sum of all expenses
- Formatted display in Reais (R$)
- Budget overview

---

## 🏗️ Architecture

### Project Structure

```
financial-control/
├── Despesa.h           # Data model class
├── Despesas.cpp        # Despesa class implementation
├── Controle.h          # Main controller class
├── Controle.cpp        # Business logic and persistence
├── main.cpp            # Entry point and menu interface
└── despesas.txt        # Persistence file (auto-generated)
```

### Class Diagram

```
┌─────────────────────────────────────────┐
│        ControleFinanceiro               │
│        (FinancialControl)               │
├─────────────────────────────────────────┤
│ - despesas: vector<Despesa>             │
│   (expenses)                            │
│ - categorias: vector<string>            │
│   (categories)                          │
├─────────────────────────────────────────┤
│ + ControleFinanceiro()                  │
│ + adicionardespesa()                    │
│   (addExpense)                          │
│ + listardespesas()                      │
│   (listExpenses)                        │
│ + removerdespesa()                      │
│   (removeExpense)                       │
│ + calcular()                            │
│   (calculate)                           │
│ + filtrardespesas()                     │
│   (filterExpenses)                      │
│ + filtrar_mes()                         │
│   (filterMonth)                         │
│ + salvarcontrole()                      │
│   (saveControl)                         │
│ + carregarcontrole()                    │
│   (loadControl)                         │
└──────────────┬──────────────────────────┘
               │
               │ 1..*
               │
               ▼
┌─────────────────────────────────────────┐
│           Despesa (Expense)             │
├─────────────────────────────────────────┤
│ - descricao: string (description)       │
│ - valor: double (amount)                │
│ - data: string (date)                   │
│ - categoria: string (category)          │
├─────────────────────────────────────────┤
│ + Despesa(desc, val, date, cat)         │
│ + getDescricao(): string                │
│ + getValor(): double                    │
│ + getData(): string                     │
│ + getCategoria(): string                │
└─────────────────────────────────────────┘
```

### Design Patterns

| Pattern | Application | Benefit |
|---------|-------------|---------|
| **MVC (Model-View-Controller)** | Separation of concerns | Maintainability |
| **Encapsulation** | Despesa class with getters | Data security |
| **Repository Pattern** | File persistence methods | Data abstraction |

### Data Flow

```
┌─────────────┐
│    main()   │  ← Entry point
└──────┬──────┘
       │
       ▼
┌────────────────────────────┐
│  ControleFinanceiro        │
│  (Single instance)         │
└──────┬─────────────────────┘
       │
       ├─── carregarcontrole() (loadControl)
       │    ├─ Opens despesas.txt
       │    ├─ Parse line by line
       │    └─ Creates Despesa objects
       │
       ├─── Interactive Menu
       │    ├─ Add expense
       │    ├─ List expenses
       │    ├─ Calculate total
       │    ├─ Remove expense
       │    ├─ Filter by category
       │    └─ Filter by month
       │
       └─── salvarcontrole() (saveControl)
            ├─ Serializes expenses
            └─ Saves to despesas.txt
```

---

## 🚀 Installation

### Prerequisites

- 💻 **Operating System:** Windows (uses `windows.h` for specific functions)
- 🔧 **C++ Compiler:** MinGW-w64, MSVC or similar with C++11+ support
- 📝 **IDE (Optional):** Code::Blocks, Visual Studio, VS Code, Dev-C++

### Compilation via MinGW (Recommended)

#### 1️⃣ Install MinGW

Download and install MinGW-w64:
- [MinGW-w64 Download](https://sourceforge.net/projects/mingw-w64/)
- During installation, select the architecture compatible with your system

#### 2️⃣ Clone the repository

```bash
git clone https://github.com/your-username/cpp-financial-control.git
cd cpp-financial-control
```

#### 3️⃣ Compile the project

```bash
# Compile all files
g++ -std=c++17 -o financial_control.exe main.cpp Despesas.cpp Controle.cpp

# Or with optimization
g++ -std=c++17 -O2 -o financial_control.exe main.cpp Despesas.cpp Controle.cpp
```

#### 4️⃣ Run

```bash
financial_control.exe
```

### Compilation via Visual Studio

#### Method 1: Console Project

1. Open Visual Studio
2. `File` → `New` → `Project`
3. Select "Console App" (C++)
4. Add all `.h` and `.cpp` files to project
5. Press `F5` to compile and run

#### Method 2: Via Developer Command Prompt

```bash
cl /EHsc /std:c++17 main.cpp Despesas.cpp Controle.cpp
```

### Compilation via Code::Blocks

1. Open Code::Blocks
2. `File` → `New` → `Project` → `Console application`
3. Add files to project
4. `Build` → `Build and Run` (F9)

---

## 💻 How to Use

### Main Menu

When running the program, you will see the following menu:

```
-------------- Financial Control --------------
Choose an option:
1 - Add expense
2 - List expenses
3 - Calculate total expenses
4 - Remove expense
5 - Show expenses with filter
6 - Filter by month
7 - Exit
Enter your option:
```

### Usage Examples

#### 📝 Add an Expense

```
Option: 1

-------------- Expense Registration --------------
Enter expense description: Lunch at restaurant
Enter expense amount: 45.50
Enter expense date (dd/mm/yyyy): 15/12/2024

Choose which category your expense fits:
1 - Food
2 - Transportation
3 - Education
4 - Leisure
5 - Health
6 - Bills & Services
7 - Others
[Choose]: 1

✓ Expense saved successfully!
```

#### 📋 List Expenses

```
Option: 2

-----------------------------------------------------
         ***Expense List***
-----------------------------------------------------

----------------------------
Description: Lunch at restaurant
Amount: R$45.50
Date: 15/12/2024
Category: Food
----------------------------
Description: Gasoline
Amount: R$200.00
Date: 14/12/2024
Category: Transportation
----------------------------
```

#### 🗑️ Remove Expense

```
Option: 4

-----------------------------------------------------
         ***Expense List***
-----------------------------------------------------

Expense #1
Description: Lunch at restaurant
Amount: R$45.50
Date: 15/12/2024
Category: Food
----------------------------
Expense #2
Description: Gasoline
Amount: R$200.00
Date: 14/12/2024
Category: Transportation
----------------------------

Enter the expense number you want to remove (type 0 to cancel): 1

✓ Expense removed successfully!
```

#### 🔍 Filter by Category

```
Option: 5

Choose which category you want to filter:
1 - Food
2 - Transportation
3 - Education
4 - Leisure
5 - Health
6 - Bills & Services
7 - Others
: 1

----------------------------
Description: Lunch at restaurant
Amount: 45.50
Date: 15/12/2024
Category: Food
----------------------------
Description: Supermarket
Amount: 320.00
Date: 10/12/2024
Category: Food
----------------------------

Total expenses: R$365.50
```

#### 📅 Filter by Month

```
Option: 6

Enter month and year (in mm/yyyy format): 12/2024

--- Period Expenses: 12/2024 ---

----------------------------------------
  Description: Lunch at restaurant
  Amount: R$ 45.50
  Date: 15/12/2024

----------------------------------------
  Description: Gasoline
  Amount: R$ 200.00
  Date: 14/12/2024

----------------------------------------
  Total Period Spending: R$ 245.50
```

#### 💰 Calculate Total

```
Option: 3

Total expenses: R$1,245.80
```

### Typical Workflow

```
1. Start the program
   ↓
2. Program automatically loads despesas.txt
   ↓
3. Add your daily expenses (option 1)
   ↓
4. Check spending by category (option 5)
   ↓
5. Verify monthly total (option 6)
   ↓
6. Remove duplicate or incorrect expenses (option 4)
   ↓
7. Exit program (option 7)
   ↓
8. Expenses are automatically saved!
```

---

## 📁 Data Persistence

### `despesas.txt` File Format

The system uses a simple text file with CSV format (semicolon-separated values):

```
Lunch at restaurant;45.50;15/12/2024;Food
Gasoline;200.00;14/12/2024;Transportation
Online course;149.90;10/12/2024;Education
```

**Structure:**
```
[description];[amount];[date];[category]
```

### How Persistence Works

#### Loading (on startup)
```cpp
void ControleFinanceiro::carregarcontrole() {
    // 1. Opens despesas.txt
    // 2. Reads line by line
    // 3. Parses using stringstream
    // 4. Creates Despesa objects
    // 5. Adds to expenses vector
}
```

#### Saving (on exit or modification)
```cpp
void ControleFinanceiro::salvarcontrole() {
    // 1. Opens/creates despesas.txt
    // 2. Iterates over expenses vector
    // 3. Serializes each expense in CSV format
    // 4. Writes to file
    // 5. Closes file
}
```

### Text Format Advantages

✅ **Portability** - Easy transfer between systems
✅ **Readability** - Can be manually edited if needed
✅ **Simplicity** - No external libraries required
✅ **Easy Backup** - Copying file is sufficient
✅ **Facilitated Debug** - Visual data inspection

---

## 🔧 Technologies and Resources

### STL Libraries Used

| Library | Use | Functionality |
|---------|-----|---------------|
| `<vector>` | Dynamic storage | List of expenses and categories |
| `<string>` | Text manipulation | Descriptions, dates, categories |
| `<fstream>` | File input/output | Data persistence |
| `<sstream>` | String streams | CSV file parsing |
| `<iostream>` | Console input/output | User interface |
| `<iomanip>` | Output formatting | Alignment and decimal precision |
| `<limits>` | Numeric limits | Input buffer clearing |
| `<windows.h>` | Windows API | Sleep() and SetConsoleOutputCP() |

### Advanced C++ Features

#### 1. **Auto Type Deduction**
```cpp
for (const auto &expense : expenses) {
    // Modern iteration with auto
}
```

#### 2. **Range-based For Loops**
```cpp
for (auto &cat : categories) {
    std::cout << cat << std::endl;
}
```

#### 3. **String Streams for Parsing**
```cpp
std::stringstream ss(line);
std::getline(ss, description, ';');
```

#### 4. **Vector with Complex Objects**
```cpp
std::vector<Despesa> expenses;
expenses.push_back(Despesa(desc, val, date, cat));
```

#### 5. **Const Correctness**
```cpp
void listExpenses() const;  // Method doesn't modify state
```

### Applied OOP Concepts

- ✅ **Encapsulation** - Private attributes with public getters
- ✅ **Abstraction** - Clear interface and well-defined methods
- ✅ **Separation of Concerns** - Despesa (model) and ControleFinanceiro (controller)
- ✅ **Composition** - ControleFinanceiro contains vector of Despesa
- ✅ **Immutability** - Despesa objects have no setters

---

## 🎨 Interface Features

### Advanced Formatting

```cpp
// Decimal precision for monetary values
std::cout << std::fixed << std::setprecision(2);

// Text alignment
std::cout << std::left << std::setw(15) << "Description: ";

// Result: values always with 2 decimal places
// R$ 45.50 (not R$ 45.5)
```

### UTF-8 Encoding

```cpp
SetConsoleOutputCP(CP_UTF8);
// Allows correct accentuation on Windows
// "Education" instead of "Educa��o"
```

### Screen Clearing

```cpp
void clearscreen() const {
    system("cls");  // Clears console on Windows
}
```

### Usability Delays

```cpp
Sleep(3000);  // 3-second pause
// Allows user to read messages before clearing screen
```

---

## 📊 Analysis and Reports

### Available Insights

#### 1. **Global Total Spending**
```
Accumulated total of ALL registered expenses
Useful for: Budget overview
```

#### 2. **Spending by Category**
```
Total spent on Food, Transportation, etc.
Useful for: Identifying where money goes most
```

#### 3. **Monthly Spending**
```
Total spent in a specific month (e.g., 12/2024)
Useful for: Month-to-month comparison, planning
```

### Analysis Example

```
Scenario: User wants to save money

1. List all expenses (option 2)
   → Identifies unnecessary expenses

2. Filter by "Leisure" (option 5)
   → Total: R$ 450.00 per month
   → Goal: Reduce to R$ 300.00

3. Filter by current month (option 6)
   → Monthly total: R$ 2,100.00
   → Compare with previous months

4. Remove unnecessary expenses (option 4)
   → Cleans duplicate records

Result: Effective financial control! 💰
```

---

## 🚀 Future Improvements

### Short Term
- [ ] Add customizable categories
- [ ] Implement editing of existing expenses
- [ ] Add support for income/revenues
- [ ] Create automatic file backup
- [ ] More robust date validation

### Medium Term
- [ ] Graphical interface with Qt or wxWidgets
- [ ] Pie charts for category visualization
- [ ] Export to CSV/Excel
- [ ] Multiple users with login
- [ ] Cloud synchronization

### Long Term
- [ ] Mobile version (Android/iOS)
- [ ] REST API for remote access
- [ ] Bank integration (Open Banking)
- [ ] Machine Learning for expense prediction
- [ ] Budget alerts by category

---

## 🐛 Troubleshooting

### Problem: Strange characters in console

**Symptom:** Accents appear as `�` or `?`

**Solution:**
```cpp
// Already included in main.cpp
SetConsoleOutputCP(CP_UTF8);
```

### Problem: despesas.txt file is not created

**Cause:** Write permissions in directory

**Solution:**
1. Run program as administrator
2. Or move to a folder with permissions (e.g., Documents)

### Problem: Compilation fails with "windows.h" errors

**Cause:** Compiling on Linux/Mac

**Solution:** Remove or replace Windows-specific functions:
```cpp
// Replace Sleep(3000) with:
#include <thread>
#include <chrono>
std::this_thread::sleep_for(std::chrono::seconds(3));

// Replace system("cls") with:
system("clear");  // Linux/Mac
```

### Problem: Monetary values with many decimal places

**Cause:** Lack of precision formatting

**Solution:** Already implemented with:
```cpp
std::cout << std::fixed << std::setprecision(2);
```

---

## 🤝 Contributing

Contributions are very welcome! This is a perfect educational project for learning C++.

### How to Contribute

1. Fork the project
2. Create a branch for your feature (`git checkout -b feature/MyFeature`)
3. Commit your changes (`git commit -m 'Add new feature'`)
4. Push to the branch (`git push origin feature/MyFeature`)
5. Open a Pull Request

### Contribution Ideas

- 🎨 Improve console interface with colors (ANSI codes)
- 📊 Add more reports and statistics
- 🔒 Implement data file encryption
- 🌍 Add multi-language support
- ✅ Create unit tests
- 📖 Improve code documentation

---

## 📄 License

This project is under the MIT license. See the [LICENSE](LICENSE) file for more details.

---

## 👨‍💻 Author

**Your Name**

- GitHub: https://github.com/JoaoGuilhermmy
- LinkedIn: www.linkedin.com/in/joão-guilhermmy-93661b29b
- Email: your.email@example.com

---

## 🙏 Acknowledgments

- C++ community for excellent documentation
- Stack Overflow for common problem solutions
- Everyone who tested and gave feedback on the project

---

## 📚 Additional Resources

### Recommended Tutorials
- [Learn C++](https://www.learncpp.com/) - Complete C++ tutorial
- [CPlusPlus.com](http://www.cplusplus.com/) - STL reference
- [GeeksforGeeks C++](https://www.geeksforgeeks.org/c-plus-plus/) - Practical examples

### Suggested Books
- "C++ Primer" by Stanley B. Lippman
- "Effective Modern C++" by Scott Meyers
- "The C++ Programming Language" by Bjarne Stroustrup

---

<div align="center">

### ⭐ If this project was useful, consider giving it a star!

**Developed with ❤️ and lots of ☕**

### 💡 Educational project to demonstrate C++ and OOP concepts

</div>
