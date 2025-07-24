# Crop Yield Prediction Pipeline

A comprehensive machine learning pipeline for predicting maize crop yields using historical field data, climate information, and agronomic management practices.

## 🎯 Project Overview

This project implements an end-to-end ML pipeline to help farmers make informed decisions about their maize crops by predicting yield based on various factors including:

- Historical field data
- Climate conditions
- Agronomic management practices
- Soil characteristics

## 🚀 Quick Start

### Prerequisites
- Python 3.8+
- pip

### Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd crop-yield-predictor
   ```

2. **Create and activate virtual environment**
   ```bash
   # Windows
   python -m venv venv
   .\venv\Scripts\Activate.ps1
   
   # Linux/Mac
   python -m venv venv
   source venv/bin/activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Verify installation**
   ```bash
   python test_installation.py
   ```

## 📁 Project Structure

```
crop-yield-predictor/
├── src/                           # Main source code
│   ├── __init__.py
│   ├── data_pipeline.py          # Data loading and preprocessing
│   ├── feature_engineering.py    # Feature creation and engineering
│   ├── model.py                  # ML model training and evaluation
│   ├── api.py                    # FastAPI endpoints
│   └── config.py                 # Configuration management
├── tests/                        # Unit tests
├── data/                         # Data storage (gitignored)
├── models/                       # Trained models (gitignored)
├── notebooks/                    # Jupyter notebooks
├── requirements.txt              # Python dependencies
├── .gitignore                   # Git ignore rules
└── README.md                    # This file
```

## 🔧 Development Setup

### Jupyter Notebook
The project includes a Jupyter kernel for interactive development:

```bash
# Activate virtual environment
.\venv\Scripts\Activate.ps1

# Start Jupyter
jupyter notebook
```

### Code Quality
The project includes development tools for code quality:

- **Black**: Code formatting
- **Flake8**: Linting
- **MyPy**: Type checking
- **Pre-commit**: Git hooks

## 📊 Dataset

The primary dataset is from Kaggle:
- [Crop Yield Prediction Dataset](https://www.kaggle.com/datasets/patelris/crop-yield-prediction-dataset)

## 🏗️ Architecture

### Data Pipeline
- Data loading and validation
- Missing value handling
- Data type validation
- Logging and monitoring

### Feature Engineering
- Climate feature extraction
- Soil characteristic features
- Agronomic practice features
- Temporal features

### Model Development
- Multiple algorithm comparison (Random Forest, Linear Regression)
- Hyperparameter optimization
- Cross-validation strategies
- Performance metrics (RMSE, R², MAE)

### API Development
- FastAPI-based REST API
- Input validation
- Health check endpoints
- Prediction endpoints

## 🧪 Testing

Run tests with pytest:
```bash
pytest tests/
```

## 📈 Metrics

The model evaluation focuses on:
- **RMSE**: Root Mean Square Error
- **R²**: Coefficient of determination
- **MAE**: Mean Absolute Error

## 🚀 Deployment

### Local Development
```bash
# Start the API server
uvicorn src.api:app --reload
```

### Docker (Optional)
```bash
# Build and run with Docker
docker build -t crop-yield-predictor .
docker run -p 8000:8000 crop-yield-predictor
```

## 📝 License

This project is part of the Kilimo technical assessment.

## 🤝 Contributing

This is a technical assessment project. For questions or issues, please refer to the project requirements.

---

**Note**: This project emphasizes code quality, modular architecture, and reasoning over completeness. Focus on demonstrating best practices and clean, maintainable code.
