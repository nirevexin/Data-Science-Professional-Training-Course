## Project: Determining patterns of videogames sales success
* **Description**: 
An online videogames store, which sells computer games all over the world, needs to identify patterns that determine a videogame success. This will allow them to place a bet on a potentially popular product and plan advertising campaigns.
* **Goal**: 
Identifying the patterns that determine a videogame sales success. 
* **Stack**: 
`Pandas`, `NumPy`, `SciPy`, `Matplotlib`, `Seaborn`, `Statistical Hypothesis Testing`, `Descriptive Statistics`, `Exploratory Data Analysis`
* **Activity Area**:
`Online Stores`, `Business`
* **Technical Area**:
`Data Analysis`, `Marketing Analysis`, `Product Analysis`
* **Data**:
     - Name - the name of the game
     - Platform - platform
     - Year_of_Release — year of release
     - Genre - game genre
     - NA_sales - sales in North America (millions of copies sold)
     - EU_sales - sales in Europe (millions of copies sold)
     - JP_sales - sales in Japan (millions of copies sold)
     - Other_sales - sales in other countries (millions of copies sold)
     - Critic_Score - critics' score (maximum 100)
     - User_Score - user rating (maximum 10)
     - Rating - rating from the ESRB (Entertainment Software Rating Board). This association determines the rating of computer games and assigns them an appropriate age category.
### Results:

- On average, gaming platforms are supported by developers for 4-5 years.
- The most **potentially profitable platforms** are `PS4` and `XOne`. For some time, games for the `3DS`, `WiiU`, and `PSV` platforms will still be relevant. As for the `PC`, it has always been there, it doesn’t sell as much as others, but it always remains.
- If we divide the **popularity of platforms by market**, then:
     - In **Japan**, they are true to their own: `Sony` and `Nintendo` platforms are the most popular.
     - In **Europe** and **North America**, everything is very similar, in contrast to the market share between `PS4` and `XOne`:
          - In **America**, they are almost equal, but in **Europe**, `PS4` dominates.
- From **genres**, it is recommended to choose games in the genre of `Action`, `Shooters` and `Sports` for **Europe** and **North America** and `Role-Playing` and `Action`for the **Japanese market**.
- **Age rating**:
     - In **Europe** and **North America**, the most sold ratings are `M`, `E` and `Unrated`.
     - In **Japan**: `Unrated` tops, with great superiority over others.
- **Critic ratings** have the same impact on game sales on all platforms: games that receive good reviews from critics tend to sell better.
- **User ratings** have no impact on sales on `PS3`, `PS4`, `X360` and `XOne`, but start to have some impact on `3DS` and `WiiU`, both from `Nintendo`.
- We also tested two hypotheses stated at the very beginning of the study. As a result:

     - **average user ratings** for `Xbox One` and `PC` have big probability to be **identical**.

     - **average user ratings** for the `Action` and `Sports` genres have big probability to be **different**.
