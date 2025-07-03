# Code Style and Conventions

## File Organization
- **Notebooks**: Jupyter notebooks (.ipynb) for analysis and experimentation
- **Python modules**: Supporting .py files for reusable code
- **Data directories**: Organized by data source (edgar/, kaggle/, stooq/, etc.)

## Python Code Style
- **Import organization**: Standard library, third-party, then local imports
- **Variable naming**: snake_case for variables and functions
- **Class naming**: PascalCase for classes (e.g., `StrategyBase`, `Client`)
- **Constants**: UPPER_CASE (e.g., `API_URL`, `PATH`, `MARKET`, `TICKER`)

## Documentation
- **Minimal comments**: Focus on explaining why, not what
- **Reference links**: Include source URLs in comments (e.g., GitHub repos)
- **README files**: Present in main directories with explanations

## Code Patterns
- **Base classes**: Use inheritance (e.g., `StrategyBase` for trading strategies)
- **Error handling**: Basic exception handling with custom exception classes
- **Logging**: Print statements with timestamps and colored output
- **Configuration**: Hardcoded paths and parameters in notebooks/scripts

## Notebook Conventions
- **Cell structure**: Import cells at top, followed by configuration, then analysis
- **Output display**: Use `%matplotlib inline` and `%matplotlib widget`
- **Path handling**: Raw strings for Windows paths (r'path\\to\\file')

## No Formal Standards
- No linting configuration (no .pylintrc, .flake8, etc.)
- No formatting tools setup (no black, autopep8 config)
- No type hints usage observed
- No formal testing framework detected