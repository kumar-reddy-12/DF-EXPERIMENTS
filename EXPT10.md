# Ex. No. 10 — Use Ghidra to Disassemble and Analyze Malware Code

## Digital Forensics Lab

### Aim 

**Ghidra** is a software reverse-engineering framework that can be used to disassemble and analyze binary programs.

This experiment demonstrates how to use Ghidra to load a binary file, perform automatic analysis, examine functions, inspect strings and imports, analyze decompiled code, and identify possible malware-related characteristics.

The main objectives are:

* Disassemble and analyze a binary using Ghidra.
* Recognize common malware-related functionality.
* Identify possible persistence mechanisms.
* Examine anti-analysis techniques.
* Analyze possible network communication.
* Interpret low-level assembly and understand higher-level program behavior.

> **Safety Note:** Use only benign or controlled sample binaries for this laboratory exercise. Do not execute unknown malware on a normal personal computer.

---

# Requirements

The following are required:

* Ghidra
* Java Runtime Environment
* Windows / Linux / macOS system
* Isolated virtual machine (recommended)
* Benign sample binary or controlled test binary
* Hex dump (optional)
* GitHub repository

The experiment recommends using a virtualized environment and benign or safely controlled sample binaries.

---

# 1. Set Up the Analysis Environment

## 1.1 Install Ghidra

Download and install Ghidra on the analysis system.

Verify that the required Java environment is available.

For example:

```bash
java -version
```

---

## 1.2 Use an Isolated Environment

For malware-analysis experiments, use an isolated virtual machine whenever possible.

Example setup:

```text
Host Computer
     |
     └── Virtual Machine
          |
          ├── Ghidra
          ├── Java
          └── Benign Sample
```

The analysis environment should be isolated from important personal or production systems.

<img width="1280" height="720" alt="WhatsApp Image 2026-09-23 at 9 36 56 PM" src="https://github.com/user-attachments/assets/87d2fd35-249f-41a5-928f-f6afb8913a27" />


# 2. Prepare the Sample Binary

Use a **benign binary**, controlled sample, or hex dump for the experiment.

Example:

```text
samples/
├── benign_sample1.bin
└── benign_sample2.hex
```

The lab document specifically recommends safe, benign binaries or hex dumps rather than live malware.

---

# 3. Create a Ghidra Project

Open Ghidra and create a new project.

### Steps

1. Launch Ghidra.
2. Select **File → New Project**.
3. Select the appropriate project type.
4. Choose a project directory.
5. Enter a project name.
6. Click **Finish**.

Example project name:

```text
Ghidra-Malware-Analysis
```

<img width="1280" height="426" alt="WhatsApp Image 2026-09-23 at 9 36 57 PM" src="https://github.com/user-attachments/assets/f946cc55-abc8-4b8b-a91e-40b5a12f85b1" />


# 4. Import the Binary

Import the sample binary into the Ghidra project.

### Steps

1. Open the Ghidra project.
2. Select **File → Import File**.
3. Select the sample binary.
4. Review the detected file format.
5. Select the appropriate processor/language if required.
6. Click **OK**.

Example:

```text
samples/benign_sample1.bin
```

---

# 5. Start Automatic Analysis

After importing the binary:

1. Double-click the imported program.
2. Ghidra will open the **CodeBrowser**.
3. Start the automatic analysis.
4. Keep the appropriate analysis options enabled.
5. Start the analysis.
6. Wait for Ghidra to complete processing.

Automatic analysis helps identify:

* Functions
* Entry points
* Strings
* References
* Instructions
* Control-flow information

The experiment specifically includes loading a binary, performing automatic analysis, and identifying entry points as part of the initial analysis.

<img width="1280" height="720" alt="WhatsApp Image 2026-09-23 at 9 36 57 PM (1)" src="https://github.com/user-attachments/assets/a8d78f76-e056-4342-a5a5-e680f9625e86" />


# 6. Identify the Entry Point

After analysis, examine the program's entry point.

The entry point provides an initial location from which program execution can be examined.

Look for:

```text
Entry Point
Functions
Instructions
References
```

Use Ghidra's navigation and listing views to understand how execution begins.

---

# 7. Analyze Functions

Use the **Symbol Tree** or function listing to locate functions.

Example:

```text
Functions
├── entry
├── main
├── function_001
├── function_002
└── ...
```

For each important function, examine:

* Function name
* Parameters
* Return value
* Called functions
* Calling functions
* Instructions
* Cross-references

The experiment recommends identifying and analyzing critical functions and using Ghidra's cross-referencing features.

---

# 8. Examine the Decompiler

Open the **Decompiler** window for an analyzed function.

The decompiler converts assembly instructions into a higher-level representation that can make program logic easier to understand.

Example workflow:

```text
Assembly
   ↓
Function
   ↓
Decompiler
   ↓
High-Level Program Logic
```

Examine:

* Conditional statements
* Loops
* Function calls
* Variables
* Parameters
* Return values

Use the decompiled representation together with the assembly view rather than relying on the decompiler alone.

---

# 9. Use Cross-References

Cross-references help determine where a function, string, or address is being used.

For example:

```text
String
   ↓
XREF
   ↓
Function
   ↓
Caller
```

Use cross-references to determine relationships between different parts of the program.

This can help identify functions associated with:

* File operations
* Registry operations
* Network operations
* Process operations
* Other system functionality

---

# 10. Analyze Strings

Use Ghidra's **Defined Strings** or string-related views to locate readable strings inside the binary.

Look for strings such as:

```text
http://
https://
cmd.exe
powershell
User-Agent
registry
temp
```

These strings are only indicators and should be investigated in context.

A useful analysis record can be:

```text
String:
http://example.test

Reference:
function_001

Observation:
Possible network-related string
```

The lab document specifically includes string analysis as a method for locating information related to potentially malicious behavior.

---

# 11. Analyze Imports

Examine the binary's imported functions.

Depending on the binary, imports may provide clues about functionality such as:

```text
File Operations
Network Communication
Registry Operations
Process Creation
Memory Operations
```

Create an investigation table:

| Imported Function    | Category    | Observation                        |
| -------------------- | ----------- | ---------------------------------- |
| File-related API     | File System | Possible file operation            |
| Network-related API  | Network     | Possible communication             |
| Registry-related API | Registry    | Possible configuration/persistence |
| Process-related API  | Process     | Possible process creation          |

Imported functions should be interpreted in context because an API's presence alone does not prove malicious behavior.

---

# 12. Analyze Possible Persistence Mechanisms

Examine the binary for functions and strings associated with persistence.

Possible areas to investigate include:

```text
Registry modifications
Startup locations
Scheduled tasks
Services
Configuration files
```

The objective is to identify whether the program contains functionality that could allow it to remain active across system restarts.

The project objectives specifically include recognizing persistence mechanisms.

---

# 13. Analyze Anti-Analysis Techniques

Examine the code for possible techniques designed to make analysis more difficult.

Examples to investigate include:

```text
Obfuscated strings
Unusual control flow
Packed code
Debugger checks
Environment checks
```

Do not classify a technique as malicious solely because it is unusual. Examine its implementation and context.

The experiment includes advanced analysis topics such as obfuscation detection.

---

# 14. Analyze Possible Network Communication

Search strings and imported functions for possible network-related functionality.

Look for:

```text
URLs
IP addresses
Domain names
Network APIs
Socket-related functions
HTTP-related strings
```

Example investigation:

```text
Indicator:
https://example.test

Referenced By:
function_004

Observation:
Possible network communication
```

Network-related functionality is one of the behavioral areas identified in the experiment.

---

# 15. Examine the Control Flow

Ghidra can display control-flow information for functions.

A simplified example:

```text
        ┌──────────────┐
        │ Function A   │
        └──────┬───────┘
               │
        ┌──────▼───────┐
        │ Condition    │
        └───┬──────┬───┘
            │      │
          Yes      No
            │      │
      ┌─────▼─┐  ┌─▼─────┐
      │ Func B│  │ Func C│
      └───────┘  └───────┘
```

Use control-flow information to understand how execution moves between functions and code blocks.

---

# 16. Advanced Analysis

The project can optionally include advanced Ghidra capabilities.

These include:

* Dynamic analysis
* Control-flow graphs
* Custom Python scripts
* Custom Java scripts
* Obfuscation detection
* P-Code analysis
* Runtime analysis

The uploaded experiment lists these as advanced techniques for future or extended analysis.

---

# 17. Ghidra Scripts

Ghidra scripts can automate repetitive analysis tasks.

Possible scripts include:

```text
scripts/
├── extract_strings.py
├── network_analysis.py
└── label_functions.py
```

The experiment proposes scripts for:

* Extracting and listing string references
* Identifying network-related functions
* Identifying common malware indicators
* Labeling functions and data segments

<img width="1600" height="900" alt="WhatsApp Image 2026-09-23 at 9 37 20 PM" src="https://github.com/user-attachments/assets/f377f641-5776-4fbc-9cba-676386883261" />
<img width="1600" height="900" alt="WhatsApp Image 2026-09-23 at 9 37 18 PM" src="https://github.com/user-attachments/assets/1f567d5b-ef61-4580-982f-91b0765bb642" />


# Result

The binary file was successfully loaded and analyzed using **Ghidra**.

Functions, strings, imports, and decompiled code were examined to understand the program's behavior and identify possible malware-related characteristics.

---

