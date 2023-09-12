# Unpaired-Image-to-Image-Translation
Unpaired image-to-image translation methods aim at learning a mapping of images from a source domain to a target domain without the need of paired images from the two domains to train on.  
Recently, these methods proved to be very useful in biological applications to display subtle phenotypic cell variations otherwise invisible to the human eye.

In this project , I've translated real photos into Monet-style art and vice-versa using Cycle-Gan architecture.
### Dataset from:
https://www.kaggle.com/competitions/gan-getting-started/data  
https://www.kaggle.com/datasets/dimitreoliveira/monet-tfrecords-256x256  
Monet images : 1367  
Photo images : 7038
## Cycle-Gan Architecture  
Paper: https://arxiv.org/abs/1703.10593  
![Screenshot 2023-08-14 0953462](https://github.com/Kytamnh/Unpaired-Image-to-Image-Translation/assets/127836327/59381f28-4a33-4de8-950a-8c95f700acee)  
We have generator networks and discriminator networks working against each other. The generator tries to produce samples from the desired distribution and the discriminator tries to predict if the sample is from the actual distribution or produced by the generator. The generator and discriminator are trained jointly. The effect this has is that eventually the generator learns to approximate the underlying distribution completely and the discriminator is left guessing randomly.
## Generator
![Screenshot 2023-08-14 1009381](https://github.com/Kytamnh/Unpaired-Image-to-Image-Translation/assets/127836327/657ecea7-d1be-4881-9467-332a675aa480)  
1. Generators must make the discriminators approve all the generated images, so as to fool them.
2. The generated image must retain the property of original image, so if we generate a fake image using a generator say  GeneratorA→B
   then we must be able to get back to original image using the another generator  GeneratorB→A, i.e,it must satisfy cyclic-consistency.
3. Feeding an image from a domain into generator of same domain must reproduce an identical image.

## Discriminator  
![Screenshot 2023-08-14 1033331](https://github.com/Kytamnh/Unpaired-Image-to-Image-Translation/assets/127836327/a1cc7b8a-05a6-4b43-87d4-3e1699571785)  
1. Discriminator must approve all the original images of the corresponding categories.
2. Discriminator must reject all the images which are generated by corresponding Generators to fool them.











