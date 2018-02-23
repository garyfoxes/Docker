
**Run Dockerfile**

docker image build -t custom_nginx . (first time you run it may take longer,after that it will be cached and will spin up quickly)

TIP 
Ordering of a dockerfile is important. 
Keep commands that change the least at the top and commands that change the most at the bottom
Reason:
if a line is changed at the top, the rest of the image in the dockerfile has to be rebuilt.
Whereas if you change a line near the bottom, then most of the file will be cached when been re-built
