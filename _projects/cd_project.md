---
layout: page
title: CrunchDAO quant finance competitions
description: Creating prediction engines for a long-short hedge fund
img: assets/img/cd-project_logo.png
importance: 1
category: work
---

After [competing in WorldQuant International Quant
Championship](../wq_project/), I got a LinkedIn message from Jean Herelle at
[CrunchDAO](https://www.crunchdao.com). He asked me if I had heard about
CrunchDAO's [📈 ADIALab Market Prediction
Competition](https://adialab.crunchdao.com/), a quant finance tournament in
which participants predict stock price movements using hundreds of variables
over time. 

Eager to learn more about time series modeling and modern quant finance
techniques, I gladly signed up and dug into the data. I developed a model after
a few weeks and submitted my code just before the deadline.

I'm happy to share that so far I placed **32/4407 (top 0.8%)** in the world! This
rank will update week-to-week as new market data is processed until the
competition's end in November. I'm excited to see where I finally place! 🥳

I had so much fun competing that I signed up for CrunchDAO's other quant
competition, the weekly [DataCrunch
tournament](https://tournament.crunchdao.com). DataCrunch is a rolling
tournament in which participants model new market data as it comes in
week-to-week. This gave me an opportunity to refine my modeling and development
pipeline, specifically using more rigorous time series cross validation methods.

## How CrunchDAO works

CrunchDAO is a decentralized autonomous organization that crowdsources data
science tasks across its members. The DAO primarily works alongside financial
institutions to provide signals for automated trading. The basic pipeline is
shown below:

```
Researchers provide models ➡️ CrunchDAO aggregates into a trading signal ➡️
financial institutions execute transactions

Financial institutions profit ➡️ CrunchDAO distributes earnings ➡️ researchers
get rewarded
```

You can watch a nice explanation [🎥 here][crunchdaoexplain]

Financial institutions use these predictions to rank stocks in a basket. They
buy top-ranked stocks and short-sell bottom-ranked stocks, creating a net
neutral portfolio. This is called a "long-short" strategy.

## The data

CrunchDAO preprocesses and anonymizes its data to encourage participants to use
purely statistical models without reference to economic principles. The data
has the following format, with thousands of rows of data:

```
| time | feature 1 | feature 2 | ... | feature 600 | returns |
|------|-----------|-----------|-----|-------------|---------|
| 1    | 0.2       | 1.1       | ... | -0.5        | 2.2     |
| 1    | -1.3      | 0.1       | ... | 0.3         | -1.1    |
| 2    | 0.9       | -0.9      | ... | 1.2         | 0.3     |
```

Researchers analyze the provided data to create statistical models predicting
returns. Models are evaluated by the [Spearman rank correlation][spearman]
between their return prediction and the actual returns observed in the market.
This rewards models that accurately predict which stocks will be at the top and
bottom of the basket in a given time period.

## My models

### ADIALab competition

I started my journey by working through the [📔 Jupyter notebooks][crunchdaonb]
provided by the CrunchDAO crew. I also connected with staff and other
participants on the CrunchDAO Discord channel and read up on [modern time series
regression][timeseries] and [statistical learning][statlearning] techniques. 

My data exploration and model development for the ADIALab competition is
detailed in this [📔 Jupyter notebook][adianb]. In short, I created a
simple linear regression model that provides moderate but stable accuracy over
time. The model uses [🕸️ elastic net regularization][elasticnet] to prevent
overfitting the model to noise. Basic cross validation on a holdout dataset 
found optimal hyperparameters, and simple trial-and-error with the retraining
rate indicated I should retrain the model every 4 time periods as new data comes
in.

### DataCrunch tournament

After squeezing in my final submission for the ADIALab tournament just before the
deadline, I turned my attention to the DataCrunch tournament. I implemented a
more robust cross validation technique for the elastic net and explored a wider
range of hyperparameter values. This [📔 Jupyter notebook][datacrunchnb] shows
the code and data analysis for my DataCrunch models. 

I implemented a conservative and an aggressive cross validation method to find
optimal hyperparameters -- see Section 1 in the notebook for details. In the
end, I used aggressive method in order to leverage time series autocorrelation
between the end of the training data and beginning of the test data.

The graph below shows an example of tuning both the lookback training period and
elastic net L1 ratio to maximize Spearman correlation in the aggressive CV
method. The graph shows fairly smooth behavior, indicating our CV method
performs stably. The optimal hyperparameters found with the simple grid search
are clear winners compared to the rest.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/cd-project_crossval.jpg"
        title="cross validation of lookback period and L1 ratio"
        class="img-fluid rounded z-depth-1"
        width="500"%}
    </div>
    <div class="col-sm mt-3 mt-md-0">
    </div>
</div>
<div class="caption"> Spearman correlation score vs. lookback period for the
elastic net with `alpha=0.0001` found via the aggressive cross validation
strategy. Colors indicate values of `L1 ratio` parameter which tunes L1 vs. L2
regularization. Brighter colors indicate higher ratio (bounded between 0 and 1).
The graph shows a smooth trend with a clear optimum, indicating stability in our
cross validation technique. </div>

## Performance 

My elastic net model's performance in the ADIALab competition is shown below.
The red data indicates my performance on the training dataset, and the blue data
indicates my performance on the test data. Luckily, my elastic net model
generalizes well to new data and has generated fantastic performance recently!

Each week until mid-November will bring new market data, so I won't know my
final ranking until then. For now, I'm ranked 32/4407! 🎉

<img src="/assets/img/cd-project_performance.jpg" width="800"/>

The performance in the DataCrunch competition is ongoing and follows a [more
complicated evaluation methodology][datacruncheval]. Right now I am ranked
125/4407, but that will increase as my model is evaluated on new data. 🚀

## Conclusion

The past few months have been a blast as I've learned about quant finance
prediction models, time series regression, cross validation strategies, and
elastic net regularization. I'm so glad Jean reached out to let me know about
CrunchDAO! 🙏 I highly recommend checking out their competition if you're
interested in quant finance or machine learning in general.

These competitions taught me a very important lesson in data science: **simplicity
and robustness are paramount!** I was quite surprised to see my elastic net
linear regression models rise from the top 150 of the training leaderboard to
the top 40 of the test leaderboard 📈. Early in the competition, I read reports
from competitors who used neural networks, decision trees, and complex
ensembling techniques for their models. It was unfortunate to see some of these
folks fall from the top 50 to the top 500 as new data arrived 📉. I can only
imagine how much time they dedicated to training these models. In the end, they
overfit the training data -- a classic mistake that's hard to avoid! This taught
me to stick
with simple models with few hyperparamaters, focusing on robust cross validation
to ensure good generalization.

Quant funds need much more than just a prediction engine. They also need a
risk management system, a trading execution algorithm, a market impact
model, and more. I look forward to learning more about these topics next! Reach
out via LinkedIn or email if you know of any competitions that test these
skills.

[adianb]: https://drive.google.com/file/d/1eIQu0D8pY4dR1Xurzmbi0BP8WimYrMM8/view?usp=sharing
[datacrunchnb]: https://drive.google.com/file/d/1pJc1KKpvtl7nlzfwIVtTqFyNmd7IlKoq/view?usp=sharing
[timeseries]: https://www.google.com/books/edition/Time_Series_Analysis_and_Its_Application/sfFdDwAAQBAJ?hl=en&gbpv=0
[statlearning]: https://www.google.com/books/edition/The_Elements_of_Statistical_Learning/yPfZBwAAQBAJ?hl=en&gbpv=0
[crunchdaonb]: https://github.com/crunchdao/adialab-notebooks
[elasticnet]: https://en.wikipedia.org/wiki/Elastic_net_regularization
[datacruncheval]: https://docs.crunchdao.com/datacrunch-tournament/scoring/live-score-computation-process
[crunchdaoexplain]: https://www.youtube.com/watch?v=30h6A7MiEDk
[spearman]: https://en.wikipedia.org/wiki/Spearman%27s_rank_correlation_coefficient
