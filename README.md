# Project

From words to action: Mapping political party ideologies to climate action

# Author

Tim Koenders

# 1 Research Questions

1. How do political party preferences towards climate policy, as derived from manifesto analysis, correlate with the actual implementation of climate policies in different countries and election periods?

2. What patterns and trends can be discerned by creating an election-country-specific index and examining its relationship with real-world climate policy outcomes?

# 2 Introduction

This research employs text mining techniques to analyze political party manifestos from the Manifesto Project across diverse countries and election periods. First, the study aims to create a nuanced party preference index, measuring each party's stance on government intervention for environmentally sustainable economic practices. Second, an country-election-specific index is created by weighting the party preference index by their respective vote shares to account for varying levels of bargaining  power of parties in political coalitions. Finally, the study uses this index to help to explain the number of climate policies implemented by a government each election period.

# 3 Motivation

The examination of the relationship between party ideologies and climate change policy remains a relatively understudied area within political science. In an effort to contribute to this discourse, Farstad et al. (2017) investigated the salience of climate change in party manifestos, utilizing data from the Comparative Manifesto Project (CMP). Their findings underscore the pivotal role of left–right ideology in explaining variations in climate change salience, surpassing the influence of other party characteristics. This highlights the profound impact of ideological positions in shaping party stances on environmental issues.

However, the reliance on hand-coded CMP data introduces methodological and theoretical challenges, as outlined by Gemenis (2017) in four distinct areas: (1) theoretical underpinnings of the coding scheme; (2) document selection; (3) coding reliability; and (4) scaling. Beyond these general challenges, our specific context introduces more serious concerns. Notably, the absence of any mention of climate change in the CMP codebook until 2014 raises fundamental issues related to content validation. Consequently, the salience of issues spanning multiple categories may be underestimated, and certain measures may omit crucial elements of climate policy, such as renewable energy and energy efficiency measures, which are present in other categories. Conversely, some measures may include elements that clearly fall outside any reasonable definition of climate policy.

Recognizing these limitations, recent advancements in automated text analysis methods offer a promising avenue for refining our understanding of party ideologies and climate change policy. Orellana and Bisgin (2023) exemplify the efficacy of Natural Language Processing (NLP) in analyzing New Zealand political party manifestos. Their study not only highlights the potential of NLP for tasks such as estimating document similarity, topic modeling, and sentiment analysis but also emphasizes the need for fine-tuning in the application of these techniques. By leveraging NLP and textual analysis, we can potentially overcome some of the challenges associated with hand-coded data and better identify parties ideologies towards climate action.

# 4 Data

First, we collect data of all climate policies implemented worldwide via the IEA’s Policies and Measures Database. Second, we collect election and manifesto data from The Manifesto Project which documents political parties' election manifestos in order to study their policy preferences. Currently, the idea is to focus on English-speaking countries as those manifestos are presented in the English language and there will be no need for complex multilingual textual analysis. Finally, we collect macroeconomic data from the World Economic Outlook Database to control for various factors that influence the number of climate policies implemented and are (potentially) correlated with our index. 

# 5 Methology

Manifestos from various countries and election periods are subjected to advanced text-mining techniques, including topic modeling and sentiment analysis. Topic modeling may help objectively categorize and visualize the ideas political parties are promoting while sentiment analysis has the potential to show each political party’s attitude towards a policy idea. This process yields topic relevance and sentiment scores, forming the basis for a comprehensive party preference index. Specifically, to estimate how parties feel about government intervention towards limiting climate change, a party’s position is estimated using the following steps:

• We use topic modeling to find the climate-change related topics;

• We use the key words making up the topic to find every sentence in a party’s manifesto that mentions that topic;

• We apply the VADER algorithm to each of those sentences to estimate the sentiment of that sentence;

• We create a party’s total sentiment score on that topic by calculating the average polarity score across all the sentences in a manifesto mentioning that topic and multiplying it by the log of the number of times (sentences) a party mentions the topic in their manifesto. Multiplying by the number of times a party mentions a topic helps account for the importance a party places on that topic. Taking the log reduces the effects of sizable variations in the number of mentions. Some parties, for example, will not mention a topic at all.

From this party specific preference index, 

• We create an election-country-specific index by creating a weighted average of the party specific index where the weights are equal to their respective vote shares.

• By correlating this election-country-specific index with real-world data on climate policies, we build upon political economy theory and investigate patterns and trends, providing data-driven insights into the impact of political ideologies on environmental policy outcomes. 

# 6 Relevance

This research is highly relevant in the current global context where climate change is a pressing issue. Understanding the correlation between political ideologies and climate action can provide valuable insights into how policy decisions are influenced and implemented. The methodology employed in this research, which includes advanced text mining techniques and sentiment analysis, is innovative and comprehensive. It not only analyzes the content of political party manifestos but also quantifies the sentiment towards climate change policies. This approach provides a more nuanced understanding of party preferences and their impact on climate action. Moreover, the creation of an election-country-specific index provides a unique perspective on the collective impact of political parties within a specific election period and country. This could help identify patterns and trends that might not be apparent when analyzing individual parties. Overall, this research could contribute significantly to the field of political economy and environmental policy, providing data-driven insights that could inform future policy decisions and strategies. It could also serve as a model for similar studies in other policy areas.

# References

Farstad, F. M., (2017). What explains variation in parties’ climate change salience? Party Politics, 24(6). https://doi.org/10.1177/13540688176934

Gemenis, K. (2017). What to do (and not to do) with the Comparative Manifestos Project Data. Journal Name, 61(1_suppl). https://doi.org/10.1111/1467-9248.12015

Orellana, S., & Bisgin, H. (2023). Using Natural Language Processing to Analyze Political Party Manifestos from New Zealand. Information, 14(3), 152. https://doi.org/10.3390/info14030152

