💊 Medicine-Recommender-System

End-to-end Machine Learning project that predicts disease prognosis from patient symptoms and provides a comprehensive recommendation system, including personalized precautions, medications, diet, and workout plans.

🧭 Project Navigation

💡 Introduction & Problem Statement

🧬 Dataset and Knowledge Base

⚙️ Setup & Dependencies

🔍 Data Exploration & Quality

🧠 Model Selection & Training

📈 Evaluation & Critical Analysis

💾 Model Persistence & Inference

✨ Recommendation System Core Logic

✅ Conclusion and Future Roadmap

1. 💡 Introduction & Problem Statement

This project builds a data-driven tool to assist in preliminary disease diagnosis. By leveraging machine learning, it aims to reduce reliance on manual knowledge and provide quick, actionable health advice.

Project Goal: To build a robust classification model (SVC) capable of predicting one of 41 disease outcomes based on patient symptoms.

Importance: Provides a proof-of-concept for integrating ML into early diagnostic workflows, coupling prognosis with actionable health recommendations (medications, precautions, etc.).

Methodology: The project strictly follows the iterative Data Science Lifecycle, from data acquisition and critical analysis to model deployment structuring.

2. 🧬 Dataset and Knowledge Base

The system relies on a dual data structure: a training dataset for the ML model and a knowledge base for recommendations.

Source of the Dataset: The dataset utilized for this project is the Medicine Recommendation System Dataset hosted on the Kaggle platform by the user noorsaeed.

Training Data (Training.csv): Contains 132 symptom features (one-hot encoded) and the target variable (prognosis).

Knowledge Base: Auxiliary CSV files (precautions.csv, medications.csv, diets.csv, etc.) providing corresponding advice for each disease.

Link to the Dataset:
https://www.kaggle.com/datasets/noorsaeed/medicine-recommendation-system-dataset
3. ⚙️ Setup & Dependencies

To reproduce the environment used for model training and analysis:

Environment: Primarily built for Google Colab, requiring Google Drive mounting for data access.

Key Libraries: Dependencies include pandas, numpy, and scikit-learn (versions are logged in Section 10.5 of the notebook).

Installation: Standard imports for data manipulation and ML utility functions (joblib, etc.).

4. 🔍 Data Exploration & Quality

Initial exploration is crucial to understanding the data's composition and quality.

Data Shape: Verification of $N$ samples and 133 columns (132 features + 1 target).

Unique Outcomes: Confirmation of 41 unique disease classes.

Data Quality Assessment: Critical analysis confirming that the data is largely pre-processed (one-hot encoded) with no missing values. This justifies proceeding directly to modeling without extensive manual feature engineering.

5. 🧠 Model Selection & Training

Target Encoding: The categorical prognosis column is encoded into numerical indices (0-40) using LabelEncoder.

Data Split: The dataset is split into training and testing sets using stratified sampling


Model Candidates: Initialization of several classification models (SVC, Random Forest, Gradient Boosting, etc.) for comparative evaluation.

6. 📈 Evaluation & Critical Analysis

Comparative Analysis: Models are trained and evaluated against the test set, with the Support Vector Classifier (SVC) being selected as the best candidate for deployment.

7.2 Technical Comment: Scrutinizing Perfect Precision: A critical analysis addresses the highly unusual result of perfect precision across all models. This suggests a potential data leakage or an overly simplistic mock dataset, emphasizing the need for validation using complex, real-world data.

7. 💾 Model Persistence & Inference

Model Persistence: The final SVC model and the LabelEncoder are saved using joblib for reproducibility and later retrieval.

Single-Sample Testing: Demonstration of preparing a single 1D feature vector using .reshape(1, -1) for inference.

Inverse Transformation: The rationale for why label_encoder.inverse_transform() is essential for converting the model's integer output back into a human-readable disease name.

8. ✨ Recommendation System Core Logic

This section defines the application layer that connects the ML prediction with the knowledge base.

Knowledge Base Loading: All auxiliary datasets (precautions, diets, medications, etc.) are loaded to form the system's knowledge base.

Mapping Dictionaries: Creation of the necessary lookup dictionaries (symptom name to numerical index, and encoded index to disease name).

Core Functions: Definition of the core functions: get_predicted_value() (handles prediction) and helper() (retrieves all associated recommendations).

System Demonstration: Execution of the final user-facing system, showing the structured output encompassing prognosis, description, precautions, medications, diet, and workout advice.

9. ✅ Conclusion and Future Roadmap

9.1 Project Summary and Achievement

The project successfully established a functional and highly accurate SVC-based prognostic system.

9.2 Critical Review and Data Integrity

The next stage must involve revalidation with a real-world, large-scale clinical dataset to confirm generalization performance beyond the current mock data.

9.3 Recommendations for System Advancement

Confidence Scoring: Integrate probability outputs to provide a confidence score alongside the prognosis.

Model Ensemble: Explore ensemble methods to improve robustness.

Deployment: Develop a user-friendly web interface for seamless symptom input.


👨‍💻 Author

Kalihose Migisha
Data Science Researcher | ML Enthusiast

📧 Email: Kalihosemigisha@gmail.com

🐦 X (Twitter): @KalihoseMigisha

💻 GitHub: @KalihoseMigisha

📜 License

This project is licensed under the Apache 2 License.
