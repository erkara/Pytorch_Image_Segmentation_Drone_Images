# Pytorch_Image_Segmentation_Drone_Images

1. I would like to present an image segmentation application on drone images dataset on [here]((https://www.tugraz.at/index.php?id=22387)). Dataset contains 600 drone images acquired 
at an altitude of 5 to 30 meters above ground with masks concerning 23 classes. RGB masks are also provides. 
2. Task is to train an algorirtm to accurately predict the segmentation of each classes. I would like to present two different models here;
3. Part1: I trained Unet, which is probably the most well-known arhitecture, from scratch. Have a look at the original paper [here](https://arxiv.org/abs/1505.04597).
4. Part2: I worked on three different pretrained arhitectures Unet++, Linknet and DeepLabV3+ with and without freezing the models. Details and more models can be found in [Segmentation Models Github](https://github.com/qubvel/segmentation_models.pytorch). 
5. Here are the scoes for both models;
- Part1: **intesection-over-union-score: 0.21 pixel_accuracy: 0.71**:
- Part2: **intesection-over-union-score: 0.47 pixel_accuracy: 0.84**

- Hyperparameter optimization is performed with [Optuna](https://optuna.org/) library. It allows us to quickly identify the optimal hyperparamters resulting the best model. Besides from searching the optimal parameters in hyperparamater space, Optuna also provides several early stopping strategies to prune unpromising trials earlier to save the training time. In each notebook, I detailed the training stages clearly.
- Intersction-Over-Union is used as a cost function in training to better handle the low frequency classes.
- Data augmentation is performed via [Albumentation](https://albumentations.ai/) library. You may be used to torchvision but Albumentation is faster and more versatile. 
- In order to speep-up the training, resizing was performed before training. I realized that this step is usually overlooked in many application. However, resizing is a big bottlenect significantly increasing the training time. 
- I greatly benefited from [Aladdin Persson](https://www.youtube.com/watch?v=IHq1t7NxS8k&list=LL&index=7&t=1738s), [Abhishek Thakur](https://www.youtube.com/watch?v=u1loyDCoGbE&list=LL&index=5) and [Amirhossein Heydarian ](https://github.com/amirhosseinh77/UNet-AerialSegmentation/blob/main/losses.py).
- Please let me know if you have any feedback!
