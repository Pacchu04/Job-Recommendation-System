# Job-Recommendation-System

## Project Description
Content-based filtering leverages the textual content of job descriptions to compute similarities between jobs using TF-IDF vectorization and cosine similarity. The recommendations can be enhanced by incorporating user feedback, making them more personalized and relevant. This method ensures that job recommendations are tailored to the user's interests and previous interactions with the system.

## What is a Job Recommendation System?

![image](https://github.com/Pacchu04/Job-Recommendation-System/assets/92878457/dda20c18-29f8-4ffb-93e2-5b8da6977907)

A recommendation system or recommender system, is a subclass of information filtering system that seeks to predict the “rating” or “preference” a user would give to an item. The goal of a recommendation system is to generate meaningful recommendations to a collection of users for items or products that might interest them.

There are mainly two types of filtering techniques in Recommendation Systems namely: 
* Content-based filtering : Content-based filtering is a recommendation technique that suggests items (such as articles, movies, or jobs) to users based on the characteristics or "content" of those items. Instead of relying on the preferences or behavior of other users, it focuses on the specific features or attributes of the items themselves.
  
* Collaborative filtering: Collaborative filtering is a recommendation technique that predicts a user's interests or preferences based on the preferences and behaviors of other users. It relies on the idea that people who have agreed in the past will agree in the future.

## 1. Job Recommendation using Content-based filtering
### Project Notebook file: 
https://github.com/Pacchu04/Job-Recommendation-System/blob/main/Content-based%20filtering.ipynb
### Methodology
I Build a job recommendation engine using content-based filtering techniques.

* Data Pre-processing and Meta-data creation
* Vectorization
* Measuring similarities between skill vectors
* Enhanced Recommendations with User Feedback

### [Dataset](https://github.com/Pacchu04/Job-Recommendation-System/blob/main/datasets/job_final.csv)
### Data Pre-processing

Since job recommendation systems deal with finding relevant jobs mainly based on one’s skill sets, therefore retrieving the skills from different jobs given is an important task.
![Design Process Flowchart](https://github.com/Pacchu04/Job-Recommendation-System/assets/92878457/fb742d6a-83bc-4b16-8846-2b6152cc37fb)

### 1. Vectorization

Vectorization refers to the computation and generation of vectors based on the words present in a string. Here, a function called the text to vector() was used to convert the input text string to its corresponding vector such that the two vectors can be compared to understand the similarity between two text strings. This is done by importing the Counter library to count all the words in the given text.

### 2. Measuring Similarities between skill vectors

Different similarity metrics such as Cosine (Orchini), City block, and Euclidean require vectorization of the skill query input and the job-based skills for searching job options where the user skills are available and then search similar jobs based on the top match.

### 3. Cosine similarity  
Measure of similarity between two non-zero vectors in an inner product space that measures the cosine of the angle between them. It is used to determine how similar two documents (or vectors) are to each other.

### Mathematical Formula:
![Cosine-similarity-formula](https://github.com/Pacchu04/Job-Recommendation-System/assets/92878457/371086d2-fb18-4278-8a5f-1ce23dff83c6)

* A⋅B is the dot product of the vectors 𝐴 and B
* ∥A∥ is the magnitude (or length) of vector 𝐴
* ∥B∥ is the magnitude (or length) of vector 𝐵

### 4. Enhanced Recommendations with User Feedback

Enhanced recommendations with user feedback aim to refine job recommendations by incorporating user preferences, making them more personalized and relevant. This approach extends the basic content-based filtering by considering user ratings on specific jobs to better tailor future recommendations.
Combines user feedback with content-based similarity scores to improve recommendations. Weighs the similarity scores by the user's feedback ratings to prioritize jobs that align better with the user's preferences.

## 2. Job Recommendation using Collaborative filtering
### Project Notebook file:
https://github.com/Pacchu04/Job-Recommendation-System/blob/main/collaborate_filtering_recommendation.ipynb

### Methodology
* Data Pre-processing and Meta-data creation
* Vectorization
* Measuring similarities between skill vectors
* Methods for top recommendations to users
* Enhanced Recommendations with User Feedback

Dataset used for this recommendation: https://www.kaggle.com/datasets/tondji/jobs-data-for-recommender-systems

Same Data Pre-processing steps applied for this dataset.

### Measuring Similarities between skill vectors

The different similarity measures used for generating top job recommendations include:

* Tanimoto or Jaccard Similarity
* Cosine or Orchini Similarity
* Euclidean distance-based similarity

### Top Recommendation methods
The techniques mentioned earlier and their appropriate pre-processing and vectorization were incorporated as a recommendation model and tested on user test data as a cold-start problem.

The two ways of top recommendations are: Top 5 job recommendations and Highest score based Job Recommendations. In this way, we are able to assess the performance of the models based on whether they were able to predict the user’s job accurately two different scenarios.

### Results and Analysis
Based on the two types of user recommendations mentioned above, we analyze the performance of all the techniques mentioned above. The resultant jobs recommended to each new user are then checked with the job that the user is originally in as per the test dataset. If the original user job is recommended in the model result, then the model appends 1 for yes else, it appends 0 for no. This array of 0's and 1's thus received is then checked for accuracy by computing the count of 1's from the total user predictions

Among all the models made with the incorporation of different similarity metrics, the cosine similarity based job recommendation system model outperformed rest of them all.

Model Accuracy:

![image](https://github.com/Pacchu04/Job-Recommendation-System/assets/92878457/af5a0c35-3d45-4a85-affa-21571a84b881)

This is because cosine considers the existence of duplicate terms while computing similarity. Also, computationally, cosine has low complexity and ease over handling spare data vectors since only non-zero dimensions are considered.

Upon analyzing the result table we observe that the short-comings of some similarity measures upon recommending top 5 and highest-score based job recommendations as even upon achieving high similarity scores is due to the fact that users are seen to have different jobs than the ones recommended by the models, thus resulting in 6–10% error rates.
