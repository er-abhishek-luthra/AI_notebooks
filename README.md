# Machine Learning Practice Repository

This repository contains my learning materials and practice implementations from various machine learning courses, primarily focusing on Andrew Ng's Machine Learning course on Coursera. The purpose of this repository is to:

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

### Course Content

#### 001 Supervised Learning
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

#### 002 Unsupervised Learning
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

## Requirements

- Python 3.x
- Jupyter Notebook
- Required packages (listed in each directory)
- Markdown viewer for mobile devices

## Setup

1. **Set Python Version**
   ```bash
   pyenv local 3.10.8
   ```

2. **Create Virtual Environment**
   ```bash
   python -m venv .venv
   ```

3. **Activate Environment**
   ```bash
   source .venv/bin/activate  # macOS/Linux
   .venv\Scripts\activate    # Windows
   ```

4. **Install Dependencies**
   ```bash
   pip install -r requirements.txt
   ```

5. **Setup Jupyter**
   ```bash
   pip install jupyter ipykernel
   python -m ipykernel install --user --name=python3.10.8 --display-name="Python 3.10.8"
   ```

For detailed explanations of these commands and additional setup options, refer to [HELPFUL_COMMANDS.md](HELPFUL_COMMANDS.md).

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