# Twitch Clip Batch Downloader  
![example-gif](https://github.com/amiechen/twitch-batch-loader/blob/master/example.gif)

### Pre-Install:

1) Get a twitch `Client ID` by registering a twitch app [here](https://dev.twitch.tv/dashboard/apps/create).
Once finished, copy the `Client ID`. You will need it to run the script.

2) Install python 3 on your machine if you haven't.

### Usage:

1) Install python packages
```
pip install requests
```

2) Delete the example clips in `clips.txt` and the ones your want. Put each URL on it's own line. No commas or anything like that.

3) Then run the batchloader script with your new Client Id using the provided clip list or create your list automatically with a provided broadcaster id, filtering by time is possible by provding two RFC3339 timestamps.
The timestamps need to be at least one month apart to get results back from twitch.
The resulting list is still not complete though, there seems to be a cap after fetching approximately 1046 clips in the full timespan from beginning to end, by splitting the time frame up into 1 month steps I was able to go above the 1045 limit.
By using the twitch website to list all clips by views to get additional clip slugs I was able to get clips I couldn't get using the twich API.
```
cd twitch-batch-loader
python batchloader.py <YOUR AWESOME CLIENT ID> [<THE AWESOME BROADCASTER ID> [<Start date of time frame> <End date of time frame>]]
```

Voilà! once you see the finished message in your terminal, check the `downloads` folder in this repo and you should see the videos there.
