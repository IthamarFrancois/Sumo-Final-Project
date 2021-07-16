Sumo Website:

http://sumo-data-bucket.s3-website-us-east-1.amazonaws.com/Index.html

or

https://sumo-wrestling.herokuapp.com/Index.html

==================================================================================

**Objective:** trying different machine learning methods to develop a sumo wrestling match predictor.
**Dataset source:** https://data.world/cervus/sumo-japan, curated by Mikhail Zhilkin

### REQUIRED LIBRARY ### 
https://pypi.org/project/dataframe-image/ (pip install dataframe-image)
necessary for successful execution of ml_notebook.ipynb

1. banzuke.csv: Final results for each wrestler in all divisions for every tournament going back to 1983 (12 columns, 169,105 rows). Includes wrestler's final scores, height(cm), weight(kg), birth date and rank.
2. results.csv: Match results for each day in tournaments since 1983 for the top two divisions: Makuuchi and Juryo (13 columns, 219,990 rows).
**Understanding & Preparing Data:** 
1. Headers with Japanese terms were translated to English (stable for heya, wrestler for rikishi, tournament for basho, etc.).
2. All divisions below Makuuchi were dropped.
3. All non-active wrestlers were dropped.
4. Ranks were given a numerical value (from greatest to lowest: Yokozuna, Ozeki, Sekiwake,Komusubi, M1-18).
5. Wrestler's age at the time of the tournament was calculated.
6. For all matches, the differences in height, weight, age, and rank were calculated.
**Machine Learning**
1. Google Colab Notebook: https://colab.research.google.com/drive/1mwyxMXyvbrq9RxqpzQLxNomUelTJqf5r#scrollTo=nR-i6E8OEchD
2. Features used for machine learning: differences in height, weight, age and rank.
3. ML methods used: Logistic Regression, Decision Tree Classifier, Random Forest
4. Logistic Regression gave the highest Training/Testing Scores (59/55% respectively)
5. GridSearchCV was attempted but it took TOO DARN LONG!!!
6. The LR model was trained using data from May 2004 to March 2021 and tested with May 2021 tournament results.
7. The model came close to some actual results! It predicted Takakeisho as the winner (he was runner-up) while the actual winner, Terunofuji was predicted as the runner-up. Not bad! 
8. Ichinojo was the only perfectly predicted outcome with 9 wins, while the model predictions for Terunofuji, Wakatakakage and Shimanoumi were off by just 1 win.
9. Things to improve the model: add more features like match win percentages or wrestler injuries.
10. Sumo has a very subjective nature to it, how wrestlers move up and down ranks can vary wildly from one tournament to another, and rules are not exactly written in stone.
