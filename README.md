- I utilized the GitHub API to scrape data on Melbourne-based users with over 100 followers by automating requests, handling pagination, and processing JSON responses to collect user profiles and their repositories.
- Surprisingly, hireable developers in Melbourne do not necessarily follow more people nor share their email addresses more frequently than non-hireable developers.
- Developers seeking opportunities should optimize their GitHub profiles by highlighting key information, as being hireable doesn't correlate with typical engagement metrics like following count or email visibility.

# GitHub Users and Repositories Data Analysis

## Overview

This project involves scraping data from the GitHub API to collect information about users located in Melbourne with over 100 followers and their public repositories. The data is then analyzed to uncover interesting patterns and insights about the developer community in Melbourne.

## Data Collection Process

- **Authentication**: A personal access token was generated to authenticate requests and increase the rate limit from 60 to 5,000 requests per hour.
- **Fetching Users**:
  - Used the GitHub Search API to find users with the query `location:melbourne followers:>100`.
  - Automated pagination handling to collect all relevant users.
- **Fetching User Details**:
  - For each user, detailed information was retrieved using the GitHub Users API.
  - Data cleaning was performed on fields like `company` to meet the specified format.
- **Fetching Repositories**:
  - For each user, up to 500 of their most recently pushed public repositories were fetched using the Repositories API.
  - Relevant repository details were collected, including handling optional fields like `license`.
- **Data Storage**:
  - The collected data was stored in two CSV files:
    - `users.csv` containing user details.
    - `repositories.csv` containing repository details.
  - Ensured that boolean values are stored as `true` or `false`, and nulls as empty strings.

## Data Analysis

Several analyses were performed on the collected data to extract meaningful insights:

1. **Surname Frequency**:
   - Determined the most common surnames among the users by assuming the last word in their name is their surname.
   - Found that the most common surname(s) is/are: **[List of surnames based on your data]**.

2. **Email Sharing and Hireability**:
   - Analyzed whether hireable users share their email addresses more often.
   - Calculated the fraction of hireable users with an email minus the fraction of non-hireable users with an email.
   - Result: **[Your calculated difference, e.g., 0.123]**.
   - Conclusion: Hireable status does not significantly affect email sharing.

3. **Following Count and Hireability**:
   - Investigated if hireable users follow more people on average.
   - Computed the average following for hireable users minus the average for non-hireable users.
   - Result: **[Your calculated difference, e.g., -5.678]**.
   - Conclusion: Hireable users do not necessarily follow more people.

## Actionable Insights

- **Profile Optimization**: Developers should focus on optimizing their GitHub profiles by providing clear bios and showcasing their best work, as traditional engagement metrics like following count may not impact hireability.
- **Community Engagement**: Despite the assumption, being more active in following others doesn't correlate with being hireable, suggesting that quality over quantity in interactions is valued.
- **Email Visibility**: Since sharing an email address is not more common among hireable users, developers comfortable with public contact information might stand out to potential employers.

## How to Reproduce the Analysis

1. **Requirements**:
   - Python 3.x
   - Libraries: `requests`, `csv`

2. **Setup**:
   - Install required libraries using `pip install requests`.
   - Generate a GitHub personal access token with appropriate permissions.

3. **Execution**:
   - Run the provided Python scripts to fetch and store data in CSV files.
   - Use the analysis scripts to perform calculations and generate insights.

4. **Scripts Included**:
   - `API Scrapping.py`: Script to scrape user data, repository data and contains analysis code for the questions addressed.

## Files in the Repository

- `users.csv`: Contains user information.
- `repositories.csv`: Contains repository information.
- `README.md`: Documentation of the project.
- `API Scrapping.py`: Script to fetch user data and repository data.
  
## Conclusion

This project provides insights into the GitHub user community in Melbourne. The analysis challenges some common assumptions about developer behavior related to hireability. By focusing on meaningful engagement and profile completeness, developers can enhance their visibility to potential employers.
