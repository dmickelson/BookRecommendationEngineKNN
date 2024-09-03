# Book Recommendation Engine using KNN

This project implements a book recommendation algorithm using K-Nearest Neighbors (KNN) on the Book-Crossings dataset. The dataset contains 1.1 million ratings (scale of 1-10) of 270,000 books by 90,000 users.

## Project Overview

The goal is to develop a model that recommends books similar to a given book using the Nearest Neighbors algorithm. This algorithm measures the distance between data points to determine the "closeness" of instances, making it suitable for recommendation systems.

## Approach

1. **Data Loading and Preprocessing**

   - Load books, ratings, and users datasets using pandas
   - Merge datasets to create a comprehensive dataframe
   - Apply filters:
     - Users with at least 200 ratings
     - Books with at least 100 ratings
   - Create a pivot table: users as rows, books as columns, ratings as values

2. **Feature Engineering**

   - Convert the pivot table to a sparse matrix (csr_matrix) for computational efficiency
   - Use book titles as features for the recommendation system

3. **Model Creation**

   - Initialize NearestNeighbors model from sklearn.neighbors
   - Fit the model with the sparse matrix of book ratings

4. **Recommendation Function**

   - Implement `get_recommends` function:
     - Input: book title
     - Output: list of 5 similar books with their distances
   - Process:
     - Locate the index of the input book
     - Use the fitted NearestNeighbors model to find the 6 nearest neighbors (including the input book)
     - Extract and format the top 5 recommendations

5. **Testing and Validation**
   - Test the `get_recommends` function with sample inputs
   - Implement a test function to verify the correctness of recommendations

## Implementation Details

The core of the project is the `get_recommends` function:

```python
def get_recommends(book_title):
    # Implementation details here
    pass

# Example usage
books = get_recommends("Where the Heart Is (Oprah's Book Club (Paperback))")
print(books)

# Test function
def test_book_recommendation():
    test_pass = True
    recommends = get_recommends("Where the Heart Is (Oprah's Book Club (Paperback))")
    if recommends[0] != "Where the Heart Is (Oprah's Book Club (Paperback))":
        test_pass = False
    # Additional test cases can be added here
    return test_pass
```
