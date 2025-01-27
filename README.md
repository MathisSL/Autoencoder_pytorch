# Autoencoder pytorch

Le but de l'**autoencoder** et d'encoder les données ou l'image, c'est à dire diminuer la taille afin d'obtenir une représentation de dimension inférieur, dans un espace latent.
L'objectif de l'encodeur est de capturer les caractéristiquesles plus importantes des données.

Le **decodeur** va à partir de cette représentation latente, reconstruire l'image ou les données d'origines.
Les informations étant diminuées, on garde juste les caractéristique les plus importantes.

## Les autoencodeur sont utiles pour :
- **La reduction de dimension** tout en préservant les informations essentielles.
  Celà va permettre de passer par exemples des images encodées dans un réseau de neurone afin de diminuer au        maximum le coût calculatoire puis de la reconstruire à partir du decodeur.
  Similaire au PCA (Principal Component Analysis) mais peut captuer des relations non-linéaire.
  
- **Détection d'anomalies** : Identifie les valeurs abérantes en comparent la fonction de perte de reconstruction.

- **Traitement d'image** : Génération d'image, inpainting (retouche d'image, consiste à restaurer les zones         manquantes ou endommagées d'une image à l'aide des informations des pixels environnants), super-resolution        (consiste à améliorer la résolution spatiale, c'est-à-dire le niveau de détail, d'une image ou d'un système       d'acquisition).

- Dénormalisation d'image : **Nettoyer les données bruitées**, on peut aussi utiliser un filtre de Kalmann          (données), ils sont appelés Denoising Autoencoder. 

-  **Compréssion de données** : Obtenir des formats plus compacts.

-  **Génération de données** : Les Variational Autoencodeurs permettent de générer de nouvelles données              similaires aux données d'entraînement.


## Types d'autoencoder :
- **Vanilla Autoencoder**: The simplest form.

- **Denoising Autoencoder**: Learns to reconstruct clean input from noisy input.

- **Sparse Autoencoder**: Adds a sparsity constraint to force the model to learn more compact representations.

- **Convolutional Autoencoder**: Specialized for image data, using convolutional layers.

- **Variational Autoencoder (VAE)**: A probabilistic autoencoder used for generative tasks.

- **Sequence-to-Sequence Autoencoder**: Processes sequential data like text or time series.


## Structure d'un autoencoder :

Input layer: The raw data.
Hidden layers:

  Encoder layers reduce the dimensionality of the input.
  The bottleneck layer is the smallest dimension, representing the latent space.
  Decoder layers expand the latent representation back to the original dimensions.

Output layer: The reconstructed data.

![autoencoder_img](https://github.com/user-attachments/assets/560da686-c524-4d8c-95ff-91d178e3e715)
 
## Loss Function
The loss function measures the difference between the input and the reconstructed output, typically using:

- Mean Squared Error (MSE) for continuous data.
- Binary Cross-Entropy (BCE) for binary or probabilistic outputs.

# Super résolution autoencoder$
Pour le projet, j'ai décider d'entraîner un autoencoder permettant d'améliorer la qualité des images.

Pour cela, nous allons utiliser l'architecture du SRCNN de https://arxiv.org/pdf/1501.00092v3
<img width="556" alt="SRCNN_architecture" src="https://github.com/user-attachments/assets/2523e7cf-8cf7-469a-9801-2450c8baf1b8" />

Figure 1 shows the different kernels/filters of the SRCNN architecture. You can see that there are three layers.
Figure 2 shows the patch extraction process that is done by the SRCNN model.

There are three convolutional layers in the SRCNN model. We apply the ReLU activation to the first two convolutional layers only.*

## Le débruitage d’images par patchs :









