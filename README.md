# README

<img width="1039" height="852" alt="Instagram post - 6" src="https://github.com/user-attachments/assets/3ced92b7-13c9-4416-bc7f-21edaed60be1" />

# 🎬 **Baku Higher Oil School Cinema Club Data Analysis**
## Overview

This project presents an in-depth Exploratory Data Analysis (EDA) of participant registration and feedback data for the **[Baku Higher Oil School Cinema Club](https://www.instagram.com/bhoscinema.club/)**. The primary goal is to extract actionable insights that can help the club enhance the movie session experience, optimize outreach strategies, and make data-driven decisions for future events.

The analysis combines three distinct datasets: participant registrations, post-session feedback, and details about each movie session. By integrating these data points, we aim to uncover trends, preferences, and areas for improvement, ultimately contributing to a more engaging and satisfying experience for all club members.

## 📊 Data Sources

The data were collected by creating Google Forms for each session for registration and feedback after each session, except for Sessions 7 and 8, where feedback forms were not created due to oversight. This project utilizes three preprocessed and cleaned datasets, stored in the `data_processed/` directory:

- `processed_registration_data.csv`

  - **Description**: Contains individual participant registration records for various movie sessions.
  - **Key Fields**:
    - `participant_id`: Unique identifier for each participant.
    - `session_id`: Unique identifier for the movie session the participant registered for (links to `movie_sessions.csv`).
    - `registration_date`: Timestamp when the participant registered.
    - `university_name_proper`: The proper name of the university the participant belongs to.
    - `major_category`: Broader academic field (e.g., 'STEM', 'Business & Economics', 'Education & Environmental Studies', 'Arts, Humanities & Social Sciences', 'Health & Medical', 'Other/Not Specified').
    - `course`: Specific course or program the participant is enrolled in (e.g., 'Foundation', '1', '2', '3', '4', '5').

- `processed_feedback_data.csv`

  - **Description**: Contains individual feedback submissions from participants after movie sessions, excluding Sessions 7 and 8.
  - **Key Fields**:
    - `session_id`: Unique identifier for the movie session (links to `movie_sessions.csv`).
    - `feedback_date`: Timestamp when the feedback was submitted.
    - `satisfaction_rating`: Numeric rating (1-5) reflecting participant satisfaction (1 = Very Dissatisfied, 5 = Very Satisfied).
    - `liked_aspects_category`: Categorized aspects participants liked (e.g., 'Environment', 'Movie Selection', 'Organization', 'Overall Positive', 'Other').
    - `areas_for_improvement_category`: Categorized suggestions for improvement (e.g., 'Positive Feedback (No Improvement Needed)', 'Logistics and Quality', 'Movie Selection', 'Timing', 'Other').

- `movie_sessions.csv`

  - **Description**: Provides detailed information about each of the 13 movie sessions hosted by the club.
  - **Key Fields**:
    - `session_id`: Unique identifier for the movie session (links to `processed_registration_data.csv` and `processed_feedback_data.csv`).
    - `movie_title`: The title of the movie screened.
    - `genre`: The genre of the movie (e.g., 'Science Fiction', 'Animation', 'Comedy-Drama').
    - `duration (minutes)`: Duration of the movie in minutes.
    - `release_year`: The year the movie was originally released.
    - `session_date`: The date the movie session took place.
    - `imdb_score`: The IMDb rating of the movie.

## 🔍 Analysis Performed

The project involves comprehensive Exploratory Data Analysis (EDA) conducted using Python (Pandas, Plotly, Seaborn, Matplotlib) and further visualized in Power BI.

### 1. Feedback Data EDA (`03_feedback_data_analysis.ipynb`)

- **Objective**: To understand participant satisfaction, identify appreciated aspects, and highlight areas for improvement.
- **Key Visualizations & Insights**:
  - Distribution of Satisfaction Ratings: A bar chart showing the count of responses for each rating (1-5), revealing an overwhelmingly positive sentiment with a high concentration of 5-star ratings.
  - Average Satisfaction Trend: A line chart tracking the average satisfaction over time, providing a high-level pulse check on participant happiness.
  - Top Liked Aspects: Bar charts identifying the most frequently praised elements of the sessions (e.g., Movie Selection, Environment, Overall Positive).
  - Areas for Improvement: Bar charts pinpointing the most common suggestions for improvement (e.g., Logistics and Quality, Movie Selection, Timing).
  - Session-Specific Feedback: Analysis of individual session performance based on average satisfaction, highlighting top-performing (e.g., Sessions 5, 13) and underperforming sessions (e.g., Session 4).

### 2. Registration Data EDA (`02_participant_data_eda.ipynb`)

- **Objective**: To analyze participant demographics, registration patterns, and popularity of universities and courses.
- **Key Visualizations & Insights**:
  - Registration Trend Over Time: Line chart visualizing daily/weekly/monthly registration counts to identify peak periods.
  - Registrations by University: Bar chart showing the count of registrations from each university, with Baku Higher Oil School leading at 84.09%.
  - Major Category Distribution: Bar or pie chart illustrating the proportion of registrations across different academic fields.
  - Course Popularity: Bar chart displaying registration counts, with Foundation at 59.93%, followed by Course 1 (17.06%), and declining in higher courses.
  - Registration Lead Time: Analysis of how far in advance participants register for sessions.
  - Registrations by Day of Week: Understanding which days see the most registration activity.

### 3. Combined Analysis (Across all datasets)

- **Objective**: To uncover relationships between movie characteristics, registration behavior, and feedback.
- **Key Visualizations & Insights**:
  - Most Attractive Genres: Identifying which movie genres attract the highest number of registrations.
  - IMDb Score vs. Participation/Satisfaction: Exploring correlations between a movie's critical rating and attendance/satisfaction.
  - Satisfaction by Genre & Movie: How average satisfaction varies across different movie titles and genres.
  - Feedback Submission Rate: Comparing the percentage of feedback submissions relative to registrations for each session.

## 📈 Power BI Dashboard

A comprehensive Power BI dashboard has been designed to provide interactive insights based on the combined datasets. The dashboard is structured into two main pages:

- **Registrations Page**:

  - **Purpose**: Offers detailed analysis of participant registration patterns and demographics.
  - **Content**: Detailed Registration Trend Over Time, Registrations by University (with dynamic Top N), Major Category Distribution, Registrations by Course Popularity, and other demographic breakdowns.

- **Feedback & Satisfaction Page**:

  - **Purpose**: Focuses on in-depth understanding of participant feedback and satisfaction levels.
  - **Content**: Satisfaction Rating Distribution, Top Liked Aspects (with dynamic Top N), Top Disliked Aspects (with dynamic Top N), Average Satisfaction by Movie Genre, and Feedback Submission %.

## 📂 Project Structure

The repository is organized to ensure clarity, maintainability, and ease of navigation:

```
BHOS_CinemaClub_EDA/
├── data_processed/
│   ├── movie_sessions.csv
│   ├── processed_feedback_data.csv
│   └── processed_registration_data.csv
├── notebooks/
│   ├── 01_feedback_data_processing.ipynb
│   ├── 02_participant_data_processing.ipynb
│   ├── 03_feedback_data_eda.ipynb
│   └── 04_participant_data_eda.ipynb
├── power_bi/
│   ├── Movie Sessions Analysis.pbix
├── README.md
```

## 📧 Contact

For any questions or suggestions, please open an issue in this repository or connect with me on LinkedIn: **[Avaz Asgarov](https://www.linkedin.com/in/avaz-asgarov/)**.

## Key Insights:

- **Feedback Analysis**: Average satisfaction is 4.48/5, with Sessions 5 and 13 achieving perfect scores, while Session 4 scored lowest at 3.20, indicating potential areas for improvement.
- **Registration Analysis**: Baku Higher Oil School dominates registrations (84.09%), with Foundation course students leading at 59.93%, suggesting strong engagement from early learners.
