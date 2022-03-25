# Ganscrap
In this project I want to produce a gan image out of scraped photos posted by any user on instagram. On github there is the repository Instagram-Scraper which uses Python to download all the content from a single user. 

Running this command to install and run the instagram scraper. I do recommand to uve an envirorment and a new instagram account.
```bash
pip3 install instagram-scraper
mkdir jpg
cd jpg
instagram-scraper <username> -u <your username> -p <your password>             
```
And simply with few lines, all the images stored in a folder. In order to use [StyleGAN2-ada](https://colab.research.google.com/github/dvschultz/ml-art-colabs/blob/master/Stylegan2_ada_Custom_Training.ipynb) on google colab, we need to remove all the videos from the jpg folder and resize each photos to 256 pr 512 or 1024 which are ste supported size for this project. 
On my MacOs machine I have installed FFmpeg, and whith this is extremely simple to just convert all the pictrues to 512x512
```bash
mkdir resized
for filename in *.jpg; do ffmpeg -i "$filename" -y -vf scale=512:512 "resized/$filename";done
```
once all the images are stored in the resized folder you can compress the folder and upload to your google drive. 
Now click on the link [StyleGAN2-ada](https://colab.research.google.com/github/dvschultz/ml-art-colabs/blob/master/Stylegan2_ada_Custom_Training.ipynb) set your folder and path to your google drive an there you have a gan of the images scraped from instagram.

Unfortunately I keep getting the same error, which  I posted on Stackoverflow trying to get ans answer from there. In the mean time I am trying to execute the Google colab on the local machine at cci, (which should also be faster considering the 2080 gpu) 
