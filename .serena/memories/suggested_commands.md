# Suggested Commands - Updated

## Dependency Management (uv - Recommended)
- `uv venv` - Create virtual environment
- `uv pip install -r requirements.txt` - Install all dependencies
- `uv pip install -e ".[dev]"` - Install with development dependencies
- `uv pip install -e ".[extra]"` - Install with extra optional dependencies
- `uv pip compile --upgrade requirements.txt` - Update dependencies
- `uv pip compile pyproject.toml -o requirements.txt` - Generate requirements from pyproject.toml

## Alternative Dependency Management (pip)
- `pip install -r requirements.txt` - Install dependencies
- `pip freeze > requirements.txt` - Generate requirements file
- `pip list` - List installed packages

## Virtual Environment
- `.venv\\Scripts\\activate` - Activate virtual environment (Windows)
- `source .venv/bin/activate` - Activate virtual environment (macOS/Linux)
- `deactivate` - Deactivate virtual environment

## Windows System Commands
- `dir` - List directory contents (equivalent to `ls` on Unix)
- `cd <path>` - Change directory
- `type <file>` - Display file contents (equivalent to `cat` on Unix)
- `find /i "pattern" <file>` - Search for pattern in file
- `findstr /s "pattern" *.py` - Search for pattern in Python files

## Git Commands
- `git status` - Check repository status
- `git add .` - Stage all changes
- `git commit -m "message"` - Commit changes
- `git push` - Push to remote repository
- `git pull` - Pull latest changes

## Jupyter Commands
- `jupyter notebook` - Start Jupyter Notebook server
- `jupyter lab` - Start JupyterLab server
- `jupyter notebook --no-browser --port=8888` - Start without browser

## Development Tools (if installed)
- `black .` - Code formatting
- `flake8 .` - Linting
- `pytest` - Testing

## Data Management
- No specific data pipeline commands identified
- Manual data download and processing through notebooks
- Data stored in organized directory structure