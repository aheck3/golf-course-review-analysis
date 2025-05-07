# Exploring Consumer Tastes and Preferences in Indianapolis Golf Courses through Sentiment-Based Review Analysis

This project analyzes over 6,300 golfer reviews from GolfPass to uncover key themes and preferences that influence course ratings and customer satisfaction. Using natural language processing techniques, I explored what matters most to players — such as bunker conditions, staff interactions, pace of play, and course maintenance. The analysis was conducted using Python, VADER sentiment scoring, and BERTopic, and it was completed as my final project for the MSBA Unstructured Data Analytics course at the University of Notre Dame.

## Background

Growing up on the Southside of Indianapolis, I’ve played dozens of courses in the area — from public courses to semi-private clubs. I’ve always been curious about what makes certain courses more enjoyable than others, and what specific elements drive a golfer to leave a positive or negative review.

GolfPass offers thousands of player reviews that go far beyond star ratings, providing rich comment data on personal experiences. By analyzing this unstructured text feedback, I hoped to merge my business acumen with my knowledge and passion for golf to help courses better understand their customers and improve the on-course experience. My goal was to identify what golfers truly value — and how courses can use those insights to strengthen their brand, boost customer satisfaction, and drive long-term success.

## Objective

The goal of this project was to uncover what golfers truly care about when it comes to the courses they play. I hoped to gain insights into the factors that influence how players rate and review a course — from conditions and design to staff interactions and pace of play. By identifying the common themes in player feedback, I aimed to highlight what enhances the overall experience and what detracts from it.

Key research questions included:

What aspects of a course do golfers consistently mention in their reviews?

What do players value most, and what frustrates them when they reflect on a round?

How do sentiment trends vary across different courses in the Indianapolis area?

I believe this type of analysis has real-world applications. If a course can identify where golfers derive the most value, they can focus efforts on those areas to elevate the player experience. In turn, this can lead to stronger customer satisfaction, better public perception, and ultimately, increased revenue.

## Data

All reviews were scraped from GolfPass, a site affiliated with Golf Channel and NBC Sports. I focused on the Indianapolis region and collected:

- Course names and unique URLs  
- Over 6,300 user-submitted review comments from 45+ courses  

The data was cleaned, de-duplicated, and filtered to retain only courses with at least 20 reviews. The final dataset included 6,300+ comments.

## Methodology

- **Web Scraping**: Used BeautifulSoup to scrape course names and review text  
- **Sentiment Analysis**: Applied VADER to assign a sentiment score (-1 to +1) to each comment  
- **Topic Modeling**: Used BERTopic with a custom TF-IDF transformer to extract and group common themes from reviews  

Three topic models were developed:
- One covering all Indianapolis reviews  
- One focused specifically on my home course, The Legends Golf Club  
- One filtered to only include neutral or negative sentiment reviews (≤ 0.10 compound score)

## Results

Across all reviews, several themes emerged consistently:

- Bunkers and sand conditions (often cited as unplayable)
- Pace of play (especially during peak hours)
- Friendliness and professionalism of course staff
- Course wetness and drainage (especially after rain)

The courses with the highest average sentiment scores were:
1. Buffer Park Golf Course  
2. Deer Creek Golf Club  
3. Bear Slide Golf Club  
4. Arrowhead Golf Course  
5. Eagle Pines Golf Club  


## Conclusion

This project shows that golfers care deeply about factors that go beyond just layout and design. Maintenance, friendliness of staff, pace of play, and even bunker conditions are consistent drivers of satisfaction or frustration.

For public and semi-private courses hoping to improve reputation and increase revenue, these insights can directly inform operations and staffing decisions. Reviewing and acting on golfer feedback can lead to improved ratings, stronger customer loyalty, and increased demand.

## Reproducibility

This analysis can be applied to any other region by simply updating the GolfPass region URL. For example, in the scraping step:

```python
top_courses = 'https://www.golfpass.com/travel-advisor/destinations/57-indianapolis-in/'
```

To analyze courses in Tampa, Orlando, or any other area, replace that URL with the correct destination link from the GolfPass “Travel” section. The rest of the scraping and analysis pipeline will adjust accordingly.

## Files Included

- `golf-course-review-analysis.qmd`: Quarto source file  
- `golf-course-review-report.html`: Final rendered report  
- `golf-course-review-presentation.pdf`: Presentation slides  
- `data/`: Raw CSVs with course names and reviews  
- `topic_model_golf.joblib`: Saved BERTopic model for reuse

## Author

Alex S. Heck  
MSBA, University of Notre Dame  
GitHub: [@aheck3](https://github.com/aheck3)

## View the Report

You can view the full HTML report here:  
**https://aheck3.github.io/golf-course-review-analysis/golf-course-review-report.html**
