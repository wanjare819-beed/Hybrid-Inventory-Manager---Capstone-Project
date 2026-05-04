# Hybrid-Inventory-Manager---Capstone-Project
A complete inventory management system demonstrating hybrid C/C++ programming with a C backend and C++ frontend.
Project Structure
inventory_project/
├── include/
│   └── inventory.h          # Header file with struct and function declarations
├── src/
│   ├── inventory.c          # C backend implementation (CRUD operations)
│   ├── InventoryManager.cpp # C++ frontend class (UI and validation)
│   └── main.cpp             # Main program with console menu
├── Makefile                 # Makefile for Unix/Linux systems
├── build.bat                # Build script for Windows
├── clean.bat                # Clean script for Windows
└── README.md                # This file
Features
C Backend (inventory.c)
Binary file operations using inventory.dat
CRUD functions:
add_item() - Add new inventory item
get_item() - Retrieve item by ID
update_item() - Update existing item
delete_item() - Soft delete (marks as deleted)
list_items() - List all active items
get_next_id() - Auto-generate unique IDs
File I/O: Uses fread, fwrite, fseek
Soft delete: Items marked with is_deleted flag instead of physical deletion
C++ Frontend (InventoryManager.cpp)
InventoryManager class with encapsulated methods
STL containers: Uses std::vector<Item> for caching
Sorting: Implements std::sort with lambda for ID-based sorting
Input validation: Comprehensive validation for all user inputs
User-friendly interface: Clear prompts and error messages
Main Program (main.cpp)
Interactive console menu with 6 options:
Add Item
View Item
Update Item
Delete Item
List All Items
Exit
Robust input handling: Validates all user inputs
Clean UI: Professional menu display
Technical Details
Item Structure
typedef struct {
    int id;              // Unique identifier
    char name[50];       // Item name
    int quantity;        // Stock quantity
    float price;         // Item price
    int is_deleted;      // Soft delete flag (0=active, 1=deleted)
} Item;
Key Features
✅ extern "C" linkage for C/C++ interoperability
✅ Binary file storage (inventory.dat)
✅ Soft delete mechanism (preserves data)
✅ Auto-incrementing IDs
✅ Input validation (prevents invalid data)
✅ Memory management (proper allocation/deallocation)
✅ Error handling (file operations, user input)
Compilation
Windows (using batch files)
# Build the project
build.bat

# Run the program
app.exe

# Clean build artifacts
clean.bat
Windows (manual compilation)
gcc -Wall -Iinclude -c src/inventory.c -o inventory.o
g++ -Wall -Iinclude -c src/InventoryManager.cpp -o InventoryManager.o
g++ -Wall -Iinclude -c src/main.cpp -o main.o
g++ inventory.o InventoryManager.o main.o -o app.exe
Unix/Linux/Mac (using Makefile)
# Build the project
make all

# Run the program
make run

# Clean build artifacts
make clean
Usage Example
Start the program:

app.exe
Add an item (Option 1):

Enter item name: "Laptop"
Enter quantity: 10
Enter price: 999.99
List all items (Option 5):

View all inventory items sorted by ID
Update an item (Option 3):

Enter item ID to update
Modify name, quantity, or price
Delete an item (Option 4):

Enter item ID to delete
Confirm deletion (soft delete)
Exit (Option 6):

Safely exit the program
Data Persistence
All data is stored in inventory.dat (binary file)
Data persists between program runs
Deleted items are marked but not removed (soft delete)
File is created automatically on first use
Requirements
Compiler: GCC (gcc/g++) version 7.0 or higher
Operating System: Windows, Linux, or macOS
C Standard: C99 or higher
C++ Standard: C++11 or higher
Learning Objectives
This project demonstrates:

C programming: Structs, file I/O, pointers, memory management
C++ programming: Classes, STL containers, algorithms, OOP
Hybrid programming: C/C++ interoperability with extern "C"
File operations: Binary file handling with fread/fwrite/fseek
Data structures: Vectors, sorting algorithms
Software design: Multi-file organization, separation of concerns
Build systems: Makefiles and batch scripts
Input validation: Robust error handling
Author
Capstone Project - Hybrid Inventory Manager C Backend + C++ Frontend Solution By  Parag Wanjare


License
Educational project for learning purposes.
