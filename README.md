# Autoencoder_pytorch

Le but de l'**autoencoder** et d'encoder les données ou l'image, c'est à dire diminuer la taille afin d'obtenir une représentation de dimension inférieur, dans un espace latent.
L'objectif de l'encodeur est de capturer les caractéristiquesles plus importantes des données.

Le **decodeur** va à partir de cette représentation latente, reconstruire l'image ou les données d'origines.
Les informations étant diminuées, on garde juste les caractéristique les plus importantes.

## Les autoencodeur sont utiles pour :
- **La reduction de dimension** tout en préservant les informations essentielles.
  Celà va permettre de passer par exemples des images encodées dans un réseau de neurone afin de diminuer au        maximum le coût calculatoire puis de la reconstruire à partir du decodeur.
  Similaire au PCA mais peut captuer des relations non-linéaire.
- **Détection d'anomalies** : Identifie les valeurs abérantes en comparent la fonction de perte de reconstruction.
- **Traitement d'image** : Génération d'image, inpainting (retouche d'image, consiste à restaurer les zones         manquantes ou endommagées d'une image à l'aide des informations des pixels environnants), super-resolution        (consiste à améliorer la résolution spatiale, c'est-à-dire le niveau de détail, d'une image ou d'un système       d'acquisition).
- Dénormalisation d'image : **Nettoyer les données bruitées**, on peut aussi utiliser un filtre de Kalmann          (données), ils sont appelés Denoising Autoencoder. 
-  **Compréssion de données** : Obtenir des formats plus compacts.
-  **Génération de données** : Les Variational Autoencodeurs permettent de générer de nouvelles données              similaires aux données d'entraînement.

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
        Mean Squared Error (MSE) for continuous data.
        Binary Cross-Entropy (BCE) for binary or probabilistic outputs.





