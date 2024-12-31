# Semantic Similarity Project

This repository contains starter code for a semantic similarity project, which explores vector-based representations of word semantics. The project calculates the similarity between words using cosine similarity and evaluates the model's performance on a set of test questions. This project is part of ESC180 (Introduction to Computer Programming at the University of Toronto.

---

## Features

- **Vector Operations**: Functions to calculate the norm of vectors and cosine similarity between them.
- **Semantic Descriptor Construction**: Builds semantic descriptors from sentences or files.
- **Similarity Testing**: Evaluates the accuracy of semantic similarity models using a test set (e.g., TOEFL questions).

---

### Functionality Overview

The code offers several functionalities to analyze and compare word meanings:

*   **Vector Norm Calculation (`norm(vec)`)**

    Computes the norm (magnitude) of a vector represented as a dictionary. This helps quantify the overall strength of the semantic representation.

*   **Cosine Similarity (`cosine_similarity(vec1, vec2)`)**

    Calculates the cosine similarity between two word vectors based on their co-occurrence counts. This metric reflects how closely the semantic profiles of two words align.

*   **Building Semantic Descriptors (`build_semantic_descriptors(sentences)`)**

    Constructs a dictionary representing the semantic context for each word in a list of sentences. It tracks how often words appear alongside other words within the same sentence.

*   **Building Semantic Descriptors from Files (`build_semantic_descriptors_from_files(filenames)`)**

    Reads text files, cleans the content, and extracts sentences and words. It then calls `build_semantic_descriptors` to create semantic representations for each word.

*   **Finding the Most Similar Word (`most_similar_word(word, choices, semantic_descriptors, similarity_fn)`)**

    Given a word, a list of potential synonyms (choices), a dictionary of semantic descriptors, and a similarity function, identifies the word in the "choices" list that is most semantically similar to the given word.

*   **Running Similarity Test (`run_similarity_test(filename, semantic_descriptors, similarity_fn)`)**

    Evaluates the accuracy of the system on a provided test file. The test file contains lines with a question word, an answer word, and a set of other words (choices). This function uses the semantic descriptors and similarity function to find the most similar word to the question word from the choices within each line. It then calculates the percentage of correctly identified answers.
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
