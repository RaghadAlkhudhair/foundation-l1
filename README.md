# Foundation L1 - Programming Course

This repository contains programming foundation course materials and examples.

## Setup

### Prerequisites
- Python 3.8 or higher
- VS Code or Cursor IDE
- Git

### Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd foundation-l1
```

2. Create a virtual environment:
```bash
python -m venv venv
```

3. Activate the virtual environment:
```bash
# Windows
venv\Scripts\activate

# macOS/Linux
source venv/bin/activate
```

4. Install dependencies:
```bash
pip install -r requirements.txt
```

## AI Auto Complete Setup

This project is configured with AI auto complete support:

### VS Code/Cursor Extensions
The following extensions are recommended (see `.vscode/extensions.json`):
- Python extension
- GitHub Copilot
- GitHub Copilot Chat
- Black Formatter
- Pylint
- Markdown All in One

### Features Enabled
- **GitHub Copilot**: AI-powered code suggestions
- **Inline Suggestions**: Real-time code completion
- **Parameter Hints**: Function parameter suggestions
- **Auto Import**: Automatic import suggestions
- **Code Formatting**: Black formatter integration
- **Linting**: Pylint and Flake8 integration

### Usage
1. Open any Python file
2. Start typing - AI suggestions will appear automatically
3. Press `Tab` to accept suggestions
4. Use `Ctrl+Space` (Windows/Linux) or `Cmd+Space` (macOS) for manual suggestions

## Course Structure

- `01_intro_to_programming.md` - Introduction to programming concepts
- `02_hello_world.md` - Your first program
- `03_reading_input.md` - User input handling
- `04_variables.md` - Variables and data types
- `05_operators.md` - Mathematical and logical operators
- `06_if_statements.md` - Conditional statements
- `07_while_loops.md` - While loops
- `08_for_loops.md` - For loops
- `09_nested_loops.md` - Nested loop structures
- `10_switch_statements.md` - Switch/case statements
- `11_debugging.md` - Debugging techniques
- `12_functions.md` - Function definitions and usage
- `13_projects.md` - Practical projects

## Development

### Code Formatting
```bash
black .
isort .
```

### Linting
```bash
pylint foundation-l1/
flake8 foundation-l1/
```

### Type Checking
```bash
mypy foundation-l1/
```

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Run tests and linting
5. Submit a pull request

## License

This project is licensed under the MIT License.

