# Book Recommendation Engine using KNN

In this challenge, you will create a book recommendation algorithm using K-Nearest Neighbors.

You will use the Book-Crossings dataset. This dataset contains 1.1 million ratings (scale of 1-10) of 270,000 books by 90,000 users.

After importing and cleaning the data, use NearestNeighbors from sklearn.neighbors to develop a model that shows books that are similar to a given book. The Nearest Neighbors algorithm measures the distance to determine the “closeness” of instances.

Create a function named get_recommends that takes a book title (from the dataset) as an argument and returns a list of 5 similar books with their distances from the book argument.

## Approach

1. Data Loading and Preprocessing:

- Load the datasets (books, ratings, users) using pandas.
- Merge the datasets to create a comprehensive dataframe.
- Filter out users with less than 200 ratings and books with less than 100 ratings.
- Create a pivot table with users as rows, books as columns, and ratings as values.

2. Feature Engineering:

- Convert the pivot table to a sparse matrix using csr_matrix for efficiency.
- Use the book titles as features for the recommendation system.

3. Model Creation:

- Initialize the NearestNeighbors model from sklearn.neighbors.
- Fit the model with the sparse matrix of book ratings.

4. Recommendation Function:

- Create the get_recommends function that takes a book title as input.
- Find the index of the input book in the dataset.
- Use the fitted NearestNeighbors model to find the 6 nearest neighbors (including the input book).
- Extract the book titles and distances for the top 5 recommendations.
- Format the output as specified in the challenge description.

5. Testing and Visualization (Optional):

- Test the get_recommends function with the provided example.
- Create visualizations to explore the dataset, such as rating distributions or user activity.
