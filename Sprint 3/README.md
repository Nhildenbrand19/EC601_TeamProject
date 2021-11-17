## Sprint 3
Code attached above along with link to Google slides showing progress for this sprint

[Sprint 3 Presentation](https://docs.google.com/presentation/d/1dCgd4TxupJAoRieBpMOObiLBWHdd4vvuOeNafCRvWtg/edit#slide=id.gfd79c3bad8_0_63)

### Why DeepSort?
- The use of deep learning to track objects in video
- In the machine learning community, this is the problem of Multi-Object tracking
- Utilizes object detection and tracking detection box across frames
- This steps through each frame in a video and applies the deepsort algorithm to then cluster helmets across frames when it is the same helmet
- We can then group each of these clusters and pick the most common label for that cluster

### Fine Tuning of Test Parameters
Default Parameters
  - Score before = 0.31913
  - Score after DeepSort = 0.53862

Fine Tuned Parameters
  - Score before = 0.31913
  - Score after DeepSort = 0.68594


### Output of Video Frames

![Endzone3](https://user-images.githubusercontent.com/74614080/141796977-aa544db8-5b81-4c72-b531-a3479f4621f3.png)

![Sideline3](https://user-images.githubusercontent.com/74614080/141796993-5ebe7d21-4c0e-4c30-8dbe-72e94383e565.png)


We can see from two different clips, one being from an endzone view, and the other being from a sideline view, that our algorithm is correctly identifying helmets.
