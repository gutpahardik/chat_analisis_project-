WhatsApp Chat Analyzer (Streamlit & Python)
This is an end-to-end data analysis project developed to parse, process, and provide in-depth visualized analysis of exported WhatsApp chat logs. It operates as an interactive web application powered by Streamlit.

 Project Highlights for Interviews
This project demonstrates strong capabilities across several core technical domains:

Aspect	Core Skills Demonstrated
Data Preprocessing	Used Regular Expressions (re) to parse complex chat logs into structured data. Engineered date/time features from raw timestamps for temporal analysis.
Web App Development	Built a functional, interactive user interface using Streamlit for file upload, user selection, and dynamic visualization display.
Data Analysis	Implemented functions for statistical analysis, including frequency counts (Counter), custom stopword filtering (stop_hinglish.txt), and URL/Emoji extraction.
Data Visualization	Utilized matplotlib and seaborn to create various chart types (Time Series, Bar Charts, Heatmaps) for effective data storytelling.

 Key Features & Insights
The application provides a comprehensive analysis, which can be viewed for the 'Overall Chat' or filtered by any 'Selected User':

1. Core Chat Statistics
Quick quantitative metrics displayed in columns:

Total Messages & Total Words

Media Shared (counts the <Media omitted> entries)

Links Shared (uses URLExtract for accurate detection)

2. Temporal Analysis
Visualizing chat activity across time:

Monthly & Daily Timelines: Line plots showing messaging trends and peaks over time.

Weekly Activity Heatmap: A detailed heatmap created using seaborn and pivot_table to show message density across days of the week and hours of the day, revealing behavioral patterns.

3. Content and Language Analysis
Deep dive into the conversational content:

Most Common Words: A horizontal bar chart of the top 25 words after filtering common terms using the stop_hinglish.txt file.

WordCloud: A visual representation of high-frequency words.

Emoji Analysis: A pie chart and dataframe detailing the frequency and distribution of the most used emojis (using the emoji library).

4. Participant Analysis
Most Busy Users (Group Level Only): Identifies the top communicators and displays their percentage contribution to the overall chat.

Technical Implementation & Dependencies
The project is structured into three modular components (preprocessor.py, helper.py, app.py).

Technology Stack
This project relies on the following key Python libraries:

Category	Libraries Used
App Framework	streamlit
Data Handling	pandas
Visualization	matplotlib, seaborn
Text Processing	wordcloud, urlextract, emoji
Core Python	re (Regular Expressions), collections (Counter)
