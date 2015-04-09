---
layout: page
title: Scheduling Broadcasts in a Network of Timelines
homepage: True
permalink: /scheduling/
---

Supplementary information for our KDD '15 submission.

## Paper

[Preprint](2015.KDD.EmaadAhmedManzoor.pdf); a changelog is below:

   * 2015.04.08: Fixes based on reviewer comments.
      * Defined *U*, corrected *F/R* typo.

   * 2015.02.20: KDD '15 submission.

## Data

We use the [Twitter-Friends](http://linshuyang.com/research/PDC/) dataset described
in the following paper:

> Steering Information Diffusion Dynamically against User Attention Limitation.
> Shuyang Lin, Qingbo Hu, Fengjiao Wang, Philip S. Yu. ICDM ’14.

We provide Python [pickles](https://wiki.python.org/moin/UsingPickle)
of this data for convenient reuse in code:

   * `all_links.p` ([Download](all_tweets.p)): A list of tuples of user ID's,
     one for each link in the network, of the form *(a, b)* where *b* follows *a*.

   * `all_tweets.p` ([Download](all_tweets.p)): A list of tuples, one for each tweet,
     containing following information in order:

      1. Tweet creator ID.
      2. Tweet creation time (in milliseconds since the epoch).
      3. Retweeted user ID (-1 if not a retweet).
      4. Replied-to user ID (-1 if not a reply).

## Attention Potential

[Annotated code](https://gist.github.com/emaadmanzoor/a1e6632f905fa6bcbbcb).

Attention potential is a directed function *ap(a,b)*, estimating the attention that follower *b*
gives producer *a*. Likewise, reactions are also directed *reactions(a,b)*, measuring the number
of retweets to and replies of *a*'s tweets by *b*.

### Parameter Estimation

Behavioural parameters are estimated as detailed in section 4 of the paper. In summary:

   * *delta*: Tie weakness, estimated as the empirical probability of retweeting or
     replying to a user. This is used with a geometric cluster survival function.

   * *rho*: Estimated using the empirical average number of posts consumed on each login.
     This is then used to find the geometric parameter *rho*, assuming a geometric user
     survival function.

     Since we rely only on observed data, we consider a tweet as *consumed* if it is
     retweeted or replied to, and a *login* is counted for every tweet posted by a user
     after a gap of over 8 hours (why 8? see section 2.2 in the paper!).

   * *gamma*: Estimated as the empirical probability of a user retweeting
     or replying to any tweet.

### Correlation Results

The attention potential as estimated above, when evaluated on this Twitter dataset:

   * Is **73.61%** correlated with the retweets obtained.
   * Is **significantly** correlated (*p* < 2.2e-16).
   * Is correlated with a 95% confidence interval of [72.72%, 74.48%].
