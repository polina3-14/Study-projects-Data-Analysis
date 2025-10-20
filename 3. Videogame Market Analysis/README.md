# Video Game Market Analysis Project

A comprehensive analysis of the video game market to identify patterns that determine successful games for the "Стримчик" game store.

## 📋 Project Overview

This project analyzes historical video game sales data up to 2016 to help "Стримчик" game store make data-driven decisions about:
- Identifying potentially popular products
- Planning advertising campaigns for 2017
- Understanding regional market differences
- Evaluating factors that influence game success

## 🎯 Business Problem

The analysis was conducted in December 2016 to support marketing campaigns planned for 2017. The goal is to identify patterns that determine game success to help the store focus on potentially popular products.

## 📊 Data Sources

### `games.csv`
- **Records**: 16,715 entries initially (16,444 after preprocessing)
- **Time Period**: 1980-2016
- **Key Features**:
  - **Game Information**: Name, Platform, Year of Release, Genre
  - **Regional Sales**: North America, Europe, Japan, Other regions (in millions of copies)
  - **Ratings**: Critic scores (0-100), User scores (0-10), ESRB age rating
  - **Calculated**: Total global sales

## 🛠️ Technical Implementation

### Data Preprocessing
- **Missing Values**: Removed missing game names and release years
- **Data Types**: Converted year to integer, user scores to float
- **Duplicates**: Removed 1 duplicate entry
- **Ratings**: Replaced missing ESRB ratings with -1
- **New Feature**: Added total sales across all regions

### Analytical Approach

#### 1. Historical Analysis
- Examined game release patterns from 1980-2016
- Identified peak release years (2008-2009)
- Analyzed platform lifecycle (average 7 years)

#### 2. Platform Analysis
- Identified most popular platforms (PS4, XOne, 3DS)
- Analyzed sales trends and platform lifecycles
- Determined relevant period: 2014-2016 for 2017 planning

#### 3. Review Impact Analysis
- Correlation analysis between critic/user reviews and sales
- Platform-specific review impact assessment

#### 4. Genre Popularity
- Median sales analysis by genre
- Regional genre preferences

#### 5. Regional User Profiles
- Top platforms and genres for NA, EU, JP markets
- ESRB rating preferences by region

### Statistical Hypothesis Testing

#### Hypothesis 1: Platform Rating Equality
- **Test**: User ratings for Xbox One vs PC platforms
- **Method**: Two-sample t-test
- **Result**: No significant difference found

#### Hypothesis 2: Genre Rating Differences  
- **Test**: User ratings for Action vs Sports genres
- **Method**: Two-sample t-test
- **Result**: Significant difference found (Action ratings higher)

## 📈 Key Findings

### Market Trends
- **Platform Lifecycle**: Average 7 years for gaming platforms
- **Release Peaks**: Highest game production in 2008-2009
- **Market Shift**: Decline in traditional game sales post-2009, likely due to mobile gaming

### Platform Insights
- **Most Promising 2017 Platforms**: PS4, XOne, 3DS
- **Highest Median Sales**: XOne, PS4, WiiU, Wii
- **PC Stability**: Consistent sales due to hardware upgradability

### Review Impact
- **Critic Reviews**: Strong positive correlation with sales across all major platforms
- **User Reviews**: Minimal impact on sales
- **Recommendation**: Focus on critic scores for purchasing decisions

### Genre Performance
- **Top Genres**: Shooter, Sports, Platform
- **Lowest Genres**: Puzzle, Adventure
- **Profitability Note**: Shooter games may have high production costs

### Regional Profiles

#### North America
- **Top Platforms**: PS4 (41.3%), XOne (27.3%)
- **Popular Genres**: Action, Shooter, Sports  
- **Rating Preference**: Mature (17+)

#### Europe
- **Top Platforms**: PS4 (44.5%), XOne (24.2%)
- **Popular Genres**: Shooter, Action, Sports
- **Rating Preference**: Mature (17+)

#### Japan
- **Top Platforms**: 3DS (35.3%), PS4 (27.1%)
- **Popular Genres**: Role-Playing, Action, Misc
- **Rating Preference**: Teen (13+)
- **Key Difference**: Shooters not popular

## 🎯 Business Recommendations

### For 2017 Planning
1. **Platform Focus**: Prioritize PS4, XOne, and 3DS games
2. **Genre Strategy**: Stock Shooter, Sports, and Platform games
3. **Review Consideration**: Use critic scores as primary quality indicator
4. **Regional Adaptation**: 
   - NA/EU: Focus on mature-rated action/shooter games
   - Japan: Focus on teen-rated role-playing games

### Purchasing Strategy
- Target games with high critic scores (>75)
- Consider regional platform preferences
- Balance popular genres with production cost considerations

## 📝 Project Structure

1. **Data Loading & Preprocessing**
2. **Exploratory Data Analysis**
   - Historical release patterns
   - Platform lifecycle analysis  
   - Review impact assessment
   - Genre popularity
3. **Regional User Profiling**
4. **Statistical Hypothesis Testing**
5. **Conclusions & Recommendations**

## 🚀 How to Use

```bash
pip install pandas matplotlib scipy numpy seaborn missingno
```

### Running the Analysis
1. Clone the repository
2. Ensure dataset `games.csv` is available
3. Run the Jupyter notebook: `videogame_market_analysis.ipynb`
4. Follow the step-by-step analysis methodology

## 📝 Conclusion

This analysis provides a data-driven foundation for "Стримчик" to make informed decisions about game acquisitions and marketing strategies for the 2017 business year and provides some valuable insight:
1. The gaming market shows clear regional differences requiring tailored strategies
2. Critic reviews are more reliable predictors of success than user reviews
3. Platform lifecycle understanding is crucial for timely inventory decisions
4. Genre preferences reflect cultural differences across regions
