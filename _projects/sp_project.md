---
layout: page
title: PBG Stock Pitch Competition
description: Finding, analyzing, and valuing a winning stock
img: assets/img/sp-project_pbg_logo.png
importance: 1
category: work
---

From mid March to late April, the [Penn Biotech
Group](https://pennbiotechgroup.org) ran its first [stock pitch
competition](https://pennbiotechgroup.org/investment-research-pbg). 

VP [David Polefrone](https://www.linkedin.com/in/dpolefrone/) and
co-president [Mengdi Tao](https://www.linkedin.com/in/mengditao/) organized six
seminars covering private and public biotech markets, scientific due diligence,
and valuation. These talks featured Wharton professors alongside public and
private equity analysts from firms including [RTW](https://www.rtwfunds.com),
[Commodore Capital](https://www.commodorecapital.com), and [Foresite
Capital](https://www.foresitecapital.com), together providing complementary
perspectives on biotech investing. 

At the end, PBG hosted a stock pitch competition featuring a judge panel of
industry experts.

## Competition rules

The competition attracted about 20 masters students, PhDs, and postdocs from
around Penn. The organizers grouped students into four teams. I elected to
participate as a solo team because I wanted to learn all aspects of stock
pitching -- vetting the company's leadership team, digging deep into products,
analyzing financial statements, and scouring scientific and legal publications
to learn about the science behind the company's pharmaceutical pipeline.

The competition involved a ten-minute pitch of one publicly-traded
company. Each pitch was judged on its investment thesis covering company
background, scientific and financial due diligence, valuation, and upcoming
catalyst analysis.

## Picking a stock

The start of the competition was hectic, as the organizers requested from each
participant a list of five good candidate stocks. I had no idea what to pick!
Their recommendation to stick to stocks listed in the `$XPH` and `$XBI` ETFs
narrowed down the field, but still left over 200 companies to screen.

I checked every company to find the five that best matched my interests and
expertise. I wanted to find a small- to medium-sized biotech firm specializing
in data analytics and scientific computation. 

Unfortunately I did not find a website with a screener tool for ETF holding
lists, stock tickers, and description data. [One
website](https://stockanalysis.com) had all the data I needed, but not on one
page. So, I wrote a **[📔 Python notebook][notebook]** to piece the data together.
[This YouTube tutorial](https://www.youtube.com/watch?v=uBAaQ1Oif9k) helped me
figure out how to bypass the IP blocker to request as much data as I needed,
letting me request any data on any stock.

My analysis of each stock's description narrowed down the field to: 
  * `$ABCL` AbCellera Biologics
  * `$RLAY` Relay Therapeutics
  * `$RXRX` Recursion Pharmaceuticals
  * `$TWST` Twist Biosciences
  * `$BTAI` BioXCel Therapeutics. 

In the end, I selected `$RXRX` Recursion Pharmaceuticals for my pitch!

## The pitch

I spent dozens of hours researching Recursion. I read the [founder's doctoral
research
articles](https://scholar.google.com/citations?hl=en&user=h-RMr_IAAAAJ),
reviewed dozens of equity research reports, tracked the company's FDA approval
processes, created **[📊 my own financial model for the stock's
valuation][valuation]**, and more. 

My work is neatly summarized in this **[🖥️ PowerPoint
presentation][presentation]** (also shown below). The slide notes contain tons
of extra details that didn't make it into the pitch. For example, did you know
that Recursion bought a small company called Vium, which was founded by [Joe
Betts-Lacroix](https://en.wikipedia.org/wiki/Joe_Betts-LaCroix), an inventor
who once held the world record for creating the smallest personal computer?
There's tons more tidbits like this which paint a more detailed picture of the
people and technologies that make up Recursion. 

A brief pitch: Recursion seeks to expedite drug delivery by guiding experiments
using machine learning algorithms trained on petabytes of proprietary data.
Recursion has collected over 21 Pb of imaging and transcriptomics data and owns
a world-top-100 supercomputer to analyze it all. Recursion's main value drivers
are its advanced drugs in Phase 2 FDA studies and its partnerships with the
large pharmaceutical companies Genentech and Bayer. In these partnerships,
Recursion offers over 3x quicker and cheaper drug development over competitors.
In return, they receive milestone payments and resources to enable FDA studies
and drug distribution. 

My simple valuation provides predictions for Recursion's top two drugs,
partnership revenues, R&D expenses, and taxes.  This puts the stock's value at
$10 per share, making it a **📈 strong buy** considering the current price around $5
(as of early May 2023).

## Conclusion

🎉 I am happy to share that my pitch won the competition! I came in 1st place out
of 4 teams, beating teams pitching `$PFE` Pfizer, `$CERE` Cerevel Therapeutics,
and another team pitching Recursion. The 1st place prize was $900, which will
certainly go towards some `$RXRX` stock. Let's hope it goes to the moon! 🚀

I had a blast during the event, and I learned a ton about biotech equity markets,
company valuation, drug development, reading financial statements, modeling in
Excel, and so much more. The seminars and competition complemented each other
well, allowing me and others ask the seminar speakers questions about their
experiences in stock selection, valuation, analysis, and drug development.

I would like to thank David and Mengdi, the PBG team, and the sponsors [Third
Rock Ventures](https://www.thirdrockventures.com) and
[B+labs](https://www.brandywinerealty.com/blabs) for putting together such an
insightful and exciting event. I'm looking forward to another competition next
year!

<div style="margin-left: auto;margin-right: auto;">
    <object data="../../assets/pdf/pbg_comp_slides_glazar.pdf" type="application/pdf" width="825px" height="465px">
        <embed src="../../assets/pdf/pbg_comp_slides_glazar.pdf">
            <p>This browser does not support PDFs. Please download the PDF to view it: 
            <a href="../../assets/pdf/pbg_comp_slides_glazar.pdf">Download PDF</a>.</p>
        </embed>
    </object>
</div>

[notebook]: https://colab.research.google.com/drive/1YNnSzxABPyvEjMSfxc0P26wE8J_vDcvs?usp=sharing
[presentation]: https://docs.google.com/presentation/d/1f6h3vIJaVeIdxS6lfeMHkGjJy9nLOtpd/edit?usp=sharing&ouid=118402071372269084201&rtpof=true&sd=true
[valuation]: https://docs.google.com/spreadsheets/d/1DXcWWqGpWAOU4H5GffCCOdIpkB9zLQkf/edit?usp=sharing&ouid=118402071372269084201&rtpof=true&sd=true
