# CI2024_lab2: Traveling Salesman Problem (TSP)

This project contains my two solutions for the Traveling Salesman Problem (TSP), and a final test section to evaluate their performance on different datasets (cities of different countries, from the `cities` folder).

For all the provided solutions, the total cost of the tour is calculated as the sum of the distances between consecutive cities.\
A plot of the final tour is also generated for visualization.

## Solutions

I implemented two solutions for the TSP: a greedy algorithm and an Inver-Over crossover algorithm. Both solutions receive a distance matrix and a list of cities as input and return the best tour and its total cost.\
Both approaches don't guarantee the optimal solution, but the Inver-Over algorithm is more accurate than the greedy algorithm, even though it is much slower.

To optimize the final tour in the test section, I first run the greedy algorithm to get a good initial solution, and then I use the inver-over algorithm to improve it again.


### Solution 1: Greedy Algorithm

The greedy algorithm is a fast but approximate method for solving the TSP. It always chooses the nearest unvisited city until all cities are visited. The algorithm then returns to the starting city to complete the tour.\
To execute it on different instances, I created the function `greedy_tsp` that receives a distance matrix and a list of cities and returns the best tour and its total cost.

### Solution 2: Inver-Over Crossover Algorithm

The Inver-Over algorithm is a heuristic approach that combines inversion and crossover operations to evolve a population of solutions. It is slower but more accurate than the greedy algorithm.
The function `inver_over` receives an initial TSP tour, the distance matrix, and some optional parameters (population size, number of generations, and mutation probability). It returns the best tour and its total cost.

I chose the hyperparameters of the Inver-Over algorithm by executing it with different values and selecting the best ones.


## Tests

The final test block evaluates both solutions on the cities of all countries in the `cities` folder. It loads the cities, calculates the distance matrix, and runs both the greedy and inver-over algorithms. The results are logged for comparison.

### Test Script

```python
for file_name in os.listdir('cities'):
    logging.info(f"Processing {file_name}")
    # ...Load cities and compute distance matrix...
    # ...Run greedy algorithm...
    # ...Run inver-over algorithm...
    # ...Plot the final tours...
```

