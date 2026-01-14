# PRODIGY_DS_02: Titanic Dataset - Exploratory Data Analysis

## 🚢 Project Overview
This project presents a detailed and comprehensive Exploratory Data Analysis (EDA) of the historic Titanic dataset, aiming to uncover meaningful insights and patterns that influenced passenger survival during the tragic sinking of the RMS Titanic in 1912.

The Titanic disaster remains one of the most well-known maritime tragedies in history, and this dataset provides a valuable opportunity to explore how social, economic, and demographic factors played a crucial role in determining survival outcomes. Through systematic data exploration and visualization, this analysis transforms raw historical data into actionable insights.

## 📊 Dataset Information
- **Source**: Prodigy InfoTech / Kaggle Titanic Dataset
- **Records**: 891 passengers
- **Original Features**: `PassengerId`, `Survived`, `Pclass`, `Name`, `Sex`, `Age`, `SibSp`, `Parch`, `Ticket`, `Fare`, `Cabin`, `Embarked`
- **Engineered Features**: `Has_Cabin`, `Title`, `Family_Size`, `Age_Group`, `Fare_Category`, `Is_Alone`

## 🛠️ Tools & Technologies

 Python 3.9+, Pandas, NumPy
 Matplotlib, Seaborn, Jupyter Notebook


## 📋 Methodology

### 1. Data Loading & Initial Exploration
- Loaded dataset and examined structure (891 passengers, 12 features)
- Analyzed data types, distributions, and statistical summaries
- Identified missing value patterns

### 2. Data Cleaning
- **Age**: Filled 177 missing values (19.9%) with median (28.0 years)
- **Embarked**: Filled 2 missing values (0.2%) with mode ('S' - Southampton)
- **Cabin**: Created binary `Has_Cabin` indicator (77.1% missing), dropped original column
- **Result**: Zero remaining missing values

### 3. Feature Engineering
Created 6 new predictive features:

| Feature | Description | Purpose |
|---------|-------------|---------|
| `Title` | Extracted from Name (Mr, Mrs, Miss, Master, Rare) | Social status indicator |
| `Family_Size` | SibSp + Parch + 1 | Family grouping effect |
| `Age_Group` | Child(0-12), Teen(13-18), Adult(19-35), Middle Age(36-60), Senior(60+) | Age categorization |
| `Fare_Category` | Low, Medium, High, Very High (quartiles) | Wealth proxy |
| `Is_Alone` | 1 if Family_Size == 1 | Solo traveler indicator |
| `Has_Cabin` | 1 if cabin data exists | Deck location proxy |

### 4. Exploratory Analysis Dimensions
- Univariate analysis (survival distribution)
- Bivariate analysis (gender, class, age effects)
- Multivariate interactions (gender+class, age+family)
- Correlation analysis across all features

### 5. Visualization Suite (12+ Charts)

 Bar charts - Histograms - Box plots - Pie charts
 Heatmaps - Multi-panel grids - Statistical overlays


## 🔍 Key Findings

### 📈 Overall Statistics
  
 Total Passengers: 891
 Survived: 342 (38.38%)
 Died: 549 (61.62%)

### 🎯 Critical Survival Factors (Ranked by Impact)

| Rank | Factor | Survival Rate | Impact |
|------|--------|---------------|---------|
| 1 | **Female** | **74.20%** | 3.9x vs males |
| 2 | **1st Class** | **62.96%** | 2.6x vs 3rd class |
| 3 | **Has Cabin** | **66.67%** | 2.2x vs no cabin |
| 4 | **Child (<18)** | **54.02%** | Priority evacuation |
| 5 | **Family Size 2-4** | **53-58%** | Coordination advantage |

### Detailed Breakdown

#### Gender (Correlation: +0.543)
    
    Female: 74.20% (233/314)
    Male: 18.89% (109/577)



#### Passenger Class (Correlation: -0.338)
    
   1st Class: 62.96% (136/216)
   2nd Class: 47.28% (87/184)
   3rd Class: 24.24% (119/491)



#### Age Groups
 
  Child (0-12): 58.67%
  Teen (13-18): 38.46%
  Adult (19-35): 36.25%
  Middle Age: 42.11%
  Senior (60+): 23.81%

#### Family Size Sweet Spot
   Size 1 (Alone): 30.35%
   Size 2: 58.71%
   Size 3: 57.84%
   Size 4: 53.33%
   Size 7+: 11.11%

## 📈 Visualizations Catalog

### Complete List (7 Charts Generated)
| File | Analysis Type | Key Insight |
|------|---------------|-------------|
| `vis1_survival.png` | Overall breakdown | 38% survival baseline |
| `vis2_gender.png` | Gender disparity | 74%F vs 19%M |
| `vis3_class.png` | Class gradient | 63%→47%→24% |
| `vis4_age.png` | Age histograms | Bimodal survivor pattern |
| `vis5_family.png` | Family dynamics | 2-4 member peak |
| `vis6_correlation.png` | Feature matrix | Top correlations |
| `vis7_gender_class.png` | Gender+Class interaction | F1st=97%, M3rd=13% |

### 🎯 Top Insights Showcase
SURVIVAL- <img width="4202" height="1773" alt="vis1_survival" src="https://github.com/user-attachments/assets/ad6d81dd-e7f2-441c-a155-0974cd8ef986" />
CLASS GRADIENT -<img width="2984" height="2107" alt="vis3_class" src="https://github.com/user-attachments/assets/a4a8f33d-5733-4161-b7be-fa0a58090c2c" />
FAMILY -<img width="2984" height="1649" alt="vis5_family" src="https://github.com/user-attachments/assets/8f7dc98c-a805-46fe-a6f4-0e53cd2d6d07" />
GENDER DISPARITY -<img width="2984" height="2105" alt="vis2_gender" src="https://github.com/user-attachments/assets/ed9206e5-282c-401b-9b4f-a1b4aeef374a" />
GENDER+CLASS - <img width="3570" height="2370" alt="vis7_gender_class" src="https://github.com/user-attachments/assets/d3847dfe-12f3-40de-b7cd-3a43989cd9ea" />
CORRELATION HEATMAP -<img width="2639" height="2369" alt="vis6_correlation" src="https://github.com/user-attachments/assets/cc1e379d-0878-48f4-a8d4-c3255da7ee1b" />



## 💡 Actionable Insights for Maritime Safety

1. **Evacuation Priority**: "Women & children first" saved ~55% vs 19% male baseline
2. **Class Access**: 1st class proximity to lifeboats = 2.6x survival advantage
3. **Deck Location**: Cabin assignment (upper decks) = lifeboat proximity
4. **Group Coordination**: Small families (2-4) navigated chaos 1.7x better
5. **Resource Equity**: Eliminate socioeconomic barriers in emergencies


## 🚀 How to Replicate

### Prerequisites
```bash
pip install pandas==2.0.3 numpy==1.24.3 matplotlib==3.7.2 seaborn==0.12.2 jupyter==1.0.0


# 1. Clone repository
git clone https://github.com/adityapatil2005/Prodigy_TASK02/tree/main
cd PRODIGY_DS_02

# 2. Launch Jupyter
jupyter notebook

# 3. Open notebook
Task_ap2-checkpoint

# 4. Run all cells (Ctrl+F9) - ~5 minutes execution

