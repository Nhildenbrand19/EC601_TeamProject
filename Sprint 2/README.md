## Sprint 2
The goal for this sprint was to get our environment set up and try and implement and adapt some open source code to confirm we were working in the right direction. More specifically, we wanted to get all of our data and test code into the SCC to see if we were able to run anything. The first major part of this was making sure that we had the necessary files included in our directory to load the imports needed. This meant uploading helper code to the SCC to then import into our main program. 

![Helper Import](https://user-images.githubusercontent.com/74614080/138895174-92df0d13-e516-48e3-9ff8-ee0cc231a1a5.png)

We then needed to import the necessary libraries from python.

![Imports](https://user-images.githubusercontent.com/74614080/138895229-02100b61-cc6f-4614-bace-9bc609a86608.png)

The next part of the code we ran was reading in the data that was given in the competition. The naming of file paths was tricky in the beginning in the SCC but actually relatively straightforward after some time. You can see below the example of this code taking in the given csv files and assigning them either the tracking or helmets variable depending on their title. 

![Tracking Assignment](https://user-images.githubusercontent.com/74614080/138895302-a2f885b3-8cd1-45a5-a06d-7e01916fe16b.png)

Now we are going to split the video into frames for our program to analyze. As we mentioned before, this algorithm we are attempting to use, looks at each frame of the video and puts them back together at the end. We are trying to help with that in this code.

![Video Frames](https://user-images.githubusercontent.com/74614080/138895352-3e653a55-633d-405a-bff6-757e09494fb8.png)

I could not include the next block of code in a screenshot as it is about 110 lines of code but essentially we are processing the data that we read in early and creating the settings for the mapping. What I mean by this is that we need to create parameters that DeepSort can look at to determine for example where a helmet could be or what an impact is. The loading bar you see below is confirmation that the code ran to 100% and took only 2 minutes and 9 seconds, running at a speed of 2.52 iterations per second. To compare, running this on my personal computer took 10+ hours and did not complete.

![Parameters](https://user-images.githubusercontent.com/74614080/138895405-bb682a13-13b6-4e5b-a8ca-ef259a11f4cf.png)

The next part is scoring the predictions before applying our DeepSort algorithm postprocessing. The validation score that we got when running the code is actually higher than the open source code we adapted. This was our second sprint and we are very happy with the progress that we made. 

![Validation Score](https://user-images.githubusercontent.com/74614080/138895602-8d203d83-5055-4f3d-818c-210290376ace.png)
