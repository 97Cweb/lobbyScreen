# lobbyScreen
A simple lobby screen index that can be hosted on a simple python server using a Raspberry Pi. 

Any pictures in the folder get added to the screen on next refresh

Background will change colours based on time, from a blue, to a black, to a sunrise. 

Supported extensions for slides are jpg, png, gif. Easy to add others that are supported by browsers


logo.png - logo added to bottom left, below news
rss feed - configurable source, uses surfing waves: https://surfing-waves.com/feed.htm MUST BE CONFIGURED ON THEIR SITE DUE TO CACHING REQUIREMENTS
weather  - configurable source, uses forecast7: https://forecast7.com/en/42d31n83d04/windsor/

Note: I am not responsible for their content, if theirs breaks, this will also

# Basic setup (windows)
1. Have python installed, including path access (checkbox at bottom of Python installer)
2. have contents of git above saved in a folder
3. Open folder in file browser
4. Click on file path address. Replace file path with "cmd". This will launch a command prompt there
5. Type the following command: python -m http.server
    a. if that did not work, there are multiple commands possible for windows, go to https://developer.mozilla.org/en-US/docs/Learn/Common_questions/set_up_a_local_testing_server for other options
6. Open browser to http://localhost:8000/

# Raspberry Pi Setup
This is useful for your actual install for your TV. Recommend getting something with lots of RAM (1GB will not cut it) as images are expensive

1. Store the git contents in an easily accessible location (Desktop if you don't mind looking at it)
2. To test, open command prompt and go to the folder. Run "python -m SimpleHTTPServer "
3. Open browser to http://localhost:8000/
4. For auto deploy, sh file will need teh following lines added:
    ``` 
    cd /
    cd /home/pi/Desktop/screen
    python -m SimpleHTTPServer 
    cd /
    ```
    where the /home/pi/Desktop/screen is the path to the fold holding the git contents. For further instructions, look this up. Messing up in here is a great way to really break your pi. 
5. Enable start on boot for your browser. This is different and changes per Pi version, so look this up also. The url will still be http://localhost:8000/

# Troubleshooting
It should be functional, but there are multiple ways it can go wrong
1. Q: Takes too long to load/does nothing
   A: Reduce the number of pictures in the folder
2. Q: Component not showing up
   A: Check changes you made, odds are something is mispelt.
3. Q: Wrong weather location
   A: Change it in the index file. Uses special link. Search google for "forecast7.com <town name>" to find the correct one

Please check the errors thrown by your browser before asking questions.
    
Thank you
