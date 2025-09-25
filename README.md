# Heart-Detector-Classifier
A model that can identify the position of the heart based on chest X-rays

Here I wanted to use publicly available labelled chest x ray data, and train a pytorch model to be able to identify the position of the heart from unseen data. For more detail, please see the code book :)

The main thing I discovered was that adjusting the Learning Rate can make a dramatic difference. By reducung the LR by a factor of ten, this vastly decreased the MSE (val loss), meaning that the 2nd model was much better at identifying the position of the heart.

I showed the power of using models on medical imaging, but in the future I could do the following to improve the work:

Data and Augmentation 📊
Gather More Data: I could focus on increasing the size of my training dataset to help my model generalise better to unseen X-rays.

Diversify Augmentation: I could experiment with advanced techniques like Elastic Deformations to mimic real-world image distortions. I could also introduce more variation in brightness and contrast (Intensity/Contrast Changes) to make my model robust against different machine settings.

Check Data Quality: I could review the existing heart bounding box annotations, especially for images that were challenging. Cleaning up noisy labels could be a fast way to reduce error.

Model Architecture and Loss Function 🧠
Upgrade the Base Model: I could try replacing my current backbone with a more powerful, pre-trained network like ResNet or EfficientNet.

Change the Loss Function: Instead of relying solely on MSE for bounding box coordinates, I could switch to a loss function that's a better fit for object localisation. I could test L1 (Mean Absolute Error), which is less sensitive to big outliers, or even implement IoU (Intersection over Union) Loss, as it directly measures the quality of the predicted box overlap.

Sources:
Datasets: https://www.rsna.org/rsnai/ai-image-challenge/rsna-pneumonia-detection-challenge-2018
