## ClimateBench 2.0 Web App
Frontend application for exploring results from ClimateBench 2.0

Live app: [https://climate-analytics-lab.github.io/ClimateBench_app/index.html](https://climate-analytics-lab.github.io/ClimateBench_app/index.html)

## How to contribute
The framework can be expanded to include more models, variables, metrics, and regions. To add more data, create a pull request with the following changes:
1. Rows with relevant data added to `data/benchmark_results.csv`
    - This will add your score to the table in the scores tab
    - If you are adding a new variable, region, or metric, you will need to modify the dropdown selections in the scores.html.
        - [variable](https://github.com/climate-analytics-lab/ClimateBench_app/blob/main/scores.html#L42-L51)
        - [region](https://github.com/climate-analytics-lab/ClimateBench_app/blob/main/scores.html#L53-L61)
        - [metric](https://github.com/climate-analytics-lab/ClimateBench_app/blob/main/scores.html#L63-L76)
2. Rows with the relevant data added to `data/benchmark_results_timeseries.csv` and `data/benchmark_results_timeseries_annual.csv`
    - This will add your data to the plot below the table on the scores tab
    - If you are adding a new variable, region, or metric, you may need to modify the following sections in scores.html.
        - [variable](https://github.com/climate-analytics-lab/ClimateBench_app/blob/main/scores.html#L296)
        - [region](https://github.com/climate-analytics-lab/ClimateBench_app/blob/main/scores.html#L297)
        - [metric](https://github.com/climate-analytics-lab/ClimateBench_app/blob/main/scores.html#L260-L264)
3. Paleo changes can be made by
    - Adding data to `data/paleo_data/annual_zonal_means.csv`. You will need to recalculate the median and normalized mae columns. This will add your data to the two overview figures.
    - Adding data to `data/paleo_data/monthly_zonal_means.csv`. This will add your data to the seasonal plots. 
    - Adding data to the map options. You will need to create the map image first, and then add to the relevant paleo period folder `data/paleo_data/{paleo period}/{model}.png`. Then you will need to modify the dropdown options to include the added model.
        - [Eocene](https://github.com/climate-analytics-lab/ClimateBench_app/blob/main/paleo.html#L51-L64)
        - [Pliocene](https://github.com/climate-analytics-lab/ClimateBench_app/blob/main/paleo.html#L118-L128)
        - [Last Interglacial](https://github.com/climate-analytics-lab/ClimateBench_app/blob/main/paleo.html#L167-L184)
        - [Last Glacial Maximum](https://github.com/climate-analytics-lab/ClimateBench_app/blob/main/paleo.html#L224-L231)
        - [Mid Holocene](https://github.com/climate-analytics-lab/ClimateBench_app/blob/main/paleo.html#L271-L290)

## Local development
You will need to install npm ([instructions](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm)). Then, from the top level of the repo run
```
npx http-server
```
Which will run the app locally at http://127.0.0.1:8080
