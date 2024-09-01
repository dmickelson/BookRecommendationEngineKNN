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
