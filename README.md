# genetic-algorithm-best-individual

A from-scratch genetic algorithm in Python that searches for the best individual for a two-variable function, without using any evolutionary-computation library.

## How it works

- **Chromosome:** 10 bits. The first 5 bits encode `x` and the last 5 bits encode `y`, each decoded to a value in the range -5 to 5.
- **Fitness:** the inverse of the heuristic `(cos(x) + sin(y))^2 / (x^2 + y^2)`, with `x` and `y` in degrees and a tiny constant added to avoid division by zero.
- **Population:** 10 randomly generated chromosomes.
- **Selection:** the two fittest individuals are taken as parents each generation.
- **Crossover:** gene-wise exchange between the parents with probability 0.7.
- **Mutation:** each bit is flipped with probability 0.3.
- **Replacement:** the offspring replace the weakest individuals when both are fitter than the current worst.
- **Stop condition:** the loop ends when the best fitness exceeds 60.

The script prints the initial population as a table, then one row per generation with the best chromosome, its decoded `x` and `y`, and its fitness.

## Tech stack

- Python 3 (standard library only: `math`, `random`)

## Structure

```
evolution_GA.py   chromosome encoding, fitness, crossover, mutation and the main loop
```

## Run it

```bash
python evolution_GA.py
```

Results differ between runs because the population is random.
