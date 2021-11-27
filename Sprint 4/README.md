## Sprint 4

The goals for Sprint 4 are as follows

- Feed our algorithm other data to see the results

- Continue to fine tune parameters and compare to competition results

- Begin working towards or completing the combination of  individual frames to create final video


### Results
We can see below the output of our algorithm and confirmation that the we have successfully combined the individual frames from the previous sprint to create a video analysis. 


https://user-images.githubusercontent.com/74614080/143662721-2df2eeb9-f91d-4f69-982c-bcbe17d2e474.mp4


In regards to the fine tune of parameter and comparing these to the competition results, we can see where our final score comes from when watching the video. In the upper left hand corner we can see three different metrics.
- The first is Impact Boxes Accuracy. This is measuring the accuracy of the system detecting the correct impacts. This is calculated and incremented frame by frame throughout the entirery of the video.
- The second is Non-Impact Boxes Accuracy. This number is much higher as the algorithm is incrementing and counting every helmet boxes on every single frame and computing the accuracy of this. 
- The third is Weighted Accuracy. This final number is the combination of the two prior and is the number that is output earlier in the algorithm when we are looking at fine tuning our paramters.
