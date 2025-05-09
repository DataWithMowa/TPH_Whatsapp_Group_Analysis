<h1 style="text-align: center;">TPH WhatsApp Group Analysis</h1>

<div align="center">
  <img src="The Publishers House Image.jpg"="The TPH Image" width="500" height="400">
</div>

## Introduction: 
<details>
  <summary>Click to expand</summary>
  <br>
  
The TPH WhatsApp Group is the main online space for members of The Publishers House (TPH) — a church based at The House of Bread, Korinjoh House, Opposite Shawarma and Grills, British, Jos, Nigeria.

The group is used for:
- Sharing church updates and announcements
- Talking and staying connected with other members, leaders, and workers
- Celebrating birthdays, anniversaries, and other special moments

This project is a data analysis of the group. It looks at things like how often people chat, the most active times, what kind of messages are shared, and how people interact in the group. The goal is to better understand how the group works and how it can serve the church even more.

</details>

## Project Objective:
<details>
  <summary>Click to expand</summary>
 <br>
  
The goal of this project is to provide answers to the following questions:

- Who celebrates birthdays the most 🎉
- The most common words we use
- The emotional tone of our conversations
- Peak hours and days of message activity
- Who sends the most messages and gets the most responses
- How quickly we respond
- Who consistently engages the most
- And how many of our 274 members are active participants

It’s a look into what our group chats reveal about us as a spiritual family.
</details>

## How to Run The Source Code Locally:
<details>
  <summary>Click to expand</summary>

#### There are two code files I have created for this project. One file handles exporting data from a text file to a CSV, and the other is for exploratory data analysis (EDA) and data analysis.

- You can view and run the CSV export code and its output here:[tph_data_csv_export.ipynb](https://colab.research.google.com/drive/1Xm2DTMFDKssWEBw_G2vNj87WNqrs-dar?usp=sharing)
- You can view and run the EDA and data analysis code and its output here:[Data Cleaning & EDA.ipynb](https://colab.research.google.com/drive/1HrQmWLhFgt9AD4Jt6CpVG5xRp872bGYB?usp=sharing)
  
## Here are the Setup and Execution instructions:
### Prerequisites

Before you can run this code, you'll need to have the following installed:

* **Python:** You can download the latest version from [python.org](https://www.python.org/downloads/).
  
* **Jupyter Notebook:** Install it using pip:
    ```bash
    pip install notebook
    ```
* **Git (Optional but Recommended):** To clone the repository, download from [git-scm.com](https://git-scm.com/downloads).
  
* **Required Python Libraries:** Install Pandas, Matplotlib, Plotly, NumPy, statsmodels, and specifically, the plot_acf and plot_pacf functions from the statsmodels.graphics.tsaplots module, as well as the SARIMAX module:
    ### OR
  ```bash
    pip install pandas matplotlib plotly numpy statsmodels  # Use VS Code terminal or Google Colab
    ```
### Cloning the Repository (Use VS Code Terminal or Windows Command Prompt):

1.  Clone the repository to your local machine:
    ```bash
    git clone [https://github.com/DataWithMowa/Website_Performance_Python_Analysis.git]
    ```
2.  Navigate to the project directory:
    ```bash
    cd [https://github.com/DataWithMowa/Website_Performance_Python_Analysis.git]
    ```
### Setting Up a Virtual Environment (Recommended)

1.  Create a virtual environment:
    ```bash
    python3 -m venv venv
    ```
2.  Activate the virtual environment:
    * On Windows:
        ```bash
        venv\Scripts\activate
        ```
    * On macOS/Linux:
        ```bash
        source venv/bin/activate
        ```
### Installing Dependencies

1.  Install the required Python libraries:
    ```bash
    pip install pandas matplotlib plotly numpy statsmodels
    ```
### Running the Jupyter Notebook

1.  Start Jupyter Notebook from the project directory:
    ```bash
    jupyter notebook
    ```
2.  Your web browser will open, showing the Jupyter Notebook interface.
3.  Find and open the `925 Website Performance Analysis.ipynb` file.
4.  Run the cells in the notebook one after the other by clicking "Cell" > "Run All" or by pressing Shift + Enter in each cell.

### Data and Configuration

* Find and download the "updated dataset" used in this analysis in the `Dataset/` directory.
  
### Jupyter Notebook

 * Here is the Jupyter source file for this project: [925 Website Performance Analysis.ipynb](https://colab.research.google.com/drive/1qg95To4QTQlNtKyN9Jb9Mns9slKGOuOD?usp=sharing)
</details>

## Data Overview:
<details>
  <summary>Click to expand</summary>
 <br>This dataset is a big collection of information about how people are using a website. It’s like a logbook that tracks who’s visiting, when, how they got there, and what they’re doing. It covers stuff like marketing channels, dates, user counts, session details, engagement stats, and info about the visitors themselves (like age, gender, location, and device). 
 
### What’s in the Dataset:
<details>
  <summary>Click to expand</summary>
 <br> 
Here’s a rundown of each column and what it tells us:

1. **Marketing Channels**  
   - This shows how people found the website. Examples are “Direct Website” (they typed the URL or used a bookmark), “From Social Media” (came from platforms like Twitter or Facebook), “Organic Search” (found it via Google), “Organic Video” (maybe from YouTube), and “Uncategorized” (not sure how they got there).

2. **Date + Hour (YYYY-MM-DD-HR)**  
   - The exact date and hour when the data was recorded, like “2024-04-16 23:00:00” (April 16, 2024, at 11 PM). It helps track when people visit.

3. **No. Of Users**  
   - How many unique people visited during that hour. Ranges from 0 to hundreds (e.g., 237 users at one point).

4. **No. Of Session of Users**  
   - Total visits (sessions) by those users in that hour. A user might visit more than once, so this can be higher than the number of users (e.g., 300 sessions for 237 users).

5. **Engaged Sessions**  
   - Sessions where people actually did something—like clicked around or stayed a while—instead of just bouncing off. For example, 144 engaged sessions out of 300 total sessions.

6. **Average Engagement Time Per Session in Seconds**  
   - How long people stuck around per session, in seconds. Varies a lot, from 0 (they left right away) to over 4,000 seconds (over an hour!).

7. **Engaged Sessions Per User**  
   - Average number of engaged sessions per person. If it’s 0.6, that means each user had 0.6 engaged sessions on average (some had none, some had more).

8. **Events Per Session**  
   - How many actions (like clicks or page views) happened per session. Higher numbers mean people were more active (e.g., 4.67 events per session).

9. **Engagement Rate**  
   - The percentage of sessions that were engaged (engaged sessions divided by total sessions). A rate of 0.48 means 48% of sessions had some activity.

10. **Event Count**  
    - Total number of actions across all sessions in that hour. For example, 1,402 events means lots of clicking or scrolling happened.

11. **Age**  
    - The average (or maybe typical) age of users in that hour, ranging from 18 to 60.

12. **Age Groups**  
    - Groups users into “Young Adults” (roughly 18-34), “Adults” (35-49), or “Old People” (50+). Matches the age column.

13. **Gender**  
    - Whether the users were mostly “Male” or “Female” during that hour.

14. **Location**  
    - Where users were from, like “UK,” “Nigeria,” “United States,” “Australia,” etc. Shows the website’s global reach.

15. **Device Type**  
    - What device they used: “Mobile,” “Tablet,” or “Desktop.” Tells you if it’s phone users, tablet fans, or computer folks.

</details>
</details>

## Tools and Libraries Used:

<details>
  <summary>Click to expand</summary>
  <br>
  For this analysis, I used the following tools and libraries:  

- **Jupyter Notebook** – An interactive tool for writing, running, and documenting Python code in a clear, step-by-step way.  
- **Pandas** – Used for handling and analyzing data, including cleaning, filtering, and combining datasets.  
- **Matplotlib** – Helped create visual charts to explore and present data effectively.  
- **Plotly** – Used for interactive graphs that make it easier to understand and share insights.  
- **NumPy** – Assisted with numerical calculations, working with large arrays and mathematical functions.  
- **statsmodels** – Used for statistical modeling and time series analysis.  
- **plot_acf & plot_pacf (from statsmodels)** – Helped analyze time series data by showing patterns in past trends.  
- **SARIMAX (from statsmodels)** – Used for forecasting time series data, capturing seasonal patterns and external influences.  

This combination of tools helped ensure accurate analysis and valuable insights.
</details>

## Data Cleaning and Preparation:

<details>
  <summary>Click to expand</summary>
  <br>

Before starting the analysis, I cleaned and prepared the raw dataset using **Microsoft Excel** to ensure accuracy and consistency. You can find and download the "updated dataset" used in this analysis in the `Dataset/` directory  Here’s what was done:  

### **1. Renaming Column Headers**  
- "Session primary channel group" → **"Marketing Channels"** (for clarity)  
- "Date + hour (YYYYMMDDHH)" → **"Date + Hour (YYYY-MM-DD-HH)"** (to follow a standard format)  
- "Users" → **"No. of Users"**  
- "Session" → **"No. of Sessions of Users"**  
- "Average engagement time per session" → **"Average Engagement Time Per Session (Seconds)"** (for specificity)  
- "Engaged sessions per user" → **"Engaged Sessions Per User"**  
- "Engagement rate" → **"Engagement Rate"**  
- "Events per session" → **"Events Per Session"**  

### **2. Renaming Column Values**  
- "Direct" → **"Direct Website"** (for better context)  
- "Organic Social" → **"From Social Media"**  
- "Email" → **"Email Marketing"**  
- "Referral" → **"From Another Website"**  

### **3. Formatting Date and Time**  
- The "Date + Hour" column was converted to a proper **date-time format (YYYY-MM-DD-HH)** for consistency.  

### **4. Data Alignment & Formatting**  
- Adjusted the formatting of key columns like **Average Engagement Time, Engaged Sessions Per User, Events Per Session, and Engagement Rate** to ensure a structured and visually clear dataset.  

These steps were essential to make sure the data was clean, well-organized, and ready for analysis.
</details>

## Exploratory Data Analysis(EDA):
<details>
  <summary>Click to expand</summary>
 <br>

**Objective:**
The main goal of this Exploratory Data Analysis (EDA) was to understand how people interact with the 925 Fitness website. This included analyzing traffic patterns, user demographics, and engagement metrics to find areas for improvement and optimization.

**Methodology:**
In this analysis, I looked at website traffic data to see where visitors come from, their age, gender, location, and the devices they use. I also checked when people visit the site the most (by time, day, and month) and how engaged they are, like how long they stay, how many sessions they have, and how often they interact. I also compared different traffic sources to see which ones perform best. Lastly, I analyzed how different engagement factors are connected.

**Key Findings:**

* **Traffic Sources:** Social media is the dominant traffic source, followed by direct website visits and organic search as seen below.
  <img src="Charts Created/Marketing Channels Chart.png" alt="Marketing Channel Chart" width="auto">
  
* **Demographics:**
    * Young adults (20s-30s) are the largest user group as seen below.
      <img src="Charts Created/Users By Age Group.png" alt="User By Age Group Chart" width="auto">
      
    * A near-equal distribution of male and female users as seen below.
      <img src="Charts Created/Users By Gender.png" alt="User By Gender Chart" width="auto">
      
    * Australia, the U.S., Nigeria, and South Africa are the top geographic locations as seen below.
      <img src="Charts Created/Users By Location.png" alt="User By Location Chart" width="auto">
      
    * Traffic is evenly distributed across mobile, desktop, and tablet devices as seen below.
      <img src="Charts Created/Users By Device Type.png" alt="User By Device Type Chart" width="auto">
      
* **Temporal Patterns:**
    * Peak traffic occurs at 11 AM and 9 PM as seen below.
      <img src="Charts Created/Traffic by Time Of Day.png" alt="Traffic By Time of Day Chart" width="auto">
      
    * Weekday traffic is significantly higher than weekend traffic, with Wednesday being the peak day as seen below.
      <img src="Charts Created/Traffic By Day of Week.png" alt="Traffic By Day Of Week Chart" width="auto">
      
    * April had a significantly higher amount of traffic than May as seen below.
      <img src="Charts Created/Traffic By April & May.png" alt="Traffic By April & May Chart" width="auto">
      
* **User Engagement:**
    * April 17, 2024, at 18:00 had the highest number of user sessions as seen below.
      <img src="Charts Created/engagement_metrics_matplotlib.png" alt="Engagement Metrics Chart" width="auto">
      
    * "Organic Video" and "From Another Website" have higher engagement rates and events per session compared to social media as seen below.
      <img src="Charts Created/Channel_performance_Metrics.png" alt="Channel Perfromance Metrics Chart" width="auto">
      
* **Correlation Analysis:**
    * A strong positive correlation exists between "Engaged Sessions Per User" and "Engagement Rate." as seen below.
      <img src="Charts Created/engagement_metrics_correlation_heatmap.png" alt="Correlation Chart" width="auto">

  * **Website Traffic Forecasting:**
    * Autocorrelation (ACF) and partial autocorrelation (PACF) charts were used to determine model parameters as seen below.
      <img src="Charts Created/ACF and PACF Chart.png" alt="ACF and PACF Chart" width="auto">
    * A time series analysis was conducted using the SARIMA model to forecast website traffic for the next 24 hours as seen below.
      <img src="Charts Created/Website Traffic Forecasting Plotly.png" alt="Website Forecasting Chart" width="auto">
   
</details>

## Data Analysis:
<details>
  <summary>Click to expand</summary>
 <br>

This section explains how I analyzed data from the **925 Fitness** website to find useful insights. The analysis covered different areas, such as where visitors come from, who they are, when they visit, how they interact with the site, and how to predict future traffic.  

### **1. Traffic Source Analysis**  
- I looked at where website visitors come from (social media, direct visits, search engines, referrals, or unknown sources).  
- Bar charts were used to show the traffic distribution.  
- I compared different sources to see which ones bring the most and least visitors.  

### **2. User Demographics**  
- I analyzed visitor details like **age, gender, and location** to understand who uses the site.  
- Charts were used to display this information clearly.  
- I also checked what devices people use to access the website.  

### **3. Website Traffic Over Time**  
- I studied when people visit the website the most—looking at trends by **hour, day, and month**.  
- I used **line graphs and heatmaps** to visualize these patterns.  

### **4. User Engagement**  
- I examined how visitors interact with the site by looking at metrics like **time spent, number of visits, clicks per session, and engagement rate**.  
- I also checked how these metrics are related to each other.  

### **5. Predicting Future Traffic**  
- I used a forecasting method (**SARIMA model**) to predict website visits for the next 24 hours.  
- **Graphs (ACF and PACF)** were used to help fine-tune the model for accuracy.  

### **6. Finding Relationships Between Metrics**  
- A **heatmap** was created to show how different engagement factors are connected.  
- This helped identify **strong and weak relationships** between various user behaviors.  

### **Overall Approach**  
- I used **data visualization and statistics** to make sense of the data.  
- The goal was to find ways to **improve the website and marketing strategies**.  
- I cleaned and prepared the data using **Microsoft Excel** before analysis.
</details>

## Key Findings & Insights
<details>
  <summary>Click to expand</summary>
 <br>

### **1. Social Media Brings Traffic but Not Always Engagement**  
- Most visitors come from social media, showing a strong online presence.  
- However, while social media attracts visitors, it doesn’t always keep them engaged.  
- This means the content bringing users in might not be the same content that keeps them interested.  

**What to do:** Improve social media strategies to encourage deeper interaction. Use more engaging posts, targeted campaigns, and clear calls to action.  

### **2. Understanding User Demographics is Key**  
- Most visitors are young adults (20s-30s), meaning content should cater to their interests.  
- The nearly equal male-female split means content should be inclusive.  
- Knowing users’ locations helps in creating region-specific content and ads.  

**What to do:** Use this data to create content and marketing campaigns that better connect with the audience.  

### **3. Best Times to Post and Engage**  
- Peak traffic happens at **11 AM and 9 PM**, with **Wednesdays** being the busiest day.  
- Posting at these times can increase reach and engagement.  

**What to do:** Schedule content and ads for these peak times to get the most impact.  

### **4. More Engaged Sessions = Higher Engagement**  
- Users who stay engaged during their visit tend to interact more.  
- The more engaging each session is, the better the overall engagement rate.  

**What to do:** Improve session quality by adding interactive content, personalized experiences, and engaging features.  

### **5. Big Traffic Drop from April to May**  
- Website traffic suddenly dropped during this period.  
- Possible reasons: technical issues, changes in marketing, or search engine updates.  

**What to do:** Investigate and fix the cause—check for website errors, review marketing strategies, and analyze external factors.  

### **6. Predicting Future Traffic with SARIMA Model**  
- The SARIMA model helps forecast traffic for better planning.  
- This allows the company to prepare for traffic spikes by managing content, support, and server capacity.  

**What to do:** Use this model to make smarter decisions about content scheduling and resource allocation.  

### **7. Not All Traffic Sources Perform the Same**  
- **Social media** brings in the most visitors, but **organic video and referral traffic** have better engagement.  
- This means some channels drive **quality** traffic, while others bring **quantity** but less interaction.  

**What to do:** Study why organic video and referral traffic engage better and apply those insights to improve social media strategy.  

### **8. Website Must Work Well on All Devices**  
- Traffic is evenly split between **mobile, desktop, and tablets**.  
- This means the website must be user-friendly on all devices.  

**What to do:** Ensure ads and website content are fully optimized for all screen sizes.

</details>

## Recommendations:
<details>
  <summary>Click to expand</summary>
 <br>  

### **1. Boost Social Media Engagement (Main Traffic Source)**  
- **Action Steps:**  
  * Post 2-3 times daily across platforms like Instagram, Facebook, and TikTok.  
  * Use diverse content formats:  
    - Quick workout videos (15-30 seconds) optimized for mobile.  
    - Fitness tips, success stories, and behind-the-scenes glimpses.  
    - Interactive content like polls, Q&A sessions, and challenges.  
  * Partner with influencers for giveaways and collaborations.  
  * Add clear CTAs to direct users to key website pages.  
  * Engage followers by responding to comments and messages promptly.  
  * Consider adding a live social feed to the homepage and promote website-exclusive content.  

**What to do:** Increase engagement by diversifying content and promoting community interaction.  

### **2. Optimize Direct Website Experience (2nd Highest Traffic Source)**  
- **Action Steps:**  
  * Speed up website load times (e.g., image compression, caching).  
  * Simplify navigation for better user flow (e.g., easy class registration).  
  * Develop a "Members-Only" section with exclusive content.  
  * Use a clean, modern design.  

**What to do:** Make the website faster and easier to navigate while offering exclusive content to members.  

### **3. Enhance Organic Search Presence (3rd Highest Traffic Source)**  
- **Action Steps:**  
  * Perform keyword research and optimize content with relevant terms (e.g., "fitness classes near me").  
  * Create a blog strategy with valuable, searchable content (e.g., "5 Beginner Exercises").  
  * Improve SEO through backlinking and website structure.  

**What to do:** Focus on SEO to increase organic search visibility.  

### **4. Strengthen Referral Traffic (From Other Websites)**  
- **Action Steps:**  
  * Collaborate with fitness bloggers and influencers for backlinks.  
  * Write guest posts for external websites, including links to your site.  
  * Offer perks like discount codes or affiliate programs to encourage referrals.  

**What to do:** Increase referral traffic by collaborating with influencers and external sites.  

### **5. Investigate and Optimize Uncategorized Traffic**  
- **Action Steps:**  
  * Use UTM codes to track and categorize uncategorized traffic.  
  * Analyze each traffic source and optimize based on performance.  

**What to do:** Track and categorize uncategorized traffic for better analysis and optimization.  

### **6. Leverage Organic Video Content**  
- **Action Steps:**  
  * Embed workout videos (YouTube/TikTok) on the website.  
  * Add clear CTAs in videos directing users to the site.  

**What to do:** Use video content to drive engagement and direct traffic to the website.  

### **7. Improve Email Marketing Effectiveness**  
- **Action Steps:**  
  * Create enticing sign-up offers like free workout guides.  
  * Send personalized emails based on user preferences (e.g., tips, success stories).  
  * Segment email lists for better-targeted campaigns.  

**What to do:** Improve email marketing by offering value and personalizing content.  

### **8. Tailor Content for Specific Demographics**  
- **Action Steps:**  
  * Create content for young adults (20s-30s), busy adults (35-50), and older adults (50+).  
  * Focus on trendy, high-energy workouts for younger users and low-impact exercises for older adults.  
  * Run surveys and focus groups for deeper insights.  

**What to do:** Cater content to different age groups and preferences.  

### **9. Optimize for Geographic Locations**  
- **Action Steps:**  
  * Create region-specific content and marketing campaigns for high-performing locations.  
  * Adjust offerings (e.g., pricing, promotions) based on regional preferences.  
  * Use location-based keywords for SEO.  

**What to do:** Tailor content and offers to the needs of each region.  

### **10. Ensure Seamless Multi-Device Experience**  
- **Action Steps:**  
  * Test website responsiveness across mobile, desktop, and tablet.  
  * Optimize for quick load speeds, easy navigation, and mobile-friendly checkout.  
  * Ensure a smooth experience across all devices.  

**What to do:** Prioritize responsive design for an optimal user experience on any device.  

### **11. Optimize for Peak Traffic Times**  
- **Action Steps:**  
  * Schedule posts, emails, and ads during peak times (11 AM and 9 PM).  
  * Offer live chat and chatbot support during these hours.  
  * Optimize website to handle high traffic loads.  

**What to do:** Maximize engagement by posting and running campaigns at peak times.  

### **12. Address the April to May Traffic Drop**  
- **Action Steps:**  
  * Conduct a full audit to identify errors, technical issues, or marketing changes that could have caused the drop.  
  * Gather user feedback and analyze competitor activity.  

**What to do:** Investigate the traffic drop thoroughly and take corrective action based on findings.  

By implementing these strategies, 925 Fitness Company can boost website traffic, enhance user engagement, and create a more effective online presence.

</details>

## Limitations:
<details>
  <summary>Click to expand</summary>
 <br>

While this analysis gives useful insights into the 925 Fitness Company website's performance, it’s important to keep in mind some limitations that might affect the accuracy of the findings. These limitations include:

### 1. **Data Accuracy and Completeness**:
- The analysis relied on website traffic data, which might not show all user actions or fully reflect how users behave in the real world.
- Data collection methods, like tracking codes and analytics platforms, can have limitations that could cause mistakes or missing information.
- The "uncategorized" traffic source might have useful data that, if correctly identified, could change the analysis.
- **Implication**: The results should be taken with caution, as the data may not be complete or entirely accurate.

### 2. **SARIMA Model Forecasting Limitations**:
- The SARIMA model is good for forecasting based on past data, but it might not predict future traffic patterns accurately if something unexpected happens.
- Changes in user behavior, search engine updates, or new marketing campaigns could make the predictions inaccurate.
- **Implication**: The 24-hour traffic forecast should be seen as a guide, not a guarantee. It should be updated with new data for better accuracy.

### 3. **External Factors and Market Changes**:
- The analysis didn’t fully consider outside factors, like what competitors are doing, the economy, or seasonal trends, which could affect traffic and how users behave.
- Changes in the fitness industry or new technologies might also affect user interests and website performance.
- **Implication**: The recommendations should be flexible, considering that the market and outside factors can change.

### 4. **Single Platform Data**:
- The analysis only used website data. Other sources, like customer surveys, social media feedback, or sales data, could have provided a fuller picture of the company’s performance.
- Without these extra sources, the analysis is based only on the data we have.
- **Implication**: Future analyses should include more types of data to better understand user behavior and business results.

### 5. **Sudden Traffic Drop in April-May**:
- There was a sharp drop in website traffic from April to May, which is an unusual event that needs more investigation.
- The analysis couldn’t fully explain why this drop happened or how it might affect the business in the long run.
- **Implication**: The traffic trends should be looked at in light of this unusual drop, and further research is needed to figure out what caused it and what it means for the future.

### 6. **Correlation vs. Causation**:
- While the analysis showed some relationships between engagement metrics, it doesn’t prove that one thing causes another.
- For example, the strong link between "Engaged Sessions Per User" and "Engagement Rate" doesn’t mean that increasing one will automatically increase the other.
- **Implication**: Recommendations based on these relationships should be tried cautiously, and more testing is needed to confirm if one really causes the other.
  
These limitations should be considered when using the recommendations, as they are based on the available data and current situation.
</details>
  
## Challenges and Lessons Learned:
<details>
  <summary>Click to expand</summary>
 <br>

Every project comes with its own set of hurdles, and this one was no different. Here are a couple of challenges I faced and the valuable lessons I learned along the way:

1. **Plotly Chart Rendering in Google Colab**  
   At first, I couldn’t get my Plotly charts to render in Google Colab, even though they worked fine in Jupyter Notebook. It was frustrating, and I spent over a week troubleshooting without much success. The lack of error messages made it tough to pinpoint the issue. Eventually, I learned that specifying the renderer (`fig.show(renderer="colab")`) helped solve the problem.

   **Lesson learned:** Platforms and tools have their quirks, and sometimes the solution is as simple as checking the documentation. Persistence and patience go a long way in problem-solving!

2. **GitHub Documentation and Time Management**  
   I didn’t expect the documentation process to take as long as it did! Structuring it, writing clear explanations, and staying consistent was more demanding than I thought. I realized how important it is to dedicate time for documentation from the start, as it plays a huge role in making a project understandable and reproducible.

   **Lesson learned:** Documentation isn’t just a side task, it’s a core part of any project. Organizing it well and paying attention to small details can really make a difference.

These experiences taught me the value of adaptability, persistence, and learning along the way. I’m looking forward to applying these lessons in future projects!

</details>

## Thank you for reading! 😊

