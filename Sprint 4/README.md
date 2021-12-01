## Sprint 4

The goals for Sprint 4 are as follows

- Feed our algorithm other data to see the results

- Continue to fine tune parameters and compare to competition results

- Begin working towards or completing the combination of  individual frames to create final video


### Results
We can see below the output of our algorithm and confirmation that the we have successfully combined the individual frames from the previous sprint to create a video analysis. 


https://user-images.githubusercontent.com/74614080/143662721-2df2eeb9-f91d-4f69-982c-bcbe17d2e474.mp4


In regards to the fine tune of parameter and comparing these to the competition results, we can see where our final score comes from when watching the video. In the upper left hand corner we can see three different metrics.
- The first is Impact Boxes Accuracy. This is measuring the accuracy of the system detecting the correct impacts. This is calculated and incremented frame by frame throughout the entirery of the video. The total number at the end of the video is calculated by the number of times we see the helmet box light up red throughout the video. We say that the impact is accuract when we see the box turn yellow. 
- The second is Non-Impact Boxes Accuracy. This number is much higher as the algorithm is incrementing and counting every helmet boxes on every single frame and computing the accuracy of this. When I say accuracy, you can see in even before starting the video the boxes around each helmet. You will also notice that some boxes are green and some are white. The green boxes are confidant in the accuracy and therefore help contribute to overall number. When looking at the video before starting it, we can see that there are 6 green helmets, and 22 total helmet boxes, which gives us the starting Non-Impact Boxes Accuracy of 6/22.
- The third is Weighted Accuracy. This final number is the combination of the two prior and is the number that is output earlier in the algorithm when we are looking at fine tuning our paramters.


### PowerPoint Presentation
Attached above is the powerpoint presentation made to quickly encapsulate the results of this sprint. 
