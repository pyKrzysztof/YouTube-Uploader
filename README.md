# YouTube-Uploader
Automatic uploading of videos to youtube.


## Config
- API_name -> don't touch
- API_ver -> if new version comes up maybe I'll only need to change that (lol).
- videos_path -> full path to the folder with videos.
- archived_videos_path -> full path to the folder where you want uploaded videos to be moved.
- do_archive_videos -> if set to <b>true</b> then the videos will be moved to archived videos so they don't get uploaded twice next time.
- secret_path -> full path to client oauth secret file. (More later)
- refresh_token_path -> path where the refresh_token will be saved and read from. (do not create your own)
- default_parameters -> default parameters that are used when no json matches the video file, or when the json doesn't have all the values. NOTE: about categoryID, this is numerical, do not enter a text here cause it will cause request errors. You can look up IDs online or change them after.

## Usage
It's as simple as running `python3 run.py`
You need the following packages installed:
`pip install oauth2client google-api-python-client google-auth-oauthlib google-auth-httplib2`
Make sure you install them for Python 3.x and not 2.x.

## Video Config
To create a config linked to a video, create a file with the same name but with extension .json
For example if video name is tutorial.mp4 then tutorial.json would contain config of this video.

Keys are the same as default parameters with additional 'title' key. By default, the video title is filename without the extension.


## What is this

This is YouTube video uploader which utilizes the YouTube API, to use it you need oauth client secret which you need from google developers website, you have to create a project, download the api, create and download the oauth. I don't want to get into this here, just look it up.
