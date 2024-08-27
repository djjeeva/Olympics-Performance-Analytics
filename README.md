
# Olympics Performance Analytics

## Introduction:
The 2024 Olympic Games bring together athletes from around the globe, competing at the highest level. This project focuses on analyzing and visualizing the performance of athletes, the distribution of medals, and the participation of countries in the 2024 Olympics. Historical data from 1896 to 2022 is also included to provide context and identify long-term trends.

## Key Highlights:

- Athlete Participation: 11,110 athletes (5,655 male and 5,455 female)
- Medal Tally: 2,282 medals (752 Gold, 760 Silver, 814 Bronze)
- Leading Nation: USA with 330 medals
- Participating Countries: 206
- Dominant Age Group: 26-30 years

## Project Structure

The project integrates various tools and techniques to develop a dynamic and interactive dashboard:

- **Python for Data Integration:**  
  Instead of manually updating data, Python was used to directly connect to the dataset on Kaggle. This ensures that the data is always current, eliminates the need for local storage, and allows for automatic updates.

- **Interactive Dashboard Features:**  
  The dashboard includes dynamic visuals that allow users to explore specific sports or view data in a consolidated manner, providing a more engaging user experience.

- **Dynamic Data Presentation:**  
  The dashboard updates key metrics in real-time as filters are applied, giving users customized insights based on their specific interests.

- **Diverse Visualization Techniques:**  
  The project uses various visuals to represent data on athlete preferences, medal counts, and country performances. Historical data enhances these visuals, allowing for a deeper understanding of trends over time.

## Python Script to Directly Import Kaggle Dataset into Power BI.

Below is a Python script that downloads and loads data from Kaggle for the Paris 2024 Olympic Summer Games.

```python
import kaggle
import os
import pandas as pd

# Set Kaggle API credentials directory
os.environ['KAGGLE_CONFIG_DIR'] = 'C:/Users/JEEVA/.kaggle'  # Update this path to your Kaggle configuration directory

# Specify the dataset identifier
dataset = 'piterfm/paris-2024-olympic-summer-games'

# Set the download path
download_path = 'C:/Users/JEEVA/Downloads/Olympics dashboard/history' # Change this to your preferred download directory

# Remove existing files in the folder to prevent duplicates or outdated files
for file in os.listdir(download_path):
    file_path = os.path.join(download_path, file)
    try:
        if os.path.isfile(file_path):
            os.unlink(file_path)  # Delete the file
            print(f"Deleted {file_path}")
    except Exception as e:
        print(f"Error deleting {file_path}: {e}")

# Download the dataset using the Kaggle API and unzip the files
kaggle.api.dataset_download_files(dataset, path=download_path, unzip=True)

# List of CSV files to be imported
csv_files = [
    'athletes.csv',
    'events.csv',
    'medallists.csv',
    'medals.csv',
    'medals_total.csv',
    'schedules.csv',
    'schedules_preliminary.csv',
    'teams.csv',
    'torch_route.csv',
    'venues.csv'
]

# Initialize a dictionary to hold DataFrames
dataframes = {}

# Iterate through each CSV file and load it into a DataFrame
for file in csv_files:
    # Construct the full path to the CSV file
    file_path = os.path.join(download_path, file)
    
    # Load the CSV file into a Pandas DataFrame
    df = pd.read_csv(file_path)
    
    # Add the DataFrame to the dictionary using the file name as the key
    table_name = file.split('.')[0]  # Remove the .csv extension
    dataframes[table_name] = df


## Analytics Report
![Screenshot 2024-08-23 141823](https://github.com/user-attachments/assets/e1b5078f-394e-4415-8252-8e64fa4c5fec)
![Screenshot 2024-08-23 142021](https://github.com/user-attachments/assets/3521c93d-2f92-484a-8cda-6f4d54b93034)
![Screenshot 2024-08-23 142035](https://github.com/user-attachments/assets/e1dfe34c-7c03-4b99-85b9-8c4839a9290c)
![Screenshot 2024-08-23 142050](https://github.com/user-attachments/assets/c371091d-a806-471f-b0bc-1ca114aab298)




## Distinctive Features

- **Real-time Data Access:**  
  Direct integration with Kaggle using Python ensures up-to-date information.

- **Enhanced User Interaction:**  
  The dashboard's dynamic visuals and controls make it highly interactive and user-friendly.

- **Customized Insights:**  
  Metrics adjust in real-time based on user selections, ensuring relevant and personalized data presentation.

- **Historical Context:**  
  The analysis includes data from previous Olympics, offering a comprehensive view of trends and patterns.



## Target Audience

- **Event Organizers:**  
  Highlights trends and areas where future events can be enhanced, offering valuable data-driven guidance for planning.

- **General Audience:**  
  Transforms complex Olympic data into an engaging and accessible format, making it easier for everyone to explore and understand.

- **Analysts:**  
  Provides in-depth insights into the performance of athletes and countries, aiding in detailed performance evaluations.
## Conclusion

This dashboard provides an in-depth analysis of the 2024 Olympics, coupled with historical insights. The integration of Python and interactive visuals makes this project both innovative and practical, offering valuable tools for analysts, organizers, and the general public.


### Dashboard Link
If you're interested in exploring and interacting with the dashboard,[click here](https://app.powerbi.com/view?r=eyJrIjoiMDY2ODNiMTctMWRjYy00ODM0LWI4ZWYtODk1ZWI0ZjQzYzg1IiwidCI6Ijc1NWUxZmNkLWY3YzAtNDBmNi1iMWRhLTg5NjkyNDVkNjg1ZCJ9)

## Contact
For any questions or further information, please contact    [Jeevitha D J](http://jeevithadj1999@gmail.com#fragment)









