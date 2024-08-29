YouTube Video Downloader:

This Python project is a simple YouTube video downloader that allows users to download videos from YouTube. It uses the pytube3 and yt-dlp libraries to handle video extraction and downloading.

Features:
Fetch video details such as title, views, length, description, and rating.
Download videos in the best available quality.

Installation:
To get started with this project, you'll need to install the required libraries. You can install them using pip:


pip install pytube3 yt-dlp

Note: If you need to upgrade pytube3, use the following command:
pip install --upgrade pytube3

Enter the YouTube video URL when prompted.
The script will fetch and display video details.
You will be asked if you want to download the video. Type yes to download, or no to abort.

from pytube import YouTube
from yt_dlp import YoutubeDL

# Prompt the user to enter a YouTube video URL
link = input("Enter the video link: ")

# Create a YouTube object using the provided URL
yt = YouTube(link)

# Print video details
print("Title:", yt.title)
print("Number of views:", yt.views)
print("Length of video:", yt.length)
print("Description:", yt.description)
print("Rating of video:", yt.rating)

# Ask the user if they want to download the video
download_option = input("Do you want to download this video? (yes/no): ").lower()

if download_option == "yes":
    url = link
    ydl_opts = {'format': 'best'}
    with YoutubeDL(ydl_opts) as ydl:
        print("Downloading...")
        ydl.download([url])
        print("Download completed.")
else:
    print("Download aborted.")
Contributing
Feel free to contribute to this project by submitting issues or pull requests. Any improvements or suggestions are welcome!

License
This project is licensed under the MIT License - see the LICENSE file for details.

