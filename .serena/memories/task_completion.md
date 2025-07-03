# Task Completion Guidelines - Updated

## When Task is Completed

### Dependency Management
- **Check dependencies**: Ensure all required packages are in requirements.txt and pyproject.toml
- **Virtual environment**: Verify setup works with `uv venv` and `uv pip install -r requirements.txt`
- **Compatibility**: Test with both uv and pip installation methods

### Testing and Quality
- **Notebook execution**: Ensure all cells run without errors
- **Data consistency**: Verify data processing results
- **Visualization quality**: Check plots and charts render correctly
- **Code organization**: Maintain consistent file structure

### Development Tools (Optional)
- **Code formatting**: Run `black .` if black is installed
- **Linting**: Run `flake8 .` if flake8 is installed
- **Testing**: Run `pytest` if tests are available

### Documentation Updates
- Update relevant README files if adding new analysis
- Add comments explaining new methodologies
- Document data sources and assumptions
- Update dependency lists if new packages added

### Version Control
- Commit changes with descriptive messages
- Push to repository after verification
- Consider branching for experimental features

## Quality Checks
- **Environment setup**: Verify `uv venv` and `uv pip install -r requirements.txt` works
- **Package compatibility**: Check for version conflicts
- **Cross-platform**: Ensure setup works on Windows, macOS, Linux
- **Documentation accuracy**: README instructions match actual setup

## Modern Development Setup
- **pyproject.toml**: Used for modern Python packaging standard
- **requirements.txt**: Maintained for compatibility
- **uv package manager**: Recommended for faster dependency resolution
- **Development dependencies**: Available via `.[dev]` extra

## Current Workflow
1. Develop in Jupyter notebooks
2. Extract reusable code to .py modules
3. Update dependencies in pyproject.toml
4. Generate requirements.txt using uv
5. Test environment setup
6. Manual testing through notebook execution
7. Visual verification of results
8. Git commit and push