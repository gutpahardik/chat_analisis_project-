 WhatsApp Chat Analyzer (Streamlit & Python)
This is an end-to-end data analysis project developed to parse, process, and provide in-depth visualized analysis of exported WhatsApp chat logs. It operates as an interactive web application powered by Streamlit.

💡 Project Highlights for Interviews
This project demonstrates strong capabilities across several core technical domains:

Aspect	Core Skills Demonstrated
Data Preprocessing	Used Regular Expressions (re) to parse complex chat logs into structured data. Engineered date/time features from raw timestamps for temporal analysis.
Web App Development	Built a functional, interactive user interface using Streamlit for data upload, user selection, and dynamic visualization display.
Data Analysis	Implemented functions for statistical analysis, including frequency counts (Counter), custom stopword filtering (stop_hinglish.txt), and URL/Emoji extraction.
Data Visualization	Utilized matplotlib and seaborn to create various chart types (Time Series, Bar Charts, Heatmaps) for effective data storytelling.

Export to Sheets
✨ Key Features & Insights
The application provides a comprehensive analysis, which can be viewed for the 'Overall Chat' or filtered by any 'Selected User':

1. Core Chat Statistics
Quick quantitative metrics displayed in columns:

Total Messages & Total Words

Media Shared (counts the <Media omitted> entries)

Links Shared (uses URLExtract for accurate URL detection)

2. Temporal Analysis
Visualizing chat activity across time:

Monthly & Daily Timelines: Line plots showing messaging trends and peaks over time.

Activity Maps: Bar charts highlighting the Most Busy Day of the week and the Most Busy Month of the year.

Weekly Activity Heatmap: A detailed heatmap created using seaborn and pivot_table to show message density across days of the week and hours of the day (e.g., morning, night), revealing behavioral patterns.

3. Content and Language Analysis
Deep dive into the conversational content:

Most Common Words: A horizontal bar chart of the top 25 words after filtering common terms using the stop_hinglish.txt file.

WordCloud: A visual representation of high-frequency words.

Emoji Analysis: A pie chart and dataframe detailing the frequency and distribution of the most used emojis (using the emoji library).

4. Participant Analysis
Most Busy Users (Group Level Only): Identifies the top communicators with a bar chart and displays a full dataframe showing the percentage contribution of every participant to the overall chat.

⚙️ Technical Implementation Details
The project is structured into three distinct, modular components:

1. preprocessor.py (The Data Engine)
This module handles the crucial step of turning raw text into a clean DataFrame.

Parsing Logic: Employs a specific Regular Expression pattern (\d{1,2}/\d{1,2}/\d{2,4},\s\d{1,2}:\d{2}\s-\s) to reliably split messages from their timestamps.

User/Message Extraction: Uses re.split to separate the user name from the message text, handling variations for group notifications.

Feature Engineering: Converts the timestamp string to a datetime object and creates essential columns like year, month_num, day_name, and the hourly period column for the heatmap.

2. helper.py (The Analytics Core)
This module contains all the analytical functions:

User Filtering: Each function efficiently filters the DataFrame using df = df[df['user'] == selected_user] for user-specific analysis.

Frequency Counting: Leverages collections.Counter for fast word and emoji tallying.

Timeline Creation: Uses pandas.groupby() to aggregate message counts by date, month, and year for time-series plots.

3. app.py (The Streamlit Application)
Integrates all modules.

Handles file upload and user interaction logic (st.sidebar.selectbox, st.sidebar.button).

Manages the presentation layout using st.columns, st.title, and st.header.

▶️ Installation and Setup
Dependencies
Ensure these libraries are listed in your requirements.txt:

streamlit
pandas
matplotlib
seaborn
wordcloud
urlextract
emoji
Steps to Run
Clone the Repository:

Bash

git clone https://github.com/YourUsername/YourRepoName.git
cd YourRepoName
Install Libraries:

Bash

pip install -r requirements.txt
Ensure stop_hinglish.txt: Place a text file named stop_hinglish.txt (containing custom stopwords, one per line) in your project root for accurate content analysis.

Export Chat: Export your WhatsApp chat as a .txt file (WITHOUT MEDIA).

Run the App:

Bash

streamlit run app.py
