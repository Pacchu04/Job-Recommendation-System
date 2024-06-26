# Job-Recommendation-System

## Project Description
Content-based filtering leverages the textual content of job descriptions to compute similarities between jobs using TF-IDF vectorization and cosine similarity. The recommendations can be enhanced by incorporating user feedback, making them more personalized and relevant. This method ensures that job recommendations are tailored to the user's interests and previous interactions with the system.

## What is a Job Recommendation System?

![image](https://github.com/Pacchu04/Job-Recommendation-System/assets/92878457/dda20c18-29f8-4ffb-93e2-5b8da6977907)

A recommendation system or recommender system, is a subclass of information filtering system that seeks to predict the “rating” or “preference” a user would give to an item. The goal of a recommendation system is to generate meaningful recommendations to a collection of users for items or products that might interest them.

There are mainly two types of filtering techniques in Recommendation Systems namely: 
* Content-based filtering : Content-based filtering is a recommendation technique that suggests items (such as articles, movies, or jobs) to users based on the characteristics or "content" of those items. Instead of relying on the preferences or behavior of other users, it focuses on the specific features or attributes of the items themselves.
  
* Collaborative filtering: Collaborative filtering is a recommendation technique that predicts a user's interests or preferences based on the preferences and behaviors of other users. It relies on the idea that people who have agreed in the past will agree in the future.

## Methodology
I Build a job recommendation engine using content-based filtering techniques.

* Data Pre-processing and Meta-data creation
* Vectorization
* Measuring similarities between skill vectors
* Enhanced Recommendations with User Feedback

### Data Pre-processing

Since job recommendation systems deal with finding relevant jobs mainly based on one’s skill sets, therefore retrieving the skills from different jobs given is an important task.
![Design Process Flowchart](https://github.com/Pacchu04/Job-Recommendation-System/assets/92878457/fb742d6a-83bc-4b16-8846-2b6152cc37fb)

### Vectorization

Vectorization refers to the computation and generation of vectors based on the words present in a string. Here, a function called the text to vector() was used to convert the input text string to its corresponding vector such that the two vectors can be compared to understand the similarity between two text strings. This is done by importing the Counter library to count all the words in the given text.

### Measuring Similarities between skill vectors

Different similarity metrics such as Cosine (Orchini), City block, and Euclidean require vectorization of the skill query input and the job-based skills for searching job options where the user skills are available and then search similar jobs based on the top match.

### Cosine similarity  
Measure of similarity between two non-zero vectors in an inner product space that measures the cosine of the angle between them. It is used to determine how similar two documents (or vectors) are to each other.

### Mathematical Formula:
![Cosine-similarity-formula](https://github.com/Pacchu04/Job-Recommendation-System/assets/92878457/371086d2-fb18-4278-8a5f-1ce23dff83c6)

* A⋅B is the dot product of the vectors 𝐴 and B
* ∥A∥ is the magnitude (or length) of vector 𝐴
* ∥B∥ is the magnitude (or length) of vector 𝐵

