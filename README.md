<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Demand Forecasting in E-commerce</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      line-height: 1.6;
    }
    table {
      width: 100%;
      border-collapse: collapse;
      border: 1px solid #ddd;
      font-size: 14px;
    }
    th, td {
      padding: 10px;
      text-align: left;
    }
    th {
      font-size: 16px;
    }
    tbody tr:nth-child(odd) {
      background-color: #f9f9f9;
    }
    .tree ul {
      padding-top: 20px; 
      position: relative;
      transition: all 0.5s;
    }
    .tree li {
      float: left; 
      text-align: center;
      list-style-type: none;
      position: relative;
      padding: 20px 5px 0 5px;
      transition: all 0.5s;
    }
    .tree li::before, .tree li::after {
      content: '';
      position: absolute; 
      top: 0; 
      right: 50%;
      border-top: 1px solid #ccc;
      width: 50%; 
      height: 20px;
    }
    .tree li::after {
      right: auto; 
      left: 50%;
      border-left: 1px solid #ccc;
    }
    .tree li:only-child::after, .tree li:only-child::before {
      display: none;
    }
    .tree li:only-child {
      padding-top: 0;
    }
    .tree li:first-child::before, .tree li:last-child::after {
      border: 0 none;
    }
    .tree li:last-child::before {
      border-right: 1px solid #ccc;
      border-radius: 0 5px 0 0;
    }
    .tree li:first-child::after {
      border-radius: 5px 0 0 0;
    }
    .tree ul ul::before {
      content: '';
      position: absolute; 
      top: 0; 
      left: 50%;
      border-left: 1px solid #ccc;
      width: 0; 
      height: 20px;
    }
    .tree li a {
      border: 1px solid #ccc;
      padding: 5px 10px;
      text-decoration: none;
      color: #666;
      font-family: arial, verdana, tahoma;
      font-size: 11px;
      display: inline-block;
      border-radius: 5px;
      transition: all 0.5s;
    }
    .tree li a:hover, .tree li a:hover+ul li a {
      background: #c8e4f8; 
      color: #000; 
      border: 1px solid #94a0b4;
    }
    .tree li a:hover+ul li::after, 
    .tree li a:hover+ul li::before, 
    .tree li a:hover+ul::before, 
    .tree li a:hover+ul ul::before {
      border-color:  #94a0b4;
    }
  </style>
</head>
<body>

<h1>Demand Forecasting for E-commerce</h1>

<h2>Overview</h2>

<p>This repository contains the code and resources for demand forecasting in e-commerce. The project focuses on using various time series models to predict demand and optimize marketing strategies.</p>

<h2>Table of Contents</h2>
<ul>
  <li><a href="#project-structure">Project Structure</a></li>
    <li><a href="#models-implemented">Models Implemented</a></li>
  <li><a href="#installation">Installation</a></li>
  <li><a href="#usage">Usage</a></li>
  <li><a href="#results">Results</a></li>
  <li><a href="#license">License</a></li>
</ul>

<h2 id="project-structure">Project Structure</h2>

- **dataset/**: Directory containing raw data files.
  - `ProductA.xlsx`: Original data file 1.
  - `ProductA_google_clicks.xlsx`: Original data file 2.
  - `ProductA_fb_impressions.xlsx`: Original data file 3.
- **notebooks/**: Directory containing Jupyter notebooks for different stages of the project.
  - `preprocessing.ipynb`: Notebook for data merging, preprocessing, and feature engineering.
  - `EDA.ipynb`: Notebook for Exploratory Data Analysis (EDA) to visualize trends and hypotheses.
  - `Modeling.ipynb`: Notebook for modeling and obtaining forecasting results.
- `notebook.ipynb`: Combined notebook for the whole project.

- `final_df.xlsx`: Merged and preprocessed data used for analysis and modelling.
- `project.pdf`: PDF document summarizing the project including methodology and results.
- `README.md`: Readme file providing an overview of the project, instructions, and usage.
- `requirements.txt`: File listing dependencies required to reproduce the project environment.

<h2 id="models-implemented">Models Implemented</h2>

<ul>
  <li><strong>AR (AutoRegressive)</strong></li>
  <li><strong>MA (Moving Average)</strong></li>
  <li><strong>ARMA (AutoRegressive Moving Average)</strong></li>
  <li><strong>ARIMA (AutoRegressive Integrated Moving Average)</strong></li>
  <li><strong>ARIMAX (ARIMA with Exogenous Variables)</strong></li>
  <li><strong>SARIMA (Seasonal ARIMA)</strong></li>
  <li><strong>SARIMAX (SARIMA with Exogenous Variables)</strong></li>
</ul>

<h2 id="installation">Installation</h2>

<ol>
  <li>Clone the repository:
    <pre><code>git clone https://github.com/thejatingupta7/demand-forecasting-for-E-commerce.git
cd demand-forecasting-for-E-commerce.git</code></pre>
  </li>
  <li>Create a virtual environment and activate it:
    <pre><code>python -m venv venv
source venv/bin/activate  
venv\Scripts\activate</code></pre>
  </li>
  <li>Install the required packages:
    <pre><code>pip install -r requirements.txt</code></pre>
  </li>
</ol>

<h2 id="usage">Usage</h2>

<ol>
  <li><strong>Data Preprocessing:</strong><br>Run the data preprocessing script to clean and prepare the data.
    <pre><code>data_preprocessing.ipynb</code></pre>
  </li>
  <li><strong>EDA.ipynb:</strong><br>Visulize the data to understand it and find trends.
    <pre><code>EDA.ipynb</code></pre>
  </li>
  <li><strong>Model Training:</strong><br>Train the various time series models.
    <pre><code>modelling.ipynb</code></pre>
  </li>
</ol>


<h2 id="results">Results</h2>

The performance of these models was evaluated using Mean Absolute Percentage Error (MAPE) and other error metrics on both validation and test datasets.

<i><b>`The results indicated that the **SARIMAX model** achieved the best performance with the least MAPE score and the lowest error, followed by the **SARIMA model** and the **ARIMAX model**.`</i></b>

Here's a summary of the results:

- `SARIMAX`: Achieved the lowest MAPE and error rates on both validation and test datasets.
- `SARIMA` : Performed well, but slightly less accurate than SARIMAX.
- `ARIMAX` : Showed reasonable performance, leveraging exogenous variables for forecasting.

<i>This demonstrates the effectiveness of including seasonality and exogenous variables in improving the accuracy of demand forecasting in e-commerce.</i>

<h2 id="license">License</h2>

<p>This project is licensed under the MIT License - see the <a href="LICENSE">LICENSE</a> file for details.</p>

</body>
</html>
