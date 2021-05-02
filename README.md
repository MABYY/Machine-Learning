# Machine-Learning
Explore trading oportunities in Argie bonds using machine learning algorithms.

<img width="809" alt="Screen Shot 2021-05-02 at 2 56 50 PM" src="https://user-images.githubusercontent.com/34326154/116824945-26713f00-ab63-11eb-9489-fbfd05c77e19.png">


## Development setup

Machine learning library adopted for the implementation

> pip install -U scikit-learn

Import Python package to re-sampling imbalanced  datasets

> pip install imblearn

Libraries used to create visualizations

> pip install matplotlib

> pip install seaborn

## The Model

In order to explore trading opportunities, decided to transform a time series problem into a classification problem. To do so, we first had to create the features. We thus calculated several technical analysis indicatos such as the MACD, RSI and the Bollinger Bands and many trading signals based on the critical. Moreover, we defined the labels by attaching a "Buy" (1) label to those entry points that offered a possitive return five days ahead, and a "Sell" (0) to the rest of the occasions. Take a look at our problem.

<img width="476" alt="Screen Shot 2021-05-02 at 2 57 00 PM" src="https://user-images.githubusercontent.com/34326154/116824927-19545000-ab63-11eb-8eb2-bff59d04c174.png">

Another problem we had to face is the fact that our dataset is imbalanced. Should we run the classification models without solving this problem before hand, we would have trained the parameters incorrectly. The model would be more prone to spotting one label than the other, thus running the risk of making wrong trading decisions. 

Having solved that problem, we decided to run both a Random Forest Model (RF) and a Adaboost classifier model (AB). RF use a modified tree learning algorithm that selects, in each candidate division, a random subset of variables. This process is sometimes called feature bagging. AB takes a weak base model and tries to make it strong by retraining it on the misclassified samples.


## Results

As we can see from the results, the Random Forest Model shows a higher AUC than the AB model, higher specificity and precision scores. 

<img width="348" alt="Screen Shot 2021-05-02 at 5 00 05 PM" src="https://user-images.githubusercontent.com/34326154/116825983-232c8200-ab68-11eb-89c7-3e9fa47955f7.png">

<img width="326" alt="Screen Shot 2021-05-02 at 4 59 56 PM" src="https://user-images.githubusercontent.com/34326154/116825993-39d2d900-ab68-11eb-8396-65a1cdf44859.png">

However, RF shows lower recall. This means that the model identify buying opportunities on many ocations. Further feature engineer is recommended in this case.

Notice that the model should have been run using zero coupon rate bonds. They are not easy to calculate for Argentinean bonds. Bearing this in mind, we attempted to turn a time series problem into a classification problem we wanted and check how data fits RF and AB models chosen.


## Articles

- "How My Machine Learning Trading Algorithm Outperformed the SP500 For 10 Years", Tomiwa, https://shorturl.at/gqzT9


## Contributing

- Fork this project
- Create your feature branch
- Commit your changes
- Push to the branch
- Create a new Pull Request

