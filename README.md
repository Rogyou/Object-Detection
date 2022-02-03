# Object-Detection

We have based our model on the research paper 
You Only Look Once:
Unified, Real-Time Object Detection
Joseph Redmon∗
, Santosh Divvala∗†, Ross Girshick¶
, Ali Farhadi∗†

![image](https://user-images.githubusercontent.com/79264195/152377632-6a33515e-988e-4c64-9da5-a176a7390922.png)

YOLOv3 is extremely fast and accurate. In mAP measured at .5 IOU YOLOv3 is on par with Focal Loss but about 4x faster. Moreover, you can easily tradeoff between speed and accuracy simply by changing the size of the model, no retraining required!

Prior detection systems repurpose classifiers or localizers to perform detection. They apply the model to an image at multiple locations and scales. High scoring regions of the image are considered detections.

We use a totally different approach. We apply a single neural network to the full image. This network divides the image into regions and predicts bounding boxes and probabilities for each region. These bounding boxes are weighted by the predicted probabilities.

![image](https://user-images.githubusercontent.com/79264195/152377827-2c418752-9166-476b-bc57-a2fff145592e.png)

Our model has several advantages over classifier-based systems. It looks at the whole image at test time so its predictions are informed by global context in the image. It also makes predictions with a single network evaluation unlike systems like R-CNN which require thousands for a single image. This makes it extremely fast, more than 1000x faster than R-CNN and 100x faster than Fast R-CNN. See our paper for more details on the full system.
