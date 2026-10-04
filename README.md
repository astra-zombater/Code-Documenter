# Python Code Documentation Generator

A lightweight Python utility that automatically collects source-code files from a project and generates a professionally formatted **Microsoft Word (`.docx`) documentation file**.

The tool is designed to make project documentation easier by allowing users to document an entire project directory or select individual files. It uses a simple command-line interface with optional native file/folder selection dialogs.

## Features

* Generate documentation for an entire project folder
* Select specific files to document
* Native folder selection dialog
* Native multi-file selection dialog
* Automatically scans supported source/configuration files
* Preserves the original source code
* Uses **Consolas** monospace formatting for code
* Generates a `.docx` documentation file automatically
* Ignores unnecessary directories such as virtual environments and Git folders
* Works with or without Tkinter
* Automatically saves the generated documentation inside the selected project directory

## Supported File Types

The generator currently processes:

```text
.py
.json
.yaml
.yml
.md
.sql
.html
.css
```

These extensions are defined directly in the project configuration.

## Ignored Directories

The following directories are automatically skipped when scanning a project:

```text
venv
.venv
__pycache__
.git
build
dist
.idea
.vscode
```

This prevents unnecessary files and generated project data from being included in the documentation.

## How It Works

The program follows a simple workflow:

```text
Start Program
     │
     ▼
Choose Documentation Mode
     │
     ├── 1. Current Directory
     │
     ├── 2. Select Project Folder
     │
     └── 3. Select Specific Files
             │
             ▼
       Read Source Files
             │
             ▼
      Format Source Code
             │
             ▼
     Generate Word Document
             │
             ▼
 Project_Documentation.docx
```

The main program provides three modes:

1. **Document current directory**
2. **Choose a specific project folder**
3. **Select specific files**

The default option documents the current working directory.

## Requirements

* Python 3.8 or newer
* `python-docx`
* Tkinter *(optional, but recommended for graphical file/folder selection)*

## Installation

Clone the repository:

```bash
git clone https://github.com/YOUR_USERNAME/python-code-documentation-generator.git
```

Move into the project directory:

```bash
cd python-code-documentation-generator
```

Install the required dependency:

```bash
pip install python-docx
```

> Tkinter is normally included with standard Python installations on Windows. If it is unavailable, the program automatically falls back to command-line path input.

## Usage

Run the program:

```bash
python documentor_v3_fnl.py
```

You will see:

```text
==================================================
       PYTHON CODE DOCUMENTATION GENERATOR
==================================================
1. Document current directory (Default)
2. Choose a specific folder...
3. Select specific file(s)...

Enter choice (1/2/3, default is 1):
```

### Option 1 — Current Directory

Select:

```text
1
```

The program scans the current directory and its subdirectories for supported files.

The generated document will be:

```text
Project_Documentation.docx
```

### Option 2 — Select Project Folder

Select:

```text
2
```

A folder-selection window will open when Tkinter is available.

After selecting a project folder, the program scans it recursively while ignoring unnecessary directories.

### Option 3 — Select Specific Files

Select:

```text
3
```

A multi-file selection dialog allows you to choose individual files.

Only the selected files will be included in the generated documentation.

## Generated Documentation

The generated Word document contains:

* A project documentation title
* A heading for each processed file
* The complete source code of each file
* Monospace code formatting
* File paths when scanning folders

Each source file is added to the document as a separate section.

Example:

```text
Project Source Code Documentation

File: main.py
--------------------------------
<source code>

File: utils/helper.py
--------------------------------
<source code>

File: config.json
--------------------------------
<configuration>
```

## Project Structure

A minimal repository can look like this:

```text
python-code-documentation-generator/
│
├── documentor_v3_fnl.py
├── README.md
└── Project_Documentation.docx
```

The generated `.docx` file does not need to be committed to GitHub unless you specifically want to distribute an example output.

## Technical Overview

The project is built around three main components.

### 1. Documentation Generator

`generate_code_docs()` creates the Word document, scans the requested directory/files, filters supported extensions, and adds each file's contents to the document.

### 2. File and Folder Selection

The project uses Tkinter's native dialogs when available:

* `askdirectory()` for folder selection
* `askopenfilenames()` for selecting multiple files

If Tkinter is unavailable, the application falls back to terminal-based path input.

### 3. Command-Line Interface

The `main()` function provides the application's interactive menu and determines which documentation mode should be used.

## Error Handling

The application includes basic handling for file-reading errors. If a file cannot be read, the generated document receives an error message instead of stopping the entire documentation process.

## Use Cases

This tool can be useful for:

* University programming projects
* Software project submissions
* Creating source-code documentation
* Preparing project reports
* Code review
* Archiving project source code
* Creating documentation for presentations
* Quickly combining multiple source files into one Word document

## Limitations

The current version focuses on **source-code collection and formatting** rather than automatic code analysis.

It does not currently:

* Generate detailed function/class documentation
* Create UML diagrams
* Analyze dependencies
* Generate API documentation
* Automatically explain the code
* Generate a table of contents
* Extract Git history
* Convert documentation to PDF

These could be added in future versions.

## Future Improvements

Possible future enhancements include:

* [ ] Automatic table of contents
* [ ] Syntax highlighting
* [ ] Function and class extraction
* [ ] Code statistics
* [ ] Line numbering
* [ ] PDF export
* [ ] HTML documentation
* [ ] Markdown documentation
* [ ] Automatic project structure tree
* [ ] Git integration
* [ ] Searchable documentation
* [ ] GUI interface
* [ ] Custom document templates
* [ ] Dark/light themes
* [ ] Automatic README generation

## Contributing

Contributions are welcome.

1. Fork the repository
2. Create a new branch

```bash
git checkout -b feature/your-feature
```

3. Make your changes
4. Commit your changes

```bash
git commit -m "Add new feature"
```

5. Push the branch

```bash
git push origin feature/your-feature
```

6. Open a Pull Request

## License

This project is available under the **MIT License**.

You may use, modify, and distribute the project according to the terms of the license.



⭐ If you find this project useful, consider giving the repository a star!
