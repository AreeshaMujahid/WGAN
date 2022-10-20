# WGAN
Wasserstein GAN

There are few problems with simple GAN.
• The training time of discriminator is very long because to train the discriminator
where discriminator can be fooled is not so easy and takes hours to find that
point.
• The abrupt loss function of generator and discriminator gives no information.
To solve the above problems WGAN was developed where the discriminator model
weights are clipped in the range of [-1,1] this is done to reduce the time of training.
In WGAN the discriminator is replaced by critic which works in the same way as
discriminator but the discriminator is trained 5 times for each generator training.
This modification is motivated by the theoretical argument that aim of generator
training is to reduce the distance between the distribution of authentic data and
distribution of fake data.

The pros of WGAN is that the training process is more stable and less sensitive to the
model architecture and the choice of hyperparameter configurations. Perhaps most
importantly, the loss of the discriminator appears to be related to the quality of the
images produced by the generator.
Perhaps most importantly, discriminator loss is related to the quality of the images
produced by the generator. The less critic loss in evaluating the generated image, the
higher the expected quality of the generated image. This is important because, unlike
other his GANs, which aim for stability in the sense of finding a balance between the
two models, WGAN aims for convergence and reduces generator losses.
Since there is no WGAN clipping, we can apply the Lipschitz constraint to the Critical
model and compute the Wasserstein distance. The difficulty with WGAN is enforcing
the Lipschitz constraint. Trimming is easy, but it presents some challenges. The model
can still produce poor quality images and fail to converge, especially if the
hyperparameter c is not set properly. Weight loss works like weight control. It reduces
model capacity and limits the ability to model complex functions
