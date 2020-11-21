# Model effectiveness(R1Q1, R2Q1)

Given a query, our tool can recommend a list of query reformulations, which provide hints to bridge both the gap between developers’ intention and input queries, and the semantic gap between developers’ queries and the documents.

In addition to evaluating the query reformulation quality in Section Ⅴ, in each query reformulation thread (mentioned at the end of Section Ⅱ), we also collected a pair of users’ original query and finally-visited post which is assumed to be the target post. These 65,103 pairs can be used to demonstrate the retrieval effectiveness of our approach. For each pair, we adopt both our approach and baselines in Section V.B to reformulate the query and check the ranking of the target post in all candidate posts on Stack Overflow.

We use MRR (Mean Reciprocal Rank) as the metric which is the average of the reciprocal ranks (the multiplicative inverse of the rank of the target post in the search result) of the search results for all the queries. For example, given a query, if the target post ranks fifth in the search result, the reciprocal rank is 1/5=0.2, a higher MRR value indicates better search result.

As seen in the table below, our approach achieves the best performance with 23.7% boost to the best baseline. We had omitted the results from the submitted version for space reasons since the focus of our work is on reformulation accuracy instead of effectiveness (which has been studied before), but are happy to include the results for camera-ready.

Approach|MRR
------------------|------------
Original Query|0.075
LanguageTool|0.071
GooglePS|0.083
HRED-qs|0.108
seq2seq|0.127
seq2seq+Attn.|0.139
**SEQUER**|**0.172**
