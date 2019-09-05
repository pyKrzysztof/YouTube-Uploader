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
- default_parameters -> default parameters that are used when no json matches the video file, or when the json doesn't have all the values.

## Video Config
To create a config linked to a video, create a file with the same name but with extension .json
For example if video name is tutorial.mp4 then tutorial.json would contain config of this video.

Keys are the same as default parameters with additional 'title' key.

