# Semantic Similarity Project

This repository contains starter code for a semantic similarity project, which explores vector-based representations of word semantics. The project calculates the similarity between words using cosine similarity and evaluates the model's performance on a set of test questions. This project is part of ESC180 (Introduction to Computer Programming at the University of Toronto.

---

## Features

- **Vector Operations**: Functions to calculate the norm of vectors and cosine similarity between them.
- **Semantic Descriptor Construction**: Builds semantic descriptors from sentences or files.
- **Similarity Testing**: Evaluates the accuracy of semantic similarity models using a test set (e.g., TOEFL questions).

---

## Code Overview

### `norm(vec)`
Calculates the Euclidean norm of a vector represented as a dictionary.

### `cosine_similarity(vec1, vec2)`
Computes the cosine similarity between two vectors.

### `build_semantic_descriptors(sentences)`
Builds a dictionary of semantic descriptors from a list of tokenized sentences.

### `build_semantic_descriptors_from_files(filenames)`
Processes text files to build semantic descriptors. Converts text into sentences, tokenizes words, and calculates co-occurrences.

### `most_similar_word(word, choices, semantic_descriptors, similarity_fn)`
Returns the most semantically similar word from a list of choices, based on a given similarity function.

### `run_similarity_test(filename, semantic_descriptors, similarity_fn)`
Evaluates the performance of the semantic similarity model on a test dataset. Reports the percentage of correct guesses.

---

## Example Usage

### Step 1: Build Semantic Descriptors
```python
sem_descriptors = build_semantic_descriptors_from_files(["book1.txt", "book2.txt"])
```

### Step 2: Run Similarity Test
```python
accuracy = run_similarity_test("TOEFL_questions.txt", sem_descriptors, cosine_similarity)
print(f"{accuracy}% of the guesses were correct")
```

---

## Input File Formats

- **Text Files**: Input files for `build_semantic_descriptors_from_files()` should contain text. Sentences are split by `.`, `!`, or `?`.
- **Test Files**: Input for `run_similarity_test()` should have lines in the format:
  ```
  <word> <correct_choice> <choice1> <choice2> ... <choiceN>
  ```
