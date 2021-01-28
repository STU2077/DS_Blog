<strong>1. Installation</strong>
<p>There should be no necessary libraries to run the code here beyond the Anaconda distribution of Python. The code should run with no issues using Python versions 3.*.</p>
<strong>2. Project Motivation</strong>
<p>Due to Covid-19 outbreak, tourism, hospitality, and real estate industries were struggled.
In order to stimulate the economy, AU government offers great benefits to property investors, which motivates me to play around with Melbourne’s Airbnb data. Maybe I can find some investment ideas.</p>

<strong>3. File Descriptions</strong>
<p>A notebook is available here to showcase work related to the above questions. Each cell has a sentence at the top for describing the purpose of the code.
Two data sets (Listings and Calendar) are used. </p>

<strong>4. Results</strong>
<p>The main findings of the code can be found at the post available here <a href="https://shelbytu22.medium.com/this-melbourne-airbnb-dataset-tells-4-things-effaeee2f4bf">here</a>.</p>

<strong>5. Licensing, Authors, Acknowledgements</strong>
<p>Thanks for Airbnb making their data available to public. You can find the Licensing for the data and other descriptive information on <a href="http://insideairbnb.com/get-the-data.html" target="_blank">http://insideairbnb.com/get-the-data.html</a>.</p>

<strong>_CRISP-DM_</strong>

<strong>1. Business Understanding</strong>
<p> 
My goal is to gain some investment ideas from Airbnb Melbourne data sets. There are four questions I am expecting to find answers :</p>
<p>Q1: How is the rental market performing in Melbourne on Airbnb?
<br/>(The answer of this question will give me a picture about the current rental market.) </p>
<p>Q2: What neighborhoods have a greater chance to rend out properties?
<br/>(A higher rental rate a neighborhood has, a better location the neighborhood is.)</p>
<p>Q3: What type of property should I invest in?
<br/>(After knowing where to buy, the next question is what to buy.)</p>
<p>Q4: How do price and review scores affect rental properties?
<br/>(By answering this question, I would know if I bought a rental property, how likely price and reviews affect my rentals.)</p>

<strong>2. Data Understanding</strong>
<p>Two data sets are available. The Listings data set shows property details. Each property has a unique listing id. Another data set is Calendar, which shows whether a property is available or not per date plus some other information such as price, maximum and minimum leasing days. By joining these two data sets, it is possible to see what properties are unavailable (let) and their details. The data were scraped on 05/11/20, and only one year data (05/11/20 to 04/11/21) are included. Many columns have null values, and some have null values only. Moreover, the name of neighborhoods is not always consistent, for example, a property is located in Melbourne but shown Melbourne in other languages than English.</p>

<strong>3. Prepare Data</strong>
<p>  (1) Remove columns with null values only in Listings.
<br/>(2) Transform the Price column in Calendar to numeric.
<br/>(3) Create a new column to show year-month in Calendar.
<br/>(4) Merge Listings and Calendar.
<br/>(5) Sub-set the merged data set to keep predictors and a outcome variable.
<br/>(6) Replace rows with null values to column median to avoid errors when fitting a regression model. 
<br/>(7) Replace the outcome variable, "available", to dummies.
</p>
<strong>4. Data Modeling</strong>
<p>Logistic regression model is used here for three reasons. (1)Through coefficients of the model to understand the correlation between the outcome variable and predictors. (2) "Available" has only "t" and "f" values. (3) A regression model can tell what factors are  most important.</p>
<p>*As we only have one year data, and these data show current bookings or bookings in the future instead of historical data, so it is not beneficial to form a prediction model using these data. </p>

<strong>5. Evaluate the Results</strong>
<p>The best model is decided based on a model's AUC value. 
The top 3 most important factors are 'price', 'value', and 'cleanliness', and the model's AUC value is 0.5747. A plot of AUC test and train sets show the model is underfitting.</p>

<strong>6. Deployment</strong>
<p>As long as the Airbnb data set structure remains the same, users can always replace the data source to a recent one and run the model without any modifications.</p>