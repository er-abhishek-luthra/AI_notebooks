# Helpful Commands for Project Setup

This document contains essential commands and their detailed explanations for setting up Python projects. Each command includes its purpose, usage, and important notes.

## Python Version Management (pyenv)

```bash
# List all installed Python versions
pyenv versions
```
**Explanation:**
- Shows all Python versions installed via pyenv
- The currently active version is marked with an asterisk (*)
- Useful for verifying available versions before installation

```bash
# Install a specific Python version
pyenv install 3.10.8
```
**Explanation:**
- Downloads and installs the specified Python version
- Version 3.10.8 is recommended for this project
- May take a few minutes to complete installation
- Requires build dependencies to be installed first

```bash
# Set Python version for current directory
pyenv local 3.10.8
```
**Explanation:**
- Creates/updates `.python-version` file in current directory
- Sets Python version only for this project
- Takes precedence over global version
- Ensures consistent Python version across team members

```bash
# Set global Python version
pyenv global 3.10.8
```
**Explanation:**
- Sets default Python version for all projects
- Affects all directories without local version
- Use with caution as it affects all projects
- Recommended to use `pyenv local` instead for project-specific versions

## Virtual Environment Management

```bash
# Create a new virtual environment
python -m venv .venv
```
**Explanation:**
- Creates isolated Python environment in `.venv` directory
- Copies Python interpreter and pip
- Creates necessary directory structure:
  ```
  .venv/
  ├── bin/          # Contains activation scripts
  ├── include/      # Contains Python headers
  ├── lib/          # Contains Python packages
  └── pyvenv.cfg    # Virtual environment configuration
  ```
- `.venv` is a common convention for virtual environment directory

```bash
# Activate virtual environment (macOS/Linux)
source .venv/bin/activate
```
**Explanation:**
- Activates the virtual environment
- Modifies shell prompt to show `(.venv)`
- Changes PATH to use virtual environment's Python
- Isolates package installations to this environment
- Must be run in the project directory

```bash
# Activate virtual environment (Windows)
.venv\Scripts\activate
```
**Explanation:**
- Windows-specific activation command
- Same functionality as macOS/Linux version
- Uses Windows path separator
- Must be run in Command Prompt or PowerShell

```bash
# Deactivate virtual environment
deactivate
```
**Explanation:**
- Returns to system Python environment
- Removes virtual environment from PATH
- Restores original shell prompt
- Useful when switching between projects

```bash
# Check if virtual environment is active
echo $VIRTUAL_ENV  # macOS/Linux
echo %VIRTUAL_ENV% # Windows
```
**Explanation:**
- Shows path to active virtual environment
- Returns empty if no virtual environment is active
- Useful for verifying environment status
- Different syntax for different operating systems

## Package Management (pip)

```bash
# Upgrade pip
pip install --upgrade pip
```
**Explanation:**
- Updates pip to latest version
- Recommended before installing packages
- Helps avoid compatibility issues
- Should be run in virtual environment

```bash
# Install packages from requirements.txt
pip install -r requirements.txt
```
**Explanation:**
- Installs all packages listed in requirements.txt
- Maintains exact versions specified
- Creates dependency tree
- Essential for project reproducibility

```bash
# Install a specific package
pip install package_name
```
**Explanation:**
- Installs latest compatible version
- Can be used for individual packages
- Automatically resolves dependencies
- Example: `pip install numpy`

```bash
# Install a package with specific version
pip install package_name==version
```
**Explanation:**
- Installs exact package version
- Ensures compatibility
- Example: `pip install numpy==1.24.3`
- Useful for reproducible environments

```bash
# List all installed packages
pip list
```
**Explanation:**
- Shows all installed packages and versions
- Includes dependencies
- Useful for auditing environment
- Helps identify outdated packages

```bash
# Generate requirements.txt
pip freeze > requirements.txt
```
**Explanation:**
- Creates/updates requirements.txt
- Lists all installed packages with versions
- Includes all dependencies
- Essential for project documentation

```bash
# Show package information
pip show package_name
```
**Explanation:**
- Displays detailed package information
- Shows version, location, dependencies
- Useful for troubleshooting
- Example: `pip show numpy`

```bash
# Uninstall packages not in requirements.txt
pip freeze | grep -v -f requirements.txt | xargs pip uninstall -y
```
**Explanation:**
- Lists all installed packages (`pip freeze`)
- Excludes packages in requirements.txt (`grep -v -f requirements.txt`)
- Uninstalls remaining packages (`xargs pip uninstall -y`)
- `-y` flag automatically confirms uninstallation
- Useful for cleaning up unused packages
- **Note:** Be careful with this command as it will uninstall all packages not listed in requirements.txt

## Jupyter Notebook Setup

```bash
# Install Jupyter
pip install jupyter
```
**Explanation:**
- Installs Jupyter Notebook and dependencies
- Required for interactive development
- Includes notebook server
- Should be installed in virtual environment

```bash
# Install Jupyter kernel
pip install ipykernel
```
**Explanation:**
- Installs Jupyter kernel package
- Required for Python kernel
- Enables notebook execution
- Part of Jupyter ecosystem

```bash
# Register a new kernel
python -m ipykernel install --user --name=python3.10.8 --display-name="Python 3.10.8"
```
**Explanation:**
- Creates new Jupyter kernel
- Links to current Python environment
- Makes kernel available in notebooks
- `--user` flag installs for current user only

```bash
# List available kernels
jupyter kernelspec list
```
**Explanation:**
- Shows all installed Jupyter kernels
- Displays kernel names and locations
- Useful for kernel management
- Helps identify available environments

```bash
# Remove a kernel
jupyter kernelspec uninstall kernel_name
```
**Explanation:**
- Removes specified Jupyter kernel
- Cleans up kernel files
- Useful for removing old environments
- Example: `jupyter kernelspec uninstall python3.10.8`

## Common Issues and Solutions

### Package Installation Issues
```bash
# Clear pip cache
pip cache purge
```
**Explanation:**
- Removes cached package files
- Helps resolve corrupted downloads
- Frees disk space
- Useful when packages fail to install

```bash
# Force reinstall package
pip install --force-reinstall package_name
```
**Explanation:**
- Reinstalls package regardless of version
- Useful for fixing corrupted installations
- Ignores existing installation
- Example: `pip install --force-reinstall numpy`

```bash
# Install with verbose output
pip install -v package_name
```
**Explanation:**
- Shows detailed installation process
- Helps identify installation issues
- Displays dependency resolution
- Useful for debugging

### Virtual Environment Issues
```bash
# Remove and recreate virtual environment
rm -rf .venv
python -m venv .venv
source .venv/bin/activate
```
**Explanation:**
- Complete reset of virtual environment
- Removes all installed packages
- Creates fresh environment
- Useful when environment is corrupted

### Jupyter Issues
```bash
# Reset Jupyter configuration
jupyter notebook --generate-config
```
**Explanation:**
- Creates new Jupyter config file
- Resets to default settings
- Useful for fixing configuration issues
- Creates `~/.jupyter/jupyter_notebook_config.py`

```bash
# Clear Jupyter cache
jupyter cache clear
```
**Explanation:**
- Removes cached notebook outputs
- Clears temporary files
- Helps with notebook performance
- Useful when notebooks behave unexpectedly

## Best Practices

1. **Always use virtual environments**
   - Isolates project dependencies
   - Prevents conflicts between projects
   - Makes project portable
   - Essential for reproducibility

2. **Keep requirements.txt updated**
   - Document all dependencies
   - Specify version constraints
   - Update when adding packages
   - Enable easy project setup

3. **Use version control**
   - Track all project files
   - Ignore virtual environment
   - Document setup steps
   - Enable collaboration

4. **Regular maintenance**
   - Update packages periodically
   - Check for security updates
   - Clean up unused packages
   - Test after updates

Remember to replace placeholder values (like `package_name`, `version`, etc.) with actual values when using these commands. 