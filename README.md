# Spotify_Dashboard
Welcome to the Spotify Dashboard project! This repository showcases my journey of analyzing a 2023 Spotify dataset, cleaning and enhancing it using the Spotify API, and creating an interactive dashboard to visualize the data. The project focuses on improving my data visualization and design skills, while also demonstrating the importance of data cleaning and API integration.

## 📊 Project Overview 
This project revolves around a dataset containing track names, artist names, and audio features collected from the Spotify API. The goal was to:
Clean the dataset by removing non-English characters and filling missing values using the Spotify API.
Enhance the dataset by fetching additional audio features (e.g., key, mode, tempo, etc.) for each track.
Create an interactive dashboard using HTML and embedded Spotify URLs to visualize the data.

The project highlights my ability to:
Work with APIs to fetch and enrich data.
Clean and preprocess datasets for analysis.
Design and build visually appealing dashboards.

## 🛠️ Technologies Used
Python: For data cleaning, API integration, and preprocessing.
Spotify API: To fetch track details, audio features, and cover URLs.
Pandas: For dataset manipulation and cleaning.
HTML/CSS: For building the interactive dashboard.
Data Visualization: Tools like Plotly or Matplotlib for creating charts (if applicable).

## 📂 Dataset
The dataset consists of the following columns:

track_name: Name of the track.

artist(s)_name: Name of the artist(s).

cover_url: URL of the track's cover art.

key: The key the track is in (fetched from Spotify API).

mode: The modality of the track (major or minor).

Other audio features like tempo, danceability, energy, etc.

## 🧹 Data Cleaning and Enhancement
1. Removing Non-English Characters
To ensure consistency in the dataset, I removed all non-English characters from the track_name and artist(s)_name columns using Python's re module. This step was crucial for standardizing the data and making it easier to work with.

2. Filling Missing Values Using Spotify API
Many rows in the dataset had missing values for key, mode, and cover_url. I used the Spotify API to:
Fetch the missing key and mode values using the audio_features endpoint.
Replace missing cover_url values with the track's cover art or the artist's image.

3. Handling API Errors
I implemented error handling to manage 403 Forbidden errors and rate limits, ensuring the script runs smoothly even when the API encounters issues.

##🎨 Interactive Dashboard
Using the cover_url and other data collected from the Spotify API, I built an interactive HTML dashboard to visualize the dataset. Here's how I did it:

1. Embedding Spotify URLs
I used the cover_url to display track cover art in the dashboard.
2. Added a measure named poster containing html code which was made possible to use by PowerBI html extension:
Poster = 
VAR x =
    CALCULATE(
        MAX('Spotify'[cover_url]),
        'Spotify'[streams] = MAX('Spotify'[streams])
    )
RETURN
"
<!DOCTYPE html>
<html lang='en'>
<head>
    <meta charset='UTF-8'>
    <title>Image Cropping</title>
    <style>
        .image-container {
            width: 1142px; /* Increased width */
            height: 269px; /* Increased height */
            overflow: hidden; /* Hide parts of the image that don't fit */
            border-radius: 0px; /* Slightly more rounded corners */
            position: relative; /* Relative positioning for the child element */
        }

        .image {
            object-fit: cover; /* Cover the entire container */
            object-position: center; /* Center the image */
            width: 100%; /* Full width */
            height: 100%; /* Full height */
        }
    </style>
</head>
<body>
    <div class='image-container'>
        <img src='" & x & "' alt='Album Cover' class='image'>
    </div>
</body>
</html>
"

2. Visualizing Audio Features
I created charts and tables to display audio features like key, mode, and tempo. These visualizations help users understand the characteristics of each track at a glance.

3. Design Focus
Rather than focusing on complex backend logic, I prioritized design and usability. The dashboard is clean, intuitive, and visually appealing, showcasing my ability to create user-friendly interfaces.

## 4. Publishing to the Web
I published the Power BI dashboard to the web using Power BI's Publish to Web feature. This generated an embed code, which I used to create an interactive HTML file. Users can interact with the dashboard once they sign in to their Spotify account, ensuring a personalized and secure experience.

How It Works
Publish to Web:

I published the Power BI dashboard to the web, which generated an embed code.
This embed code was used to create an interactive HTML file.

Interactive HTML File:
The HTML file contains an embedded Power BI report that users can interact with.
Users are prompted to sign in to their Spotify account to access the dashboard.

User Experience:
Once signed in, users can explore the dataset, filter tracks, and view audio features in real-time.

 The dashboard is fully responsive and works seamlessly on all devices.
## For live interaction Click here:https://jacinto2727.github.io/Spotify_Dashboard/ 







