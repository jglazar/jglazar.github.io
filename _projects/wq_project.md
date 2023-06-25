---
layout: page
title: WorldQuant Global Alphathon
description: Creating alpha strategies for portfolios
img: assets/img/wq-project_alpha.png
importance: 1
category: work
---

From late March through Fall 2023, [WorldQuant](https://www.worldquant.com) is
running its annual [International Quant
Championship](https://www.worldquant.com/brain/iqc/).

The competition runs on WorldQuant's [🧠 BRAIN
platform](https://www.worldquant.com/brain/), which hosts over 85,000 data
fields, hundreds of operator functions, and a custom backtesting simulator to
test alpha ideas.

I'm happy to share that I placed 382/29,101 in the world (top 1.3%) and 20/1,191
(top 1.7%) in the USA during the 1st round. I placed 315/2,920 in the world (top
11%) and 19/100 in the USA for the 2nd round. The third round involved the best
candidates from each region, so I did not qualify to advance. Go team USA 🇺🇸!

## Competition rules

Alphas are the building blocks of investment portfolio construction. They are
functions which assign weights to each stock in a given universe, dictating how
much stock to buy on a given day.

Contestants generate alphas using operators to process historical stock data like price,
volume, revenue, options prices, and news coverage. These operators and data
fields can be combined in exponentially many ways, opening the door for
creativity and uniqueness.

I recorded 


The competition involved a ten-minute pitch of one publicly-traded
company. Each pitch was judged on its investment thesis covering company
background, scientific and financial due diligence, valuation, and upcoming
catalyst analysis.

## Generating alphas

WorldQuant generously hosted Q and A sessions with current quant researchers. I
got the chance to interact with researchers from India, Korea, and China as they
taught about topics from alpha neutralization (unbiasing alphas across different
industries or sectors) to vector data fields (which provide more than 1 data
point per day). 

These webinars were the source of countless alpha ideas and tactics to improve performance. 
My [webinar notes][webinar] list out the alphas and tips shared by the researchers, as well as the 
answers to some of the questions asked by myself and the other participants.

I found WorldQuant's articles to be fantastic sources of new ideas. My
[article notes][ideas] show hundreds of the alphas I tested. For example, I
tried *every single one* of the [101 formulaic alphas](https://arxiv.org/pdf/1601.00991.pdf). 
It took me over an hour, but I managed to find a few worth submitting!

## A few alphas

Overall, I tested 1,103 alphas and submitted 28 for scoring. These involved
data fields comprising price, volume, fundamental, and news information on
stocks from the USA and China.

Here are a few of my favorite alphas:



## Conclusion

🎉 After months of researching and testing alphas, attending seminars, and reading articles, 
I am happy to finish out the 2nd round in the top 20 of the USA. I'll certainly
be following along to cheer on the USA team as it progresses into the 3rd
round!

I had a great time learning about backtesting, alpha generation, and data
exploration from some of the best quant researchers in the world. The tutorials,
seminars, and recommended papers complemented each other well.

I would like to thank WorldQuant again for putting together such a well-run
event and exciting event. I'm looking forward to another competition next
year!

[alphas]: https://github.com/jglazar/notes/blob/main/quant_interview/submitted_alphas.md
[ideas]: https://github.com/jglazar/notes/blob/main/quant_interview/alpha_ideas.md
[webinar]: https://github.com/jglazar/notes/blob/main/quant_interview/worldquant_seminar.md
