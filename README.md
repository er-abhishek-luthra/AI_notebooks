# Machine Learning Practice Repository

This repository contains my learning materials and practice implementations from various machine learning courses, primarily focusing on Andrew Ng's Machine Learning course on Coursera.

## Table of Contents
- [Purpose](#purpose)
- [Project Structure](#project-structure)
- [Course Content](#course-content)
- [Getting Started](#getting-started)
- [Setup Guide](#setup-guide)
  - [Requirements](#requirements)
  - [Additional Packages](#additional-packages)
  - [Installation Steps](#installation-steps)
  - [Notebook Output Handling](#notebook-output-handling)
- [Mobile Access](#mobile-access)
- [Contributing](#contributing)
- [License](#license)

## Purpose

The purpose of this repository is to:
1. Document my learning journey in machine learning
2. Maintain organized practice implementations
3. Keep track of course materials and notes
4. Create a reference for future ML projects
5. Share learning resources with others

## Project Structure

```
MLNotebooks/
├── 001_supervised_learning/
│   ├── 001_regression/
│   │   ├── labs/                   # Practice implementations and examples
│   │   │   ├── data/              # Lab datasets
│   │   │   ├── images/            # Lab images and plots
│   │   │   └── *.ipynb            # Lab notebooks
│   │   └── notes/                 # Concept notes and summaries
│   │
│   └── 002_classification/
│       ├── labs/                   # Practice implementations
│       └── notes/                  # Concept notes
│
└── 002_unsupervised_learning/
    ├── labs/                       # Practice implementations
    └── notes/                      # Concept notes
```

## Organization

Each main directory contains:
- `labs/`: Practice implementations and examples
  - Contains lab notebooks, datasets, and supporting files
  - Organized by topic and difficulty level
  - Includes all necessary resources (data, images, code snippets)
- `notes/`: Concept notes and summaries
  - Contains detailed explanations of concepts
  - Includes Evernote notes converted to Markdown
  - Organized by topic

## Course Content

### 001 Supervised Learning
- **001 Regression**
  - Linear Regression with One Variable
    - Cost function
    - Gradient descent
    - Feature scaling
  - Linear Regression with Multiple Variables
    - Multiple features
    - Polynomial regression
    - Normal equation

- **002 Classification**
  - Logistic Regression
    - Binary classification
    - Decision boundaries
    - Regularization
  - Neural Networks: Representation
    - Neural network architecture
    - Forward propagation
    - Activation functions

### 002 Unsupervised Learning
- Neural Networks: Learning
  - Backpropagation
  - Cost functions
  - Gradient checking
- Machine Learning System Design
  - Error analysis
  - Cross validation
  - Learning curves

## Getting Started

1. Clone this repository
2. Navigate to the specific concept directory
3. Follow the structure:
   - Start with `notes/` for concept understanding
   - Practice with `labs/` for hands-on implementation
   - All resources are included within the labs directory

## Setup Guide

### Requirements

- [Anaconda](https://www.anaconda.com/products/distribution) (recommended) or [Miniconda](https://docs.conda.io/en/latest/miniconda.html)
- Git for version control
- A text editor or IDE (e.g., VSCode, PyCharm)

### Additional Packages

Depending on your specific needs, you might need to install additional packages:

1. **Deep Learning**
   ```bash
   pip install tensorflow>=2.15.0  # For deep learning
   ```

2. **Data Processing**
   ```bash
   pip install pandas  # For data manipulation
   pip install seaborn  # For statistical visualizations
   ```

3. **Image Processing**
   ```bash
   pip install opencv-python  # For computer vision
   pip install pillow  # For image processing
   ```

### Installation Steps

1. **Install Anaconda**
   - Download and install Anaconda from [https://www.anaconda.com/products/distribution](https://www.anaconda.com/products/distribution)
   - Verify installation:
     ```bash
     conda --version
     ```

2. **Clone Repository**
   ```bash
   git clone https://github.com/yourusername/your-repo.git
   cd your-repo
   ```

3. **Create and Activate Conda Environment**
   ```bash
   # Create environment from environment.yml
   conda env create -f environment.yml

   # Activate the environment
   conda activate ainotebooks
   ```

4. **Verify Installation**
   ```bash
   # Check Python version
   python --version

   # Check if key packages are installed
   python -c "import tensorflow; print(tensorflow.__version__)"
   python -c "import numpy; print(numpy.__version__)"
   ```

### Managing the Environment

1. **Daily Usage**
   ```bash
   # Activate the environment
   conda activate ainotebooks

   # Deactivate when done
   conda deactivate
   ```

2. **Installing Additional Packages**
   ```bash
   # Using conda
   conda install package_name

   # Using pip (if package not available in conda)
   pip install package_name
   ```

3. **Updating Packages**
   ```bash
   # Update all packages
   conda update --all

   # Update specific package
   conda update package_name
   ```

4. **Environment Management**
   ```bash
   # List all environments
   conda env list

   # Export environment
   conda env export > environment.yml

   # Remove environment
   conda env remove --name ainotebooks
   ```

5. **Updating Environment with New Dependencies**
   ```bash
   # Update the environment with new dependencies from environment.yml
   conda env update --file environment.yml --prune
   ```

### Running Jupyter Notebooks

1. **Start Jupyter**
   ```bash
   # Make sure your environment is activated
   conda activate ainotebooks

   # Start Jupyter Notebook
   jupyter notebook
   ```

2. **Select Kernel**
   - In your notebook, select Kernel → Change kernel → Python [conda env:ainotebooks]

### Notebook Output Handling

To keep the repository clean and avoid committing unnecessary notebook outputs (like large data, images, or sensitive information), we use `nbstripout`. This tool automatically strips output cells from Jupyter notebooks before committing them to version control.

#### Setting up nbstripout

1. **Install nbstripout** (already included in requirements.txt)
   ```bash
   pip install -r requirements.txt
   ```

2. **Install Git Hook**
   ```bash
   nbstripout --install
   ```
   This will automatically strip outputs whenever you commit notebooks.

3. **Configure Git Attributes**
   Create or update `.gitattributes` in the repository root:
   ```
   *.ipynb filter=nbstripout
   ```

4. **Optional: Customize nbstripout Configuration**
   Create `.nbstripout` in the repository root to customize what gets stripped:
   ```json
   {
       "keep_output": false,
       "keep_count": false,
       "keep_id": false,
       "keep_metadata": false
   }
   ```

#### Manual Usage

If you need to strip outputs manually:
```bash
nbstripout notebook.ipynb
```

#### Benefits
- Keeps repository size small
- Prevents committing sensitive data
- Makes notebook diffs cleaner and more meaningful
- Ensures consistent notebook state across different environments

### Troubleshooting

1. **Package Conflicts**
   - If you encounter package conflicts, try:
     ```bash
     conda install package_name=version
     ```
   - Or update your environment.yml and recreate the environment

2. **Kernel Issues**
   - If Jupyter doesn't recognize your environment:
     ```bash
     python -m ipykernel install --user --name=ainotebooks
     ```

3. **Environment Problems**
   - If your environment becomes corrupted:
     ```bash
     # Remove and recreate
     conda env remove --name ainotebooks
     conda env create -f environment.yml
     ```

## Mobile Access

For offline access:
1. Clone the repository
2. Use a Markdown reader app
3. All notes and code will be available offline
4. Images and diagrams are stored locally
5. Each directory's content is self-contained

## Contributing

Feel free to:
- Fork this repository
- Use the code and notes for your learning
- Suggest improvements or corrections
- Share your own implementations

## License

This project is for educational purposes. All course materials and implementations are based on the respective course content. 