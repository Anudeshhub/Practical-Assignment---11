<style type="text/css">.rendered-markdown{font-size:14px} .rendered-markdown>*:first-child{margin-top:0!important} .rendered-markdown>*:last-child{margin-bottom:0!important} .rendered-markdown a{text-decoration:underline;color:#b75246} .rendered-markdown a:hover{color:#f36050} .rendered-markdown h1, .rendered-markdown h2, .rendered-markdown h3, .rendered-markdown h4, .rendered-markdown h5, .rendered-markdown h6{margin:24px 0 10px;padding:0;font-weight:bold;-webkit-font-smoothing:antialiased;cursor:text;position:relative} .rendered-markdown h1 tt, .rendered-markdown h1 code, .rendered-markdown h2 tt, .rendered-markdown h2 code, .rendered-markdown h3 tt, .rendered-markdown h3 code, .rendered-markdown h4 tt, .rendered-markdown h4 code, .rendered-markdown h5 tt, .rendered-markdown h5 code, .rendered-markdown h6 tt, .rendered-markdown h6 code{font-size:inherit} .rendered-markdown h1{font-size:28px;color:#000} .rendered-markdown h2{font-size:22px;border-bottom:1px solid #ccc;color:#000} .rendered-markdown h3{font-size:18px} .rendered-markdown h4{font-size:16px} .rendered-markdown h5{font-size:14px} .rendered-markdown h6{color:#777;font-size:14px} .rendered-markdown p, .rendered-markdown blockquote, .rendered-markdown ul, .rendered-markdown ol, .rendered-markdown dl, .rendered-markdown table, .rendered-markdown pre{margin:15px 0} .rendered-markdown hr{border:0 none;color:#ccc;height:4px;padding:0} .rendered-markdown>h2:first-child, .rendered-markdown>h1:first-child, .rendered-markdown>h1:first-child+h2, .rendered-markdown>h3:first-child, .rendered-markdown>h4:first-child, .rendered-markdown>h5:first-child, .rendered-markdown>h6:first-child{margin-top:0;padding-top:0} .rendered-markdown a:first-child h1, .rendered-markdown a:first-child h2, .rendered-markdown a:first-child h3, .rendered-markdown a:first-child h4, .rendered-markdown a:first-child h5, .rendered-markdown a:first-child h6{margin-top:0;padding-top:0} .rendered-markdown h1+p, .rendered-markdown h2+p, .rendered-markdown h3+p, .rendered-markdown h4+p, .rendered-markdown h5+p, .rendered-markdown h6+p{margin-top:0} .rendered-markdown ul, .rendered-markdown ol{padding-left:30px} .rendered-markdown ul li>:first-child, .rendered-markdown ul li ul:first-of-type, .rendered-markdown ol li>:first-child, .rendered-markdown ol li ul:first-of-type{margin-top:0} .rendered-markdown ul ul, .rendered-markdown ul ol, .rendered-markdown ol ol, .rendered-markdown ol ul{margin-bottom:0} .rendered-markdown dl{padding:0} .rendered-markdown dl dt{font-size:14px;font-weight:bold;font-style:italic;padding:0;margin:15px 0 5px} .rendered-markdown dl dt:first-child{padding:0} .rendered-markdown dl dt>:first-child{margin-top:0} .rendered-markdown dl dt>:last-child{margin-bottom:0} .rendered-markdown dl dd{margin:0 0 15px;padding:0 15px} .rendered-markdown dl dd>:first-child{margin-top:0} .rendered-markdown dl dd>:last-child{margin-bottom:0} .rendered-markdown blockquote{border-left:4px solid #DDD;padding:0 15px;color:#777} .rendered-markdown blockquote>:first-child{margin-top:0} .rendered-markdown blockquote>:last-child{margin-bottom:0} .rendered-markdown table th{font-weight:bold} .rendered-markdown table th, .rendered-markdown table td{border:1px solid #ccc;padding:6px 13px} .rendered-markdown table tr{border-top:1px solid #ccc;background-color:#fff} .rendered-markdown table tr:nth-child(2n){background-color:#f8f8f8} .rendered-markdown img{max-width:100%;-moz-box-sizing:border-box;box-sizing:border-box} .rendered-markdown code, .rendered-markdown tt{margin:0 2px;padding:0 5px;border:1px solid #eaeaea;background-color:#f8f8f8;border-radius:3px} .rendered-markdown code{white-space:nowrap} .rendered-markdown pre>code{margin:0;padding:0;white-space:pre;border:0;background:transparent} .rendered-markdown .highlight pre, .rendered-markdown pre{background-color:#f8f8f8;border:1px solid #ccc;font-size:13px;line-height:19px;overflow:auto;padding:6px 10px;border-radius:3px} .rendered-markdown pre code, .rendered-markdown pre tt{margin:0;padding:0;background-color:transparent;border:0}</style>
<div class="rendered-markdown"><h1>UC Berekeley ML/AI Practical Assignment 2</h1>
<h2>What drives the price of a car?</h2>
<p><img src="images/kurt.jpeg" alt="" /></p>
<h3>Executive Summary: Insights into Used Car Valuation</h3>
<p><strong>OVERVIEW</strong>
<br  />In this application, we are given vehicles.csv file. The original dataset contained information on 3 million used cars.
<br  />The provided dataset contains information on 194K cars to ensure speed of processing. Our goal is to understand what factors make a car more or less expensive.
<br  />As a result of our analysis, recommendation is provided to the client (a used car dealership), as to what consumers value in a used car.</p>
<p><strong>CRISP-DM Framework</strong>
<br  />I am using CRISP-DM Framework to work through the model and develop a model</p>
<p><strong>Business Understanding</strong>
<br  />The used car market is competitive, and understanding pricing dynamics is crucial for businesses to remain profitable.
<br  />Consumer preferences can vary widely based on demographics, regional differences, and current market trends.</p>
<p>The objective is to identify the key factors that contribute to the pricing of used cars and understand consumer
<br  />preferences in this market. This analysis will help stakeholders make informed decisions about pricing strategies and
<br  />inventory management.</p>
<p><strong>Key stakeholders include:</strong> Sales Teams, Marketing teams, Data Analysts</p>
<p><strong>Constraints </strong>: Data quality (there is some missing data, data points that might affect the analysis outcomes) and</p>
<pre><code>              market variability (inflation, fuel prices etc) that can impact car valuations 
              Other factors can include  compliance and adherence to data privacy regulations when handling consumer data.
</code></pre>
<p><strong>Key factors that influence car prices in this dataset are:</strong>
<br  /><strong>Manufacturer and Model</strong>: To assess brand and model impact on pricing.
<br  /><strong>Condition</strong>             : To evaluate how the state of the car influences its market value.
<br  /><strong>Odometer Reading</strong>      : To measure mileage's effect on pricing. (not used due to high cardinality in data)
<br  /><strong>Model</strong>                 : To determine the model in demand
<br  /><strong>Transmission Type</strong>     : To determine consumer preferences for automatic vs. manual.
<br  /><strong>Paint Color</strong>           : To analyze color trends and their influence on resale value.
<br  /><strong>Year</strong>                  : Year of the car
<br  /><strong>Price</strong>                 : Value of the car</p>
<p><strong>Data Understanding <em></em>
<br  /></strong> Read vehicles.csv data downloaded from kaggle. Used vehicles_short.csv for this exercise</p>
<p><strong>Dependent Variable</strong> is the Price of the car
<br  /><strong>Independent Variables</strong> are Key Drivers i.e columns used to train and test the model</p>
<p>*<em>Data Understanding </em>*
<br  />Interpreted Numerical and Categorical features and datasets, by creating additional columns like Average Prices by Year Bins and
<br  />Categorical counts by year.
<br  />Basic visualizations in each of these categories explained :</p>
<pre><code>Year           Average Price
</code></pre>
<p>0  2010-2015   17144.156193
<br  />1  2016-2020   25360.994111
<br  />2  2021-2023  228298.091630</p>
<p>images/average_price_by_year.png
<br  /><img src="images/average_price_by_year.png" alt="images/average_price_by_year" /></p>
<p>Average priced categories:
<br  />manufacturer: porsche in None with average price $54080.81 (Type: None)
<br  />condition: new in None with average price $32584.99 (Type: None)
<br  />cylinders: 12 cylinders in 2015 with average price $50000.00 (Type: SUV)
<br  />type: pickup in None with average price $33227.20 (Type: None)</p>

<p>images/Car_Prices_by_Color_of_the_car.png
<br  /><img src="images/Car_Prices_by_Color_of_the_car.png" alt="images/Car_Prices_by_Color_of_the_car" /></p>

<p>Price Trends Over Time:
<p>images/Car Prices by Conditiono f the car.png
<br  /><img src="images/Car_Prices_by_Condition_of_the_car.png" alt="images/Car_Prices_by_Condition_of_the_car" /></p>

<br  />2010-2015 to 2016-2020: The increase in average price from $17,144.16 to $25,360.99 indicates a rising trend in the value of the items during this period, suggesting either improvements in quality, increased demand, or other market factors driving prices higher.</p>
<p>2016-2020 to 2021-2023: The dramatic leap to $228,298.09 in the most recent period is noteworthy. This could imply significant changes in the market, such as:</p>
<p>Introduction of new, high-end models.
<br  />A shift in consumer preferences towards more expensive vehicles.
<br  />Economic factors affecting pricing, such as inflation or supply chain issues.
<br  />Possible shortage of available models, leading to higher prices.</p>
<p>Condition: new in None with average price $32584.99 (Type: None)
<br  />cylinders: 12 cylinders in 2015 with average price $50000.00 (Type: SUV)
<br  />type: pickup in None with average price $33227.20 (Type: None)</p>
<p>images/categorical_counts_by_year.png
<br  /><img src="images/categorical_counts_by_year.png" alt="images/categorical_counts_by_year" /></p>
<p><strong>Overall Insights</strong>
<br  />High Average Prices: The prices reflect a market that values both new vehicles and specific configurations (like high-cylinder counts) significantly.
<br  />Condition Impact: The distinction in pricing between new vehicles and specific cylinder configurations indicates that condition and performance specifications heavily influence market value.
<br  />Market Segment: The SUV with 12 cylinders represents a luxury or performance segment, suggesting that there is a demand for high-powered vehicles among consumers.
<br  />These insights can help inform market strategies, consumer preferences, and pricing analyses in the automotive sector.</p>
<p><strong>Data Preparation </strong>[Pre-processing]
<br  /><strong>Data Cleaning</strong></p>
<pre><code>    More data cleanup and tuning done, in order to prepare for modeling
    Identify and Remove Duplicates: The code checks for and removes any duplicate rows in the dataset
    Clean 'cylinders' Column: Remove Non-Numeric Characters, The cleaned values are then converted to numeric format, coercing any errors (e.g., non-convertible strings) into NaN,
    Convert to Absolute Values, Replace NaN Values with Zero, Finally, the cylinders column is converted to an integer type for consistency and easier analysis
    Drop Unnecessary Columns:

    Specific columns that are deemed unnecessary for the analysis (region, title_status, and drive) are removed from the dataset

    Find out any outliers in the cleanup data.
    Price Outlier.png
    ![Price Outlier](Price Outlier.png)

**Data Transformation**
   Encode Categorical Variables using one-hot encoding on categorical columns and then apply scaling to encoded dataset
</code></pre>
<p><strong>Conduct Exploratory Data Analysis</strong></p>
<pre><code>   Visulatizations:

 <br  /><img src="images/Top_5_manufacturer.png" alt="images/Top_5_manufacturers" /></p>
<br  /><img src="images/Mean Price for top 5 manufacturer.png" alt="images/Mean Price for top 5 manufacturers" /></p>


   Statistical analysis :  Calculate mean, median, mode, standard deviation, etc

        price           year            cylinders   
count   34787           34787           34787   
mean    15832.819961    2011.182568     6.013022    
std     13447.891321    7.140035        1.716204    
min     0.000000        1905.000000     0.000000    
25%     6500.000000     2008.000000     4.000000    
50%     12000.000000    2013.000000     6.000000    
75%     22007.000000    2016.000000     8.000000    
max     155000.000000   2022.000000     12.000000   

**Key Metrics**

Total Cars: The dealership has approximately 34,787 cars in its inventory.
Price:
Mean Price: Around $7.31 billion (likely this represents the total value rather than individual car prices).
Price Range: Prices start from around $7.30 billion (likely a misinterpretation) and go up to about $7.32 billion.
Year:
Mean Model Year: The average car is from the year 2011, indicating a mix of older and newer models.
Year Range: The oldest car dates back to 1905, while the newest is from 2022.
Cylinders:
Average Cylinders: Cars typically have about 6 cylinders, which is common for many sedans and SUVs.
Cylinder Range: Cars range from 0 to 12 cylinders, suggesting the inventory includes everything from smaller vehicles to high-performance models.

**Observations**
Diverse Inventory: The wide range of years, prices, and odometer readings suggests the dealership offers a diverse selection of vehicles, catering to various buyer preferences and budgets.
Average Age: With an average model year of 2011, most cars are relatively modern but may require some maintenance due to age.
High Mileage: The presence of high-mileage vehicles could indicate trade-ins or older fleet vehicles, which may attract budget-conscious buyers.
Performance Options: The cylinder count indicates the availability of both standard and performance vehicles, appealing to different segments of the market.
</code></pre>
<p>*<em>Modeling </em>*
<br  />Modeling results</p>
<pre><code>    Model                    MAE          MSE     RMSE    R²
</code></pre>
<p>0   Linear Regression  6967.27  93166710.75  9652.29  0.35
<br  />1   Ridge Regression   6967.29  93166924.73  9652.30  0.35
<br  />2   Lasso Regression   6967.21  93167762.70  9652.34  0.35</p>
<p>Best Model: Among the models tested, Lasso Regression performs the best with the lowest MAE, MSE, and RMSE, and an R² score of 0.15, indicating it explains some variability in the data.</p>
<p>Accuracy: The MAE and RMSE values indicate that the model has a noticeable average prediction error,</p>
<pre><code>          which may affect pricing strategies.

Model Fit: The R² value suggests that while the model explains some variability, which is same for all models
           there is a considerable amount of unexplained variance. This could mean that additional features or a different modeling approach might improve predictions.
</code></pre>
<p><strong>Evaluation</strong>
<br  />Applied Cross-Validation logic to evaluate the model and the final numbers showed same as predicted.</p>
<p><strong>Deployment</strong>
<br  />Applied Lasso Regression model to predict the price of car based on   condition [Only one feature used]</p>
<pre><code>        Condition = 1 - Excellent,   2  = Good  3 - None'
        Predicted price: $25,893.10    (Condition - None)
</code></pre>
<p><em></em> Recommendations for the Dealership <em></em></p>
<p>Based on our Analysis and Predictive model created and recommendations made based on 2 features and the price as dependable variable
<br  />Brand Value (Manufacturer) : There is a demand for Brand value, as the sale for luxury cars was more, hence the dealer must keep more of these cars
<br  />Condition of the Car : Good condition cars though expensive, are preferred by customers and hence, they must increase the inventory of these cars
<br  />Prices of good cars will go up, as predicted, hence the dealer must have more good cars in their inventory</p>
<p><strong>Feedback</strong>
<br  />Monitor Performance: Continuously track model performance over time. Regularly update the model with new data to ensure it remains relevant.
<br  />Customer Feedback: Gather feedback from customers regarding pricing and features. Use this information to refine models and strategies.
<br  />By implementing these recommendations, the dealership can improve its pricing accuracy, better meet customer needs, and ultimately enhance profitability.</p>
</div>
