# Top UK YouTubers 2024 Analysis

## Project Overview

This project aims to provide insights into the top performing UK Youtubers to form marketing collaborations with throughout the year 2024.By analysing the data, we seek to identify the top YouTubers in the UK based on subscriber count, videos uploaded and views accumulated, so that I can decide on which channels would be best to run marketing campaigns with to generate a good ROI. 

## Data Sources

The primary datasets used for this project is from Kaggle [download here](https://www.kaggle.com/datasets/bhavyadhingra00020/top-100-social-media-influencers-2024-countrywise?resource=download)

## Tools

- Excel - Exploring the data
- SQL - Server	Cleaning, testing, and analyzing the data
- Power BI - Visualizing the data via interactive dashboards
- GitHub - Hosting the project documentation and version control

## Data Transformation

Select the required columns and Extract the channel name from the 'NOMBRE' column 




  
<img width="1223" height="865" alt="sql1" src="https://github.com/user-attachments/assets/92dfe99f-49df-426a-bf3c-0b8daac4461d" />

## Create the SQL view

1. Create a view to store the transformed data
2. Cast the extracted channel name as VARCHAR(100)
3. Select the required columns from the top_uk_youtubers_2024 SQL table

   

<img width="1076" height="297" alt="sql2" src="https://github.com/user-attachments/assets/2fe6e549-4b2e-475f-b38d-307fe7c606ab" />

## Row count check


<img width="1240" height="617" alt="sql3" src="https://github.com/user-attachments/assets/d117a5ce-eac6-42fb-815b-9cfb6c70cf73" />

## Column count check



<img width="1235" height="620" alt="sql4" src="https://github.com/user-attachments/assets/d86dd252-9ebf-4ddd-84c8-ee503716e7ad" />

## Data type check




<img width="1233" height="610" alt="sql5" src="https://github.com/user-attachments/assets/7f93d2d6-b93f-47fe-af2e-b5f7d336b3a5" />

## Duplicate count check




<img width="1228" height="620" alt="sql6" src="https://github.com/user-attachments/assets/4ccf8853-a546-4d1e-a387-790a5afa2a01" />

## Visualization

### PowerBI Dashboard




<img width="1291" height="721" alt="top_uk_youtubers_2024" src="https://github.com/user-attachments/assets/18712148-a1c4-43c6-af82-9c0a50998491" />



## DAX Measures

Total Subscribers (M)
```DAX
Total Subscribers (M) = 
VAR million = 1000000
VAR sumOfSubscribers = SUM(view_uk_youtubers_2024[total_subscribers])
VAR totalSubscribers = DIVIDE(sumOfSubscribers,million)

RETURN totalSubscribers
```

## Total Views (B)
```DAX
Total Views (B) = 
VAR billion = 1000000000
VAR sumOfTotalViews = SUM(view_uk_youtubers_2024[total_views])
VAR totalViews = ROUND(sumOfTotalViews / billion, 2)
RETURN totalViews
```

## Total Videos
```DAX
Total Videos = 
VAR totalVideos = SUM(view_uk_youtubers_2024[total_videos])

RETURN totalVideos
```

## Average Views Per Video (M)
```DAX
Average Views per Video (M) = 
VAR sumOfTotalViews = SUM(view_uk_youtubers_2024[total_views])
VAR sumOfTotalVideos = SUM(view_uk_youtubers_2024[total_videos])
VAR  avgViewsPerVideo = DIVIDE(sumOfTotalViews,sumOfTotalVideos, BLANK())
VAR finalAvgViewsPerVideo = DIVIDE(avgViewsPerVideo, 1000000, BLANK())

RETURN finalAvgViewsPerVideo
```

## Subscriber Engagement Rate
```DAX
Subscriber Engagement Rate = 
VAR sumOfTotalSubscribers = SUM(view_uk_youtubers_2024[total_subscribers])
VAR sumOfTotalVideos = SUM(view_uk_youtubers_2024[total_videos])
VAR subscriberEngRate = DIVIDE(sumOfTotalSubscribers, sumOfTotalVideos, BLANK())

RETURN subscriberEngRate 
```

## Views per subscriber
```DAX
Views Per Subscriber = 
VAR sumOfTotalViews = SUM(view_uk_youtubers_2024[total_views])
VAR sumOfTotalSubscribers = SUM(view_uk_youtubers_2024[total_subscribers])
VAR viewsPerSubscriber = DIVIDE(sumOfTotalViews, sumOfTotalSubscribers, BLANK())

RETURN viewsPerSubscriber 
```

## Analysis
Findings:

### Who are the top 10 YouTubers with the most subscribers?

- NoCopyrightSounds	
- DanTDM
- Dan Rhodes
- Miss Katy	
- Mister Max
- KSI	
- Jelly	
- Dua Lipa
- Sidemen	
- Ali-A	

### Which 3 channels have uploaded the most videos?

-	GRM Daily	
-	Manchester City	
-	Yogscast

### Which 3 channels have the most views?

-	DanTDM	
-	Dan Rhodes	
-	Mister Max

### Which 3 channels have the highest average views per video?

- Mark Ronson	
- Jessie J	
- Dua Lipa

### Which 3 channels have the highest views per subscriber ratio?

-	GRM Daily
-	Nickelodeon	
-	Disney Junior UK

### Which 3 channels have the highest subscriber engagement rate per video uploaded?

-	Mark Ronson	
-	Jessie J	
-	Dua Lipa








 


