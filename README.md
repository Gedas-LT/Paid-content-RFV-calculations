# Paid content RFV calculations

Analysis of Delfi Plius subscriber engagement. The notebooks build a Recency–Frequency–Volume (RFV) score from on-site activity, check whether that score tracks subscription and spending behaviour, and try to segment users with clustering.

## RFV score

For each user, over the analysis window:

- **Recency** — days between the user's last visit and the anchor date (the end of the window).
- **Frequency** — number of distinct days the user visited.
- **Volume** — pageviews in the EDA and RFV notebooks; distinct articles in the clustering notebook.

```
rfv_score = (frequency * sqrt(volume)) / (recency + 1)
```

The `+ 1` keeps the score defined for users who visited on the anchor date (`recency = 0`).