# ferronronbox

installation d'une ronronbox
# soft
 - pour l'écran voir https://learn.adafruit.com/adafruit-pitft-28-inch-resistive-touchscreen-display-raspberry-pi/software-installation avec l'image https://s3.amazonaws.com/adafruit-raspberry-pi/2016-10-18-pitft-28r.zip
 - https://wiki.mchobby.be/index.php?title=RASP-PiTFT
 - un peu plus de configuration de l'écran https://learn.adafruit.com/raspi-animated-gif-picture-frame/installing-the-pitft
```
sudo apt install git
sudo pip3 install youtube-dl
sudo apt-get install mplayer
sudo apt-get install fbi
sudo pip3 install GPIO
# install https://pypi.python.org/pypi/mplayer.py/0.7.0

wget http://adafruit-download.s3.amazonaws.com/adapiluv320x240.jpg
sudo fbi -T 2 -d /dev/fb1 -noverbose -a adapiluv320x240.jpg
```
# utilise
 - un rapberry pi
 - un ecran
 - des hauts parleurs
 - mplayer pour lire les videos, commands : https://www.mplayerhq.hu/DOCS/tech/slave.txt
 - un repo git pour stocker message photo sons
 - youtube-dl : https://github.com/rg3/youtube-dl/blob/master/youtube_dl/YoutubeDL.py#L129-L279

# technique
 - jouer une video : sudo SDL_VIDEODRIVER=fbcon SDL_FBDEV=/dev/fb1 mplayer -vo sdl -framedrop bigbuckbunny320p.mp4
 - afficher un gif : sudo fbi -T 2 -d /dev/fb1 -noverbose -a adapiluv320x240.jpg
 - jouer un son :
 - telechargement de vidéo : 
  - youtube-dl -f 36 https://www.youtube.com/watch?v=g25KM5WffAg
  - youtube-dl -f "best[height<=240]" https://www.youtube.com/watch?v=CyehpawuU4U
 - jouer un gif annimé
 ```
 import subprocess
subprocess.call('curl -o metronome.mp4 https://media.giphy.com/media/GFHJXPCoVQEec/giphy.mp4', shell=True)
subprocess.call('sudo SDL_VIDEODRIVER=fbcon SDL_FBDEV=/dev/fb1 mplayer -vo sdl metronome.mp4', shell=True)
```
# à faire
 - messagerie
 - agenda
 - utiliser https://github.com/Giphy/GiphyAPI avec des url du type https://media.giphy.com/media/XXX/giphy.gif
 - reprendre le script d'install https://raw.githubusercontent.com/adafruit/Raspberry-Pi-Installer-Scripts/master/pitft-fbcp.sh
 - télécharger la playliste avec youtube-dl https://www.youtube.com/watch?v=0WfcgfGTMlY et curl -o XXXid XXXhttp
 - une IHM avec https://learn.adafruit.com/raspberry-pi-pygame-ui-basics/from-gpio-to-screen?view=all
 - btt d'arret http://www.pihomeserver.fr/2013/10/25/raspberry-pi-home-server-ajouter-bouton-darret/
 - btt d'arret qui wait_for_edge http://hardware-libre.fr/2013/07/raspberry-pi-5-ajouter-un-bouton-materiel-avec-python/
 - btt d'arret qui add_event_detect http://hardware-libre.fr/2013/07/ajouter-un-bouton-dextinction-avec-python/
