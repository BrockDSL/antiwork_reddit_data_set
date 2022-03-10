# antiwork Reddit Data Set

code and data to generate the antiwork dataset

parameters:

- posts to r/antiwork
- 09/01/21 - 12/31/21
- sorted by *popularity* and *controversy* scores

[Header data set](https://github.com/BrockDSL/antiwork_reddit_data_set/blob/main/antiwork.csv)

[Example PRAW item fetched](https://gist.github.com/elibtronic/030706222ce9240c3bc5bd959f5af64f)

## Prep Steps

- Install [https://github.com/Jabb0/SubredditDownloader](https://github.com/Jabb0/SubredditDownloader)
- Invoke on the command line to get the 'headers' of post that match above
```
SubredditDownloader % subredditdownloader -db ../anti-work.db -r antiwork -ds pushshift --reddit-client-id FILL --reddit-client-secret FILL --reddit-username elibtronic --start-utc 1630468800 --end-utc 1641013200
```
- Use the `post_id` of harvested heads to get full api data using [PRAW](https://praw.readthedocs.io/en/stable/) and save as [Pickle](https://wiki.python.org/moin/UsingPickle) file
- Run `Data Set Assembly.ipynb` with the proper path to the pickles set
- will save resulting data in CSV called `antiwork_massive.csv` 
