---
date: 2026-07-06
tags:
  - informatica
  - pubblico

---
# Compilatore  
---  
Il software che traduce codice sorgente (C#, Rust, C++ etc.) in codice macchina binario.  
  
### Come funziona?  
La cosa si articola in fasi:  
  
1. Tu scrivi il codice.  
  
2. Il codice viene pulito dal preprocessore (preprocessing).  
  
3. Il codice viene tradotto in Assembly, un linguaggio a basso livello specifico per famiglie di CPU.  
  
4. L'assembler traduce il linguaggio Assembly in codice binario, e genera un file .obj o .o  
  
5. Il linker unisce il file oggetto con le librerie del sistema operativo. Risolve i collegamenti mancanti e impacchetta il tutto nel file finale (es. .exe).  
  
### Una tabella  
Diversi compilatori per diversi tipi di sistemi operativi, linguaggi o CPU:  
  
| **Compilatore**     | **Linguaggio** | **Sistema Operativo**    | **Estensione finale**              |
| ------------------- | -------------- | ------------------------ | ---------------------------------- |
| **MSVC**            | C, C++         | Windows                  | `.exe` / `.dll`                    |
| **GCC** / **Clang** | C, C++, Rust   | Linux                    | Nessuna                            |
| **Clang**           | C, C++, Swift  | macOS                    | Nessuna                            |
| **Roslyn**          | C#             | Windows / Cross-platform | `.exe` / `.dll`                    |
| **javac**           | Java           | Cross-platform           | `.class` / `.jar`                  |
| **go**              | Go             | Cross-platform           | `.exe` (Win) o Nessuna (Linux/Mac) |
| **rustc**           | Rust           | Cross-platform           | `.exe` (Win) o Nessuna (Linux/Mac) |
  
  
---