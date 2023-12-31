
Lip Reading Recognition Technology helps one to transmit information without using vocal cords. This technology uses Lip Tracking which is a biometric system, it works based on a genuine system that can be developed using different levels of video processing.

The dataset that we’ll use for this project consists of ~1000 utterances of 500 different words, spoken by one speaker. All videos are 29 frames in length, and the word occurs in the middle of the video. The frames will be cropped around the speaker’s mouth and downsized to 64x64.

One of the most important, but also time-consuming aspect of this project was setting up a good data pipeline. Given the fact that the dataset couldn’t fit in memory, the performance of the pipeline was very important : at every iteration, it needed to fetch a batch of training examples from the disk, apply pre-processing on it, data-augmentation, and finally feed it to the neural network. To achieve that I chose to use TensorFlow's data input pipeline. It allow us to do everything mentioned above, but also to achieve a peak level of performance by using the CPU and GPU at the same time. As a result, the data for the next step is ready before the current step has finished.

