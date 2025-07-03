# Design Patterns and Guidelines

## Architecture Patterns

### Strategy Pattern
- `StrategyBase` class provides common interface for trading strategies
- Subclasses implement specific trading logic
- Clean separation of concerns for backtesting framework

### Client Pattern
- API clients (e.g., FinnhubClient) encapsulate external service interactions
- Consistent error handling and response processing
- Session management for HTTP requests

### Utility Modules
- Separate utility functions in dedicated modules
- Shared functionality extracted from notebooks
- Print and analysis functions for common operations

## Data Processing Patterns

### File-Based Storage
- CSV as primary data format
- Organized directory structure by data source
- Manual data management without database

### Notebook-Driven Development
- Analysis in Jupyter notebooks
- Iterative exploration and visualization
- Documentation through markdown cells

### API Integration
- Custom clients for external data sources
- Error handling with custom exceptions
- Configurable parameters for different endpoints

## Code Organization

### Separation of Concerns
- Data collection separated from analysis
- Visualization logic in dedicated cells/functions
- Reusable components extracted to modules

### Configuration Management
- Hardcoded configuration in notebooks
- Path constants defined at notebook level
- No central configuration system

## Anti-Patterns to Avoid
- Avoid mixing data collection and analysis in same notebook
- Don't hardcode API keys in source code
- Minimize code duplication across notebooks
- Avoid complex nested directory structures

## Best Practices Observed
- Reference original sources in comments
- Use descriptive variable names
- Maintain consistent import organization
- Include visual verification of results