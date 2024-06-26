
# Comment Installer TightVNC sur un ordinateur client et sur un serveur.

## *-OPTIONNEL-* Préparation de la VM sur Proxmox (Serveur et Client) 

### Partie Client et Serveur

- [Télécharger l'ISO de Windows 10](https://www.microsoft.com/fr-fr/software-download/windows10/) : Allez sur le site officiel de Microsoft pour télécharger l'ISO de Windows 10.

- [Télécharger l'ISO de Windows Server 2022](https://www.microsoft.com/en-us/evalcenter/evaluate-windows-server-2022) : Allez sur le site officiel de Microsoft pour télécharger l'ISO de Windows Server 2022.

- Ouvrez Proxmox.

- Ayez un compte utilisateur avec les droits nécessaires pour créer des VM sur Proxmox.

### Création de la VM Windows 10 ou Windows Server 2022 sur Proxmox

#### 1. Télécharger l'ISO sur Proxmox

- Connectez-vous à l'interface web de Proxmox.
- Accédez à `Datacenter` > `pve` (votre nœud Proxmox) > `Disques locaux` (par exemple, `local` ou `local-lvm`).
- Cliquez sur l'onglet `Content` puis sur `Upload`.
- Sélectionnez l'image ISO de Windows 10 (client) ou Windows Server 2022 (serveur) et téléchargez-la.

#### 2. Créer une nouvelle VM

- Dans l'interface web de Proxmox, cliquez sur le nœud où vous voulez créer la VM.
- Cliquez sur `Create VM` dans le coin supérieur droit.
  - **General** :
    - Donnez un nom à votre VM.
  - **OS** :
    - Sélectionnez le stockage où se trouve votre ISO et choisissez l'ISO de Windows 10 ou Windows Server 2022.
    - Choisissez `Microsoft Windows` comme type d'OS.
  - **System** :
    - Gardez les paramètres par défaut ou ajustez selon vos besoins.
  - **Hard Disk** :
    - Sélectionnez le stockage et configurez la taille du disque virtuel (par exemple, 60GB ou plus selon vos besoins).
  - **CPU** :
    - Définissez le nombre de sockets et de cœurs selon les ressources disponibles.
  - **Memory** :
    - Allouez la mémoire (par exemple, 4096 MB pour 4GB de RAM).
  - **Network** :
    - Configurez l'interface réseau (généralement, le mode par défaut `virtio` fonctionne bien).

#### 3. Démarrer la VM et installer Windows 10 ou Windows Server 2022

- Sélectionnez la VM nouvellement créée dans le volet de gauche.
- Cliquez sur `Start` pour démarrer la VM.
- Cliquez sur `Console` pour accéder à la console de la VM.
- Suivez les étapes de l'assistant d'installation de Windows 10 ou Windows Server 2022.
  - Choisissez la langue, le format de l'heure, et la méthode de clavier.
  - Cliquez sur `Install Now`.
  - Entrez la clé de produit si nécessaire.
  - Sélectionnez la version de Windows 10 ou Windows Server 2022 à installer.
  - Acceptez les termes de licence.
  - Choisissez `Custom: Install Windows only (advanced)`.
  - Sélectionnez le disque et cliquez sur `Next` pour installer Windows 10 ou Windows Server 2022.

#### 4. Finaliser l'installation de Windows 10 ou Windows Server 2022

- Complétez l'installation de Windows Server en suivant les instructions à l'écran.
- Configurez les paramètres initiaux, tels que le mot de passe administrateur.

## Partie Client : Installation de TightVNC et désactivation du Pare-feu

### Étape 1 : Configuration et Installation de TightVNC

1. [Télécharger TightVNC](https://www.tightvnc.com/download.php) : Téléchargez la dernière version de TightVNC pour Windows 
   
   ![TightVNC](images/Installation_TightVNC_1.png)

2. Cliquez sur `Next`.

   ![TightVNC](images/Installation_TightVNC_2.png)

3. Acceptez les règles et cliquez sur `Next`.

   ![TightVNC](images/Installation_TightVNC_3.png)

4. Cliquez sur `Custom`.

   ![TightVNC](images/Installation_TightVNC_4.png)

5. Cliquez sur `TightVNC server` et sélectionnez `Entire feature will be unavailable`.

   ![TightVNC](images/Installation_TightVNC_5.png)

6. Cliquez sur `Next`.

   ![TightVNC](images/Installation_TightVNC_6.png)

7. Cliquez sur `Next`.

   ![TightVNC](images/Installation_TightVNC_7.png)

8. Cliquez sur `Install`.

   ![TightVNC](images/Installation_TightVNC_8.png)

9. Cliquez sur `Finish`.

   ![TightVNC](images/Installation_TightVNC_9.png)

### Étape 2: Désactiver le Pare-feu

   ![TightVNC](images/pare_feu_client.png)

- **Note : Il est nécessaire de faire cela afin que l'administrateur (ou celui qui vous aide) puisse contrôler à distance votre PC.**

#### Voilà, tout est installé pour la partie client ! Si vous avez besoin d'installer TightVNC sur votre serveur, il y a l'explication dans la suite du tuto !

## Partie Serveur - Installation de TightVNC sur Windows Server 2022

### Étape 3: Configuration et Installation de TightVNC

1. [Télécharger TightVNC](https://www.tightvnc.com/download.php) : Téléchargez la dernière version de TightVNC pour Windows 
   
   ![TightVNC](images/Installation_TightVNC_1.png)

2. Cliquez sur `Next`.

   ![TightVNC](images/Installation_TightVNC_2.png)

3. Acceptez les règles et cliquez sur `Next`.

   ![TightVNC](images/Installation_TightVNC_3.png)

4. Cliquez sur `Custom`.

   ![TightVNC](images/Installation_TightVNC_4.png)

5. Cliquez sur `TightVNC server`.

   ![TightVNC](images/Installation_TightVNC_11.png)

6. Cliquez sur `Next`.

   ![TightVNC](images/Installation_TightVNC_11.png)

7. Cliquez sur `Next`.

   ![TightVNC](images/install_server.png)

8. Cliquez sur `Oui`.

   ![TightVNC](images/install_server1.png)

9. **Le premier mot de passe va permettre de sécuriser la prise de contrôle à distance sur ce poste. Chaque client VNC souhaitant s’y connecter devra connaître ce mot de passe ;**

   **Le second permet de sécuriser le comportement et la configuration de TightVNC sur ce poste. Chaque modification dans la configuration ou l’exécution du serveur TightVNC devra être confirmée avec ce mot de passe.**

   ![TightVNC](images/Installation_TightVNC_10.png)

   **Nous allons vérifier si l'installation s'est bien effectuée !**

- Normalement, vous devriez voir une icône de VNC dans la barre des tâches et dans les raccourcis Windows.

   ![TightVNC](images/install_server3.png)

   ![TightVNC](images/install_server4.png)

- De plus, si vous avez choisi l'option d'installation de TightVNC en tant que service, vous trouverez la ligne correspondante dans le menu des services de Windows, comme suit :

   ![TightVNC](images/install_server5.png)

### Étape 4: Désactiver le Pare-feu

   ![Pare_Feu](images/Pare_feu_server.png)

- **Note : Il est nécessaire de faire cela afin de pouvoir ouvrir les ports 5800 et 5900 pour pouvoir contrôler à distance les ordinateurs clients.**

#### Voilà, tout est installé. Normalement, si vous avez suivi toutes les étapes, vous avez réussi votre installation de TightVNC sur un serveur !








  


