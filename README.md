
---

# Book Recommendation System

## Introduction
This project is a **Book Recommendation System** built using collaborative filtering techniques. It recommends books based on user input by leveraging similarity scores and displays a list of popular books. The system is implemented with **Flask** as the backend and **Bootstrap** for a responsive, clean UI. The recommendation model uses pre-trained data for efficient predictions.

## Features

- **Popular Books Display**: The homepage shows the top 50 popular books with their titles, authors, number of votes, and average ratings.
- **Book Recommendation**: Based on a user’s input, the system suggests similar books using a pre-trained similarity score model.
- **Interactive UI**: A Bootstrap-styled interface ensures an intuitive and responsive user experience.

## Dataset

- **Kaggle Link**: https://www.kaggle.com/datasets/arashnic/book-recommendation-dataset/data
  
The dataset includes:
- **Books**: Titles, authors, and images.
- **Ratings**: User ratings for various books.
- **User Data**: Anonymous user interaction data with books.

If you are using a publicly available dataset, mention its source, such as **Goodreads** or **Kaggle**. You can also include any preprocessing steps like data cleaning or modifications to the dataset.

## Methodology

1. **Data Preprocessing**:
   - A **pivot table** is created where rows represent users, columns represent books, and the values represent user ratings.
   - Missing values are handled by either imputing them with zeros or calculating the mean rating.

2. **Collaborative Filtering**:
   - The model uses **item-based collaborative filtering** to recommend books based on user ratings.
   - **Cosine Similarity** is computed to measure the similarity between books based on their rating patterns.

3. **Recommendation Generation**:
   - For a given book, cosine similarity scores with all other books are computed, and a list of top N most similar books is returned.

## Project Structure

```bash
.
├── app.py                     # Main Flask application
├── templates/
│   ├── index.html             # Template for the homepage (popular books)
│   └── recommend.html         # Template for the book recommendation page
├── static/
│   ├── css/
│   └── js/
├── models/
│   ├── popular.pkl            # Pre-trained model for popular books
│   ├── pt.pkl                 # Pickle file containing pivot table data
│   ├── books.pkl              # Pickle file containing book information
│   └── similarity_scores.pkl  # Pre-trained similarity score model
└── README.md                  # Project documentation
```

## Installation and Setup

### Prerequisites
Ensure the following libraries are installed:
```bash
pip install flask numpy pandas pickle-mixin scikit-learn
```

### Steps to Run the Application

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/yourusername/book-recommendation-system.git
   cd book-recommendation-system
   ```

2. **Install Dependencies**:
   Install the required Python packages by running:
   ```bash
   pip install -r requirements.txt
   ```

3. **Prepare Model Files**:
   Ensure the following files are available in the `models/` directory:
   - `popular.pkl`
   - `pt.pkl`
   - `books.pkl`
   - `similarity_scores.pkl`

4. **Run the Application**:
   Start the Flask development server:
   ```bash
   python app.py
   ```

5. **Access the Application**:
   Open your browser and navigate to:
   ```
   http://127.0.0.1:5000/
   ```

## Usage

### Home Page (Popular Books)
- The homepage lists the top 50 popular books with their:
  - Title
  - Author
  - Number of Votes
  - Average Rating

### Book Recommendation Page
1. Go to the "Recommend" page.
2. Enter a book title in the search bar.
3. Submit to receive book recommendations based on similarity. The results will display the titles, authors, and images of similar books.

## Model and Data Files

### Pre-trained Models:
- **Popular Books Model (`popular.pkl`)**: Contains data on the most popular books.
- **Pivot Table (`pt.pkl`)**: Used to compute book-to-book similarities.
- **Books Metadata (`books.pkl`)**: Includes information about book titles, authors, and images.
- **Similarity Scores (`similarity_scores.pkl`)**: Precomputed similarity scores between books for faster recommendations.

### Model Training:
- **Cosine Similarity** is used to compute the similarity between books based on user ratings.
- A **pivot table** is constructed from the user-book interaction data to calculate these similarity scores.

### Recommendation Example:
You can generate book recommendations with the following command:
```python
recommend('Book Title')
```

## Example Code for Recommendations

```python
import pickle

# Load pre-trained models
pt = pickle.load(open('models/pt.pkl', 'rb'))
books = pickle.load(open('models/books.pkl', 'rb'))
similarity_scores = pickle.load(open('models/similarity_scores.pkl', 'rb'))

# Function to recommend books
def recommend(book_title):
    # Logic to recommend books using similarity_scores
    pass
```

## Future Improvements

- **User-based Collaborative Filtering**: Extend the system to recommend books based on user preferences.
- **Hybrid Recommendation System**: Combine collaborative filtering with content-based filtering for better accuracy.
- **Enhanced UI**: Further improve the user experience with more dynamic features, possibly using **React.js** or **Vue.js**.

## Technologies Used

- **Backend**: Flask (Python)
- **Frontend**: HTML, CSS (Bootstrap)
- **Data Processing**: Numpy, Pandas, Scikit-learn
- **Model Persistence**: Pickle

## Contributing
Feel free to contribute by opening issues or submitting pull requests. Suggestions for improving the model or the UI are highly welcome!

## Screenshots

### Home Page (Popular Books)
<img width="1919" alt="Screenshot 2024-09-29 at 11 42 53" src="https://github.com/user-attachments/assets/ab98ede9-565a-47c2-90ac-a90312facf15">

### Book Recommendation Page
<img width="1920" alt="Screenshot 2024-09-29 at 11 43 41" src="https://github.com/user-attachments/assets/eb805b1b-63b8-47ad-89ca-737a28d00e9b">

---
