# YouTube-Uploader
Automatic uploading of videos to YouTube.


## Config
- API_name -> don't touch
- API_ver -> if new version comes up maybe I'll only need to change that (lol).
- videos_path -> full path to the folder with videos.
- archived_videos_path -> full path to the folder where you want uploaded videos to be moved.
- do_archive_videos -> if set to <b>true</b> then the videos will be moved to archived videos so they don't get uploaded twice next time.
- secret_path -> full path to client oauth secret file. (More later)
- refresh_token_path -> path where the refresh_token will be saved and read from. (do not create your own)
- default_parameters -> default parameters that are used when no json matches the video file, or when the json doesn't have all the values. NOTE: about categoryID, this is numerical, do not enter a text here cause it will cause request errors. You can look up IDs online or change them after.

## Getting started with the YouTube API
You have to do this before using the script.
1) Go to google developers console https://console.developers.google.com
2) Create a new project.
3) Go to library tab and search for YouTube Data API v3, enable it for your project.
4) Navigate to credentials tab, and add <b>OAuth client ID</b> (of type other)
5) You may also create the API key but it is not utilized in this project.
6) Download the client_secret(your-id).json (your <b>OAuth 2.0 client ID</b>) file. ( I recommend renaming it to client_secret.json)

## Usage
Make sure you adjusted the config.json according to the schematic above. The secret_path HAS TO be valid and point to your oauth2 client ID file.
It's as simple as running `python3 run.py`. The first use will open up the browser and ask you to authorize the application.
You need the following packages installed:
`pip install oauth2client google-api-python-client google-auth-oauthlib google-auth-httplib2`
Make sure you install them for Python 3.x and not 2.x.

After the authorization is completed, the videos from the path you specified will be uploaded to YouTube with default parameters <b>unless</b> you also created a .json file with the same filename as the video and changed the default parameters.
I highly recommend that you have <b>do_archive_videos</b> (also don't forget to set the path) turned <b>on</b>, as unless you get rid of these files before the next usage of the script, they would be uploaded twice (not uploaded at all as YouTube knows it's already uploaded that request.) and you would lose your <b>quota</b>.
  
#### What is Quota and more about YouTube API
YouTube API utilizes a daily limit of operations that can be requested. Each operation is priced differently. These units are called <b>Quotas<b/>, daily you have access to <b>N<b/> quotas. A video upload has a cost of 1600 quotas. Which initially should give you 6 uploads per day, which I think is enough. But if you need more quotas, then you can request them.

## Video Config
To create a config linked to a video, create a file with the same name but with extension .json
For example if video name is tutorial.mp4 then tutorial.json would contain config of this video.

Keys are the same as default parameters with additional 'title' key. By default (f not specified), the video title is filename without the extension.


## What is this

This is YouTube video uploader which utilizes the YouTube API, to use it you need oauth client secret which you need from google developers website, you have to create a project, download the api, create and download the oauth. I don't want to get into this here, just look it up.
