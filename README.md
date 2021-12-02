# Dockerize a Python Script

[Google Images Download](https://github.com/sikaeducation/google-images-download) ([documentation](https://google-images-download.readthedocs.io/en/latest/index.html)) is a Python application that downloads any images matching a keyword or set of keywords. However, it requires a Python environment to compile and install it. Your task is to do this with Docker.

* Note that all of this should be done with Docker Engine (rather than Docker Compose)
* You should not use any version of Python that happens to be installed on your computer
* Pick an appropriate Python image. Not every image will work, but you should be able to get the full size of the image down to at most 160MB.
* Make sure to install the dependencies for the app.
* Once the dependencies are installed, the command to install the app to the container is `python setup.py install`
* The basic syntax for running the app inside the container is `googleimagesdownload -k "Some Keyword" -l 1`, where the number for `-l` is a limit on the number of images to download.
* The app should use a combination of entrypoint and command
* Downloaded images should go in the `images` folder. Note that you need to mount a volume for this to work.
* Make a script to abstract out the Docker command. The entire app should be runnable on the host computer by running `./google-images-downloader "Search term goes here"`. Arguments to shell scripts can be accessed by number, so the search term argument can be accessed with `$1`. Don't forget to make the script executable!

You'll know it works if you can run `./image-downloader "Kyle Coberly"` and get 1 file in the `images/Kyle\ Coberly/` directory.

## Bonus Challenges

1) Add the script to your `PATH` and mount the images folder from your downloads directory.
2) Use multi-stage builds to make the image as small as possible
