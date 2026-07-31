# wikipedia-signal: do Wikipedia pageviews move before the event?

## Goal
Test whether the traffic on a Wikipedia page carries information ahead of time: an
election, a film release, a news spike, a share price. The honest answer is probably
"sometimes, weakly", and that is a good result.

## Data
- Wikimedia Pageviews API: free, no key, daily history since 2015, all languages. One of
  the best open sources there is.
- Targets to correlate against: election results, box office, prices via yfinance.

## Steps
- [ ] Set up repo, Pageviews API client, local cache
- [ ] Pick 3 families of targets and build the list of associated pages
- [ ] Daily collector: archive the views of the tracked pages
- [ ] Clean: remove the weekly seasonality and the long trend
- [ ] Lagged correlations: views at D-k against the event at D
- [ ] Separate anticipation from reaction, which is the whole point and the main trap
- [ ] Granger causality test on the most promising series
- [ ] Negative control: rerun the analysis on unrelated pages to measure the false
      discovery rate
- [ ] README: where there is signal, and where there is none

## Done when
The negative control is in place and the README clearly separates anticipation from
plain reaction to the news.

## Traps
- Most view spikes follow the news, they do not precede it. Without a negative control
  you are telling yourself stories.
