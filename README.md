# Tracking and Evaluating Air Quality Trends in Bangalore

Air pollution is the second leading cause of death and the top environmental contributor to fatalities worldwide, responsible for over 8 million deaths in 2021. The effects of air pollution are everywhere, even though we can’t see them with the naked eye. From birth defects to respiratory illnesses, it impacts us in ways we may not even realize. As living beings on this planet, we have the right to breathe clean air—air that doesn’t harm or make us sick.

I took up this project because I am passionate about studying and advocating for a healthy and clean environment—a birthright of every living being, including the plants and trees that surround us. I firmly believe in the saying: **""We do not inherit the Earth from our ancestors; we borrow it from our children."**

Growing up in Bangalore, a cosmopolitan city and the Silicon Valley of India, I developed a deep curiosity about its air quality and environmental state. Despite its rapid growth, access to reliable air quality data was limited, creating a significant gap in understanding the city's environmental health. Reliable data on air pollution are essential for identifying problems and taking corrective actions to improve air quality. Such data inform us about the pollution levels in the air we breathe and guide efforts toward a cleaner future.
 
This project focuses on fetching and evaluating air quality data for Bangalore, India, over multiple years. By calculating a weighted air quality score and categorizing it into quality labels, the project provides a comparative assessment of air quality trends across various locations within the city. This information empowers residents to make informed decisions about living in or moving out of certain areas based on the quality of air they are exposed to.

The for the project was sourced from OpenAQ platform, an open-source, open-access data platform that aggregates and harmonizes open air quality data from across the globe and gives unfettered access to the data needed to analyze, communicate and advocate for clean air. We access the data through OpenAQ's API.

However, the air quality parameters collected from sensors deployed across Bangalore are limited and not consistently measured across all areas and years. Therefore, we narrowed our focus to the following key parameters for evaluation:

**1. Carbon Monoxide (CO)**

**2. Nitrogen Dioxide (NO2)**

**3. Sulfur Dioxide (SO2)**

**4. Particulate Matter (PM2.5)**

To compare air quality across locations and years, I calculated a **Weighted Air Quality Score**. This score accounts for the relative health impact of different pollutants using weights and standard limits defined by environmental organizations like the World Health Organization (WHO).

**Parameters and Weights**

Carbon Monoxide (CO)
- Weight: 1.0
- Limit: 34 μg/m³
Used to assess acute effects over short-term exposure periods.

Nitrogen Dioxide (NO₂)
- Weight: 1.2
- Limit: 400 μg/m³
Protects against NO₂’s respiratory effects.

Sulfur Dioxide (SO₂)
- Weight: 1.2
- Limit: 1600 μg/m³
A higher limit due to acute impacts occurring at elevated concentrations.

Particulate Matter (PM2.5)
- Weight: 1.5
- Limit: 250 μg/m³
Assigned the highest weight because PM2.5 is harmful even at low concentrations.

**Evaluation Methods**
Due to data limitations, I implemented two approaches to evaluate air quality trends:

*Subset Analysis:*
Focused on areas with consistent data across selected years (e.g., 2018–2025). This method ensures accuracy but excludes areas with incomplete data.

*Imputation:*
For areas with missing data in certain years, I used imputation techniques to estimate pollutant values. This method includes more areas but introduces assumptions about missing data.

**Subset Analysis Result**

| Name                                   | Weighted Score | Quality Label |
| -------------------------------------- | -------------- | ------------- |
| Hombegowda Nagar, Bengaluru - KSPCB    | 0.045          | Good          |
| Jayanagar 5th Block, Bengaluru - KSPCB | 0.057          | Good          |
| Bapuji Nagar, Bengaluru - KSPCB        | 0.063          | Good          |
| Hebbal, Bengaluru - KSPCB              | 3.122          | Hazardous     |
| Silk Board, Bengaluru - KSPCB          | 4.516          | Hazardous     |
| BTM Layout, Bengaluru - CPCB           | 8.670          | Hazardous     |
| Peenya, Bengaluru - CPCB               | 11.119         | Hazardous     |

**Imputation**

| Name                                     | Weighted Score | Quality Label |
| ---------------------------------------- | -------------- | ------------- |
| Hombegowda Nagar, Bengaluru - KSPCB      | 0.045          | Good          |
| Shivapura\_Peenya, Bengaluru - KSPCB     | 0.049          | Good          |
| Jayanagar 5th Block, Bengaluru - KSPCB   | 0.057          | Good          |
| Bapuji Nagar, Bengaluru - KSPCB          | 0.063          | Good          |
| Hebbal, Bengaluru - KSPCB                | 3.122          | Hazardous     |
| BTM Layout, Bengaluru - KSPCB            | 3.770          | Hazardous     |
| BWSSB Kadabesanahalli, Bengaluru - KSPCB | 4.096          | Hazardous     |
| Peenya, Bengaluru - KSPCB                | 4.341          | Hazardous     |
| Silk Board, Bengaluru - KSPCB            | 4.516          | Hazardous     |
| BTM Layout, Bengaluru - CPCB             | 8.670          | Hazardous     |
| Peenya, Bengaluru - CPCB                 | 11.119         | Hazardous     |
| BWSSB Kadabesanahalli, Bengaluru - CPCB  | 12.932         | Hazardous     |
| Kasturi Nagar, Bengaluru - KSPCB         | 13.980         | Hazardous     |


In the subset analysis, areas like Hombegowda Nagar, Jayanagar 5th Block, and Bapuji Nagar were identified as having "Good" air quality, while Hebbal, Silk Board, and BTM Layout (CPCB) exhibited "Hazardous" conditions. The imputation analysis, which addressed gaps in the dataset, expanded the scope of the evaluation, identifying additional "Good" areas like Shivapura_Peenya and additional "Hazardous" areas like BWSSB Kadabesanahalli (both CPCB and KSPCB) and Kasturi Nagar. Notably, even after imputing missing data, the areas previously classified as "Hazardous" in the subset analysis—such as Hebbal, Silk Board, and BTM Layout (CPCB)—remained in the "Hazardous" category. This consistency underscores the persistent air quality challenges in these zones and highlights the critical need for focused interventions.


