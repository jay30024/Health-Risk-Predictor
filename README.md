# Health-Risk-Predictor

1. Introduction 

The Health Risk Predictor is a comprehensive machine learning system designed to assess patient health risks based on demographic, vital, and lifestyle data. The system combines traditional ML classification with modern embedding-based similarity search and natural language explanations to provide actionable, interpretable health risk assessments. 

2. Problem Statement 

Healthcare providers face challenges in quickly and consistently assessing patient health risks. Manual assessment methods are time-consuming and can vary between practitioners. There is a need for an automated, explainable system that can provide reliable risk categorization while maintaining transparency in its decision-making process. 

3. Solution Overview 

The Health Risk Predictor addresses these challenges through: 

1. Machine Learning classification for risk prediction 

2. Patient profile embeddings for similarity search 

3. Natural language explanations for transparency 

4. Comprehensive input validation and output guardrails 

4. Technical Architecture 

4.1 Data Layer 

The system uses synthetic patient data with 13 health features including age, gender, BMI, blood pressure, cholesterol, glucose, smoking status, exercise frequency, and medical history. 

4.2 Embedding Layer 

Patient profiles are converted to text descriptions and encoded using the sentence-transformers library (all-MiniLM-L6-v2 model), producing 384-dimensional embeddings for similarity search. 

4.3 Vector Store 

FAISS (Facebook AI Similarity Search) is used to efficiently store and query patient embeddings, enabling rapid identification of similar patient profiles. 

4.4 ML Model 

A Random Forest Classifier with 100 estimators is trained on the patient data to predict risk categories: Low, Moderate, High, and Critical. 

4.5 Explanation Engine 

Template-based natural language generation provides human-readable explanations of risk factors and their contribution to the overall assessment. 

5. Key Features 

5.1 Patient Profile Embeddings 

The system converts patient data into dense vector representations, enabling semantic similarity search. This allows finding patients with comparable health profiles, providing valuable context for risk assessment. 

5.2 Risk Categorization 

Patients are categorized into four risk levels: 

1. Low (0-25%): Healthy profile with minimal risk factors 

2. Moderate (25-50%): Some factors require attention 

3. High (50-75%): Multiple elevated risk factors 

4. Critical (75-100%): Immediate attention recommended 

5.3 Natural Language Explanations 

Each prediction is accompanied by a human-readable explanation that describes the key factors contributing to the risk assessment, making the system transparent and interpretable. 

5.4 Guardrails 

The system implements comprehensive safety measures: 

1. Input Validation: Range and type checking for all patient data 

2. Category Validation: Ensures valid options for categorical fields 

3. Confidence Thresholds: Alerts for low-confidence predictions 

4. Feature Importance: Transparent display of contributing factors 

6. Sample Assessment Output 

For a 55-year-old male patient with BMI 28.5, blood pressure 145/92, cholesterol 245, and former smoking history, the system provides: 

1. Risk Level: MODERATE 

2. Confidence: 68.5% 

3. Key Factors: Age (significant), Cholesterol (high), Blood Pressure (elevated) 

4. Similar Patients: 3 found with comparable profiles 

5. Explanation: Multiple factors contribute to elevated health risks. Lifestyle modifications recommended.
