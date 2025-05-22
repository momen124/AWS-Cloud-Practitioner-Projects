# Visualizing Netflix Data with Amazon QuickSight

## Objective
Create a dashboard in Amazon QuickSight to visualize Netflix data by uploading a dataset to an S3 bucket, connecting it to QuickSight, and building charts to analyze trends in movies and TV shows.

## Steps
1. **Downloaded the Dataset**:
   - Downloaded `netflix_titles.csv` (Netflix movies and TV shows data) and `manifest.json` (configuration file for QuickSight).

2. **Stored Dataset in Amazon S3**:
   - Created an S3 bucket named `nextwork-quicksight-project-momen` in `us-east-1` for low latency.
   - Uploaded `netflix_titles.csv` and `manifest.json`.
   - Edited `manifest.json` to include the S3 URL: `s3://nextwork-quicksight-project-momen/netflix_titles.csv`.
   - Re-uploaded the updated `manifest.json`, replacing the original.
   - Screenshot: [s3-bucket-objects.png](screenshots/s3-bucket-objects.png)

3. **Created Amazon QuickSight Account**:
   - Signed up for a free trial of QuickSight (Enterprise edition) using the same email as my AWS account.
   - Set the account name to `nextwork-QuickSight-momen` in `us-east-1`.
   - Configured QuickSight to access the S3 bucket `nextwork-quicksight-project-momen`.
   - Unchecked "Add Paginated Reports" to avoid charges.
   - Screenshot: [quicksight-setup.png](screenshots/quicksight-setup.png)

4. **Connected S3 Bucket to QuickSight**:
   - Created a new dataset in QuickSight named `kaggle-netflix-data`.
   - Used the S3 URL of `manifest.json` to connect the dataset.
   - Confirmed successful connection and proceeded to visualize.
   - Screenshot: [s3-connection.png](screenshots/s3-connection.png)

5. **Created First QuickSight Visualization**:
   - Dragged `release_year` to create a donut chart showing the distribution of Netflix titles by release year.
   - Created a bar chart with `release_year` on the Y-axis and `type` (Movie/TV Show) in Group/Color to show yearly breakdowns.
   - Resized both charts for a clean dashboard layout.
   - Screenshot: [first-visualization.png](screenshots/first-visualization.png)

6. **QuickSight Treasure Hunt**:
   - Answered Netflix’s question: “Visualize the % of Movies vs. TV Shows by release year.”
   - Changed the bar chart to a **Horizontal stacked 100% bar chart** to show the percentage split.
   - Added additional charts for other questions (e.g., genres, release dates).
   - Screenshot: [stacked-bar-chart.png](screenshots/stacked-bar-chart.png)

7. **Secret Mission - Refreshing Data**:
   - Updated the dataset in S3 by uploading a new version of `netflix_titles.csv`.
   - Refreshed the dataset in QuickSight to reflect changes in visualizations.
   - Screenshot: [data-refresh.png](screenshots/data-refresh.png)

8. **Finishing Touches**:
   - Added descriptive titles to charts:
     - # of Movies/TV Shows by Release Year
     - # of Movies vs TV Shows by Release Year
     - # of Thrillers, TV Comedies, Action & Adventure
     - # of Thrillers, TV Comedies, Action & Adventure (released ≥ 2015)
     - # of Titles Added by Date
     - Secret Mission: # of Movies/TV Shows by Country
   - Published the dashboard as `Netflix titles analysis`.
   - Exported the dashboard as a PDF.
   - Screenshot: [final-dashboard.png](screenshots/final-dashboard.png)

9. **Cleaned Up Resources**:
   - Deleted the QuickSight account via **Manage QuickSight > Account Settings > Delete account**.
   - Emptied and deleted the S3 bucket `nextwork-quicksight-project-momen` and its objects (`netflix_titles.csv`, `manifest.json`).

## Answers to Project Tasks
- **Step #0: Objective**:
  - In this project, I will create a dashboard in Amazon QuickSight to visualize Netflix data trends by uploading a dataset to S3, connecting it to QuickSight, and building charts to learn data analysis and visualization.

- **Step #2: Task Description**:
  - In this step, I will create an S3 bucket and upload `netflix_titles.csv` and `manifest.json` because S3 stores the dataset for QuickSight to access and analyze.

- **Step #3: Task Description**:
  - In this step, I will sign up for a QuickSight account and configure it to access my S3 bucket because QuickSight needs this setup to create visualizations from the dataset.

- **Step #3: Cost of QuickSight**:
  - Creating a QuickSight account costs nothing with the free trial, but I must delete the account after the project to avoid charges.

- **Step #4: Task Description**:
  - In this step, I will connect my S3 bucket to QuickSight using `manifest.json` because it enables QuickSight to understand and visualize the Netflix dataset.

- **Step #5: Task Description**:
  - In this step, I will create initial visualizations (e.g., donut and bar charts) because they help analyze Netflix data trends like release years and content types.

- **Step #6: Task Description**:
  - In this step, I will create additional visualizations with filters because they answer specific questions about the Netflix dataset and enhance the dashboard.

- **Step #7: Task Description**:
  - In this step, I will add titles, publish, and export the dashboard because this makes it professional and shareable with others.

- **Final Recap: Key Services and Concepts**:
  - **Services**: Amazon S3, Amazon QuickSight
  - **Concepts**: S3 buckets, dataset storage, QuickSight datasets, data visualization, chart types (donut, bar, stacked bar), dashboard publishing, data refresh

## Lessons Learned
- **Amazon S3**: Scalable storage for datasets, accessible by other AWS services like QuickSight.
- **Amazon QuickSight**: A beginner-friendly tool for creating interactive data visualizations and dashboards.
- **Manifest File**: `manifest.json` maps S3 data to QuickSight for accurate visualization.
- **Chart Types**: Donut, bar, and stacked bar charts visualize different data perspectives.
- **Free Tier**: Used Free Tier settings and deleted resources to avoid costs.

## Challenges
- Ensured the QuickSight region matched the S3 bucket region (`us-east-1`) to avoid connection errors.
- Unchecked “Add Paginated Reports” during QuickSight signup to prevent charges.
- Updated `manifest.json` correctly with the S3 URL to ensure QuickSight recognized the dataset.
- Emptied all object versions in S3 before deleting the bucket.

## Screenshots
- S3 Bucket Objects: [s3-bucket-objects.png](screenshots/s3-bucket-objects.png)
- QuickSight Setup: [quicksight-setup.png](screenshots/quicksight-setup.png)
- S3 Connection: [s3-connection.png](screenshots/s3-connection.png)
- First Visualization: [first-visualization.png](screenshots/first-visualization.png)
- Stacked Bar Chart: [stacked-bar-chart.png](screenshots/stacked-bar-chart.png)
- Data Refresh (Secret Mission): [data-refresh.png](screenshots/data-refresh.png)
- Final Dashboard: [final-dashboard.png](screenshots/final-dashboard.png)

## Next Steps
- Share the exported dashboard PDF on LinkedIn and the NextWork community.
- Update the main repo README with this project’s completion.
- Start the next project: “Cloud Security with AWS IAM” to deepen IAM knowledge.
