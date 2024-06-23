# Project: Parallel Image Comparison Algorithm

## Part 1: Algorithm Development 

### Task 1: Pixel Difference Calculation
**Algorithm 1**: Compute the difference between two pixel values `x` and `y` as \((x - y)^2\).

### Task 2: Sum of Differences for 1D Arrays
**Algorithm 2**: Calculate the sum of differences between two 1D arrays `X[]` and `Y[]` using Algorithm 1.
- Use multithreading and MPI to parallelize the computation.
- Sum of differences is given by:
  \[
  Ed1 = \sum_{i=0}^{N} (x_i - y_i)^2
  \]

### Task 3: Sum of Differences for 2D Arrays
**Algorithm 3**: Calculate the sum of differences between two 2D arrays `X[][]` and `Y[][]` using Algorithm 2.
- Use multithreading and MPI for parallel computation.
- Sum of differences is given by:
  \[
  Ed2 = \sum_{i=0}^{M} \sum_{j=0}^{N} (x_{ij} - y_{ij})^2
  \]

### Task 4: Image Comparison
**Algorithm 4**: Load two images, convert them into 2D arrays, and apply Algorithm 3 to compare them (use OpenCV).

### Task 5: Percentage Distance Calculation
**Algorithm 5**: Compute the Percentage Distance Value using the result from Algorithm 3.
- Formula:
  \[
  \text{Percentage Distance Value} = \frac{Ed2}{N \times M}
  \]
- `N` and `M` are the width and height of the arrays, respectively.

## Part 2: Image Comparison with Dataset (30%)

### Task 1: Dataset Selection
- Identify a suitable dataset (e.g., Kaggle, MNIST, CIFAR).
- Ensure dataset images are of the same type, size, and context.
- Discuss dataset suitability with the teaching team.

### Task 2: Data Reading and Visualization
- Investigate methods to read and visualize the dataset using C++.
- Use libraries like OpenCV or customized binary data reading mechanisms.

### Task 3: Data Structures and Variables
- Use appropriate data structures, variables, and labels for the program.

### Task 4: Parallel Image Comparison
- Execute Algorithm 5 to compare one image with a dataset in parallel using multithreading and MPI.
- Compare returned Percentage Distance Values to find the minimum value.
- Identify the closest training image to the test image.
- Display the Confidence of Result using the formula:
  \[
  \text{Confidence} = 1 - \left( \frac{\text{Min(Percentage Distance Values)}}{\text{Sum(Percentage Distance Values)} \times (\text{No. of Training Elements})} \right)
  \]
  - Min(Percentage Distance Values): Minimum value among returned Percentage Distance Values.
  - Sum(Percentage Distance Values): Sum of all returned Percentage Distance Values.
  - No. of Training Elements: Number of elements the algorithm trained on during comparison.
