
# Degrees

This folder contains code and data for exploring relationships between movie actors using data inspired by IMDb. The main goal is to determine the shortest connection (degrees of separation) between two people based on the movies they have starred in.

## Folder Structure

- **large/**  
  Contains the full-size dataset with CSV files for people, movies, and their relationships.
- **small/**  
  Contains a smaller, easier-to-experiment-with version of the dataset.  
  *Recommended for testing and development.*

## Datasets

Both the `large` and `small` directories contain the following CSV files:

- `people.csv`  
  Each row: `id, name, birth`  
  Maps unique person IDs to actor names and birth years.

- `movies.csv`  
  Each row: `id, title, year`  
  Maps unique movie IDs to movie titles and release years.

- `stars.csv`  
  Each row: `person_id, movie_id`  
  Lists which people starred in which movies (by their IDs).

## Main Script: `degrees.py`

This script allows you to find the shortest path (degrees of separation) between two actors based on the movies they've appeared in together, directly or through intermediaries.

### How it Works

1. **Loads Data:**  
   Reads the CSV files from a specified directory into memory, creating dictionaries for quick lookup.
2. **Prompts for Names:**  
   User is asked to input two names. If multiple actors share a name, the program asks for clarification.
3. **Finds Shortest Path:**  
   Computes the shortest connection between the two people, where each step is a shared movie with another actor.
4. **Displays Path:**  
   Prints the sequence of movies and actors connecting the two people.

### Usage

In your terminal, run:

```bash
python degrees.py [directory]
```

- `[directory]` is optional (default is `large`).  
  For faster testing, you can use:

  ```bash
  python degrees.py small
  ```

Follow the prompts to enter the names of two actors.

### Example

```
Name: Kevin Bacon
Name: Tom Hanks
2 degrees of separation.
1: A Few Good Men (1992) starred Kevin Bacon and Tom Cruise
2: Apollo 13 (1995) starred Tom Cruise and Tom Hanks
```

## Implementation Notes

- The core logic for finding connections is in the `shortest_path` function of `degrees.py`.
- The data structures are optimized for quick lookups and graph traversal.
- If no connection exists between two people, the script reports `Not connected.`

## Requirements

- Python 3.x

No external dependencies are required.
