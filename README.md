# Timetable Scheduling Genetic Algorithm: Comprehensive README

## Problem Description:
The task is to solve a timetable scheduling problem in university environments, ensuring minimal conflicts between sections, professors, and rooms. 

## Constraints:
### Hard Constraints:
1. Classes must be scheduled in available classrooms.
2. Classrooms must accommodate sections.
3. Professors cannot have overlapping lectures.
4. Same section cannot be in multiple rooms simultaneously.
5. Rooms cannot be assigned to different sections simultaneously.
6. Professors cannot teach more than three courses.
7. No section can have more than five courses per semester.
8. Each course must have two lectures per week, not on the same or adjacent days.
9. Lab lectures must be in two consecutive slots.
10. Fifteen-minute breaks between consecutive classes.

### Soft Constraints:
1. Theory classes in the morning, labs in the afternoon.
2. Minimize floors traversed.
3. Consistent room allocation throughout the week.
4. Longer teaching blocks for professors.

## Implementation Overview:
The project, implemented in Python, uses a genetic algorithm approach.

### Functions Overview:

#### 1. `initialize_population(populationSize)`:
   - **Purpose**: Initializes the population with random binary-encoded chromosomes.
   - **Description**: Generates chromosomes representing potential timetables.
   - **Parameters**:
     - `populationSize`: Size of the population to be initialized.
   - **Returns**: List of binary-encoded chromosomes representing the initial population.

#### 2. `selection(fitness_values, num_parents)`:
   - **Purpose**: Implements tournament selection to choose the best individuals for reproduction.
   - **Description**: Randomly selects individuals and chooses the best ones based on fitness values.
   - **Parameters**:
     - `fitness_values`: List of fitness values corresponding to each chromosome.
     - `num_parents`: Number of parent chromosomes to be selected.
   - **Returns**: Indices of the selected parent chromosomes.

#### 3. `crossover(parent1, parent2)`:
   - **Purpose**: Performs single-point crossover between two parent chromosomes.
   - **Description**: Swaps genetic information between parents to generate offspring.
   - **Parameters**:
     - `parent1`: First parent chromosome for crossover.
     - `parent2`: Second parent chromosome for crossover.
   - **Returns**: Two offspring chromosomes.

#### 4. `mutate(chromosome, mutation_rate=0.01)`:
   - **Purpose**: Introduces random mutations in a chromosome.
   - **Description**: Flips the value of genes randomly to maintain genetic diversity.
   - **Parameters**:
     - `chromosome`: Chromosome to be mutated.
     - `mutation_rate`: Rate of mutation.
   - **Returns**: Mutated chromosome.

#### 5. `crossover_and_mutate(parents)`:
   - **Purpose**: Combines crossover and mutation operations to generate offspring.
   - **Description**: Applies crossover followed by mutation to produce new chromosomes.
   - **Parameters**:
     - `parents`: Parent chromosomes for reproduction.
   - **Returns**: Offspring chromosomes.

#### 6. `decode_chromosome(chromosome)`:
   - **Purpose**: Converts binary chromosomes into human-readable timetables.
   - **Description**: Decodes binary representation to extract course, professor, room, and scheduling details.
   - **Parameters**:
     - `chromosome`: Binary-encoded chromosome representing a timetable.
   - **Returns**: Human-readable timetable.

#### 7. `evaluate_fitness(chromosome, timetable, section_strength)`:
   - **Purpose**: Calculates fitness based on constraints violations.
   - **Description**: Evaluates timetable fitness considering hard and soft constraints.
   - **Parameters**:
     - `chromosome`: Binary-encoded chromosome representing a timetable.
     - `timetable`: Human-readable timetable decoded from the chromosome.
     - `section_strength`: Strength of the section for room capacity calculation.
   - **Returns**: Fitness value of the timetable.

#### 8. `visualize_timetable(population, fitness_values, generation)`:
   - **Purpose**: Provides visual representation of timetables and professor assignments for each generation.
   - **Description**: Creates visualizations of timetables and professor assignments using matplotlib.
   - **Parameters**:
     - `population`: List of chromosomes representing the population.
     - `fitness_values`: List of fitness values corresponding to each chromosome in the population.
     - `generation`: Current generation number.
   - **Returns**: None.

#### 9. `genetic_algorithm(population_size, num_generations)`:
   - **Purpose**: Orchestrates the genetic algorithm by selecting parents, generating offspring, and evaluating fitness.
   - **Description**: Runs the genetic algorithm to find the optimal timetable.
   - **Parameters**:
     - `population_size`: Size of the population.
     - `num_generations`: Number of generations.
   - **Returns**: None.
## Summary:

The Timetable Scheduling Genetic Algorithm project aims to solve the complex problem of creating optimized university timetables while adhering to various constraints. The README provides a comprehensive overview of the problem, constraints, and the genetic algorithm-based solution implemented in Python. Here's a summary of the key points:

- **Problem Description**: The project addresses the classical timetable scheduling problem encountered in university environments, ensuring minimal conflicts between sections, professors, and rooms.

- **Constraints**: 
  - **Hard Constraints**: These are non-negotiable constraints that must be satisfied without compromise, including room availability, professor assignments, and course scheduling.
  - **Soft Constraints**: These are preferences or recommendations that can be compromised to some extent, such as scheduling theory classes in the morning and labs in the afternoon.

- **Implementation Overview**: 
  - The project uses a genetic algorithm approach to find optimal timetables.
  - Various functions are implemented to initialize the population, perform selection, crossover, mutation, decode chromosomes, evaluate fitness, visualize timetables, and orchestrate the genetic algorithm.

- **Functions Overview**: Each function serves a specific purpose in the genetic algorithm workflow, including population initialization, parent selection, crossover, mutation, fitness evaluation, visualization, and algorithm execution.

- **README Content**: The README includes detailed descriptions of each function, explaining their purpose, parameters, and return values.

- **Summary**: The project offers a systematic and scalable solution to the timetable scheduling problem, leveraging genetic algorithms to produce optimized timetables while considering both hard and soft constraints.

Overall, the project provides a robust framework for addressing real-world scheduling challenges in educational institutions, offering flexibility and efficiency in timetable creation.
