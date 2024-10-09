# Set Cover Problem Optimization with Hill Climbing

## Approach
The optimization is performed using different variations of **Hill Climbing**. The general idea is to start with an initial solution (e.g., all sets selected) and iteratively improve it by removing or tweaking subsets, as long as the solution remains valid and improves the total cost.

### Key Components:
- **Initial Setup**: 
  - The universe and sets are generated based on the given parameters such as universe size, number of sets, and density.
  - Each set has a corresponding cost, calculated as a function of the number of elements it covers.
  
- **Hill Climbing Variants**:
  - **Simple Greedy Hill Climbing**: Removes sets iteratively, checking for validity and improvement in cost.
  - **Multiple Hill Climbing Trials**: Runs several independent trials to find the best solution out of multiple local optimizations.

### Functions:
- **valid(solution, SETS)**: Checks if the current solution covers the entire universe.
- **cost(solution, COSTS)**: Computes the total cost of the selected sets in the solution.

## Results
The optimization was tested on six different instances, each with varying universe sizes, number of sets, and densities. The best results obtained after running multiple trials of Hill Climbing are as follows:

| Instance | Universe Size | Number of Sets | Density | Best Cost          |
|----------|----------------|----------------|---------|--------------------|
| 1        | 100             | 10             | 0.2     | 249.55             |
| 2        | 1,000           | 100            | 0.2     | 6,814.93           |
| 3        | 10,000          | 1,000          | 0.2     | 128,233.79         |
| 4        | 100,000         | 10,000         | 0.1     | 1,961,179.84       |
| 5        | 100,000         | 10,000         | 0.2     | 2,148,258.66       |
| 6        | 100,000         | 10,000         | 0.3     | 2,184,626.04       |

### Observations:
- As the universe size and number of sets increase, the total cost increases significantly, indicating the complexity of larger instances.
- Multiple trials allow the algorithm to escape local minima, producing better results for larger problem instances.

## Conclusion
This project demonstrates the application of **Hill Climbing** to the Set Cover Problem. While it provides a simple and efficient solution for smaller instances, more sophisticated algorithms (e.g., Simulated Annealing, Tabu Search) may be required for larger or more complex instances to avoid local minima and improve global optimization.
