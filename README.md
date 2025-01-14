# Cereal Classification Project

This project involves classifying cereals based on their nutritional content using the K-Nearest Neighbors (KNN) algorithm. The dataset includes various features such as sugars, carbohydrates, proteins, fats, sodium, fiber, potassium, and calories.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

## Installation

1. Clone the repository:
    ```sh
    git clone https://github.com/userofpi/cereal-classification.git
    ```
2. Navigate to the project directory:
    ```sh
    cd cereal-classification
    ```
3. Install the required dependencies:
    ```sh
    pip install -r requirements.txt
    ```

## Usage

1. Load the dataset:
    ```python
    data = pd.read_csv('platki_dane_zad4.csv', sep=';', header=0)
    ```
2. Preprocess the data:
    ```python
    data['producent'] = data['producent'].astype('category').cat.codes
    ```
3. Split the data into training, validation, and test sets:
    ```python
    X_train, X_walidacyjne, y_train, y_walidacyjne = train_test_split(X, y, test_size=0.6, random_state=42)
    X_walidacyjne, X_test, y_walidacyjne, y_test = train_test_split(X_walidacyjne, y_walidacyjne, test_size=0.5, random_state=42)
    ```
4. Train the KNN classifier:
    ```python
    knn = KNeighborsClassifier(n_neighbors=3, metric='manhattan')
    knn.fit(X_train, y_train)
    ```
5. Evaluate the model:
    ```python
    y_pred = knn.predict(X_walidacyjne)
    print(accuracy_score(y_walidacyjne, y_pred))
    print(confusion_matrix(y_walidacyjne, y_pred))
    print(classification_report(y_walidacyjne, y_pred))
    ```

## Contributing

Contributions are welcome! Please follow these steps to contribute:

1. Fork the repository.
2. Create a new branch:
    ```sh
    git checkout -b feature/your-feature-name
    ```
3. Commit your changes:
    ```sh
    git commit -m 'Add some feature'
    ```
4. Push to the branch:
    ```sh
    git push origin feature/your-feature-name
    ```
5. Open a pull request.

## License

Distributed under the MIT License. See `LICENSE` for more information.

## Contact


Project Link: [https://github.com/userofpi/cereal-classification](https://github.com/userofpi/cereal-classification)
