## Partie Client : Installation de TightVNC et désactivation de pare-feu


## Étape 1 : Configuration et Installation de TightVNC

1. [Télécharger TightVNC](https://www.tightvnc.com/download.php) : Téléchargez la dernière version de TightVNC pour Windows 
   
   ![TightVNC](images/Installation_TightVNC_1.png)

2. Cliquez sur `Next`.

  ![TightVNC](images/Installation_TightVNC_2.png)

3. Acceptez les règles et cliquez sur `Next`.

  ![TightVNC](images/Installation_TightVNC_3.png)

4. Cliquez sur `Custom`.

  ![TightVNC](images/Installation_TightVNC_4.png)

5. Cliquez sur `TightVNC server`* et selectionner `Entire feature will be unavailable`.

   ![TightVNC](images/Installation_TightVNC_5.png)

6. Cliquez sur `Next`.

   ![TightVNC](images/Installation_TightVNC_6.png)

7. Cliquez sur `Next`.

   ![TightVNC](images/Installation_TightVNC_7.png)

8. Cliquez sur `Install`.

   ![TightVNC](images/Installation_TightVNC_8.png)

9. Cliquez sur `Finish`.

   ![TightVNC](images/Installation_TightVNC_9.png)

## Étape 2: Désactiver les pare feux 
  
  ### Désactiver les pare-feux :

   ![TightVNC](images/pare_feu_client.png)

## Partie Serveur - Installation de Windows Server 2022 avec TightVNC et une connexion SSH 

### Étape 1 : Préparation

1. [Télécharger l'ISO de Windows Server 2022](https://www.microsoft.com/en-us/evalcenter/evaluate-windows-server-2022) : Allez sur le site officiel de Microsoft pour télécharger l'ISO de Windows Server 2022.
2. Ouvrir Proxmox
3. Ayez un compte utilisateur avec les droits nécessaires pour créer des VM sur Proxmox

### Étapes 2 : Création de la VM Windows Server 2022


#### 1. Télécharger l'ISO sur Proxmox

- Connectez-vous à l'interface web de Proxmox.
- Accédez à `Datacenter` > `pve` (votre nœud Proxmox) > `Disques locaux` (par exemple, `local` ou `local-lvm`).
- Cliquez sur l'onglet `Content` puis sur `Upload`.
- Sélectionnez l'image ISO de Windows Server 2022 et téléchargez-la.

#### 2. Créer une nouvelle VM

- Dans l'interface web de Proxmox, cliquez sur le nœud où vous voulez créer la VM.
- Cliquez sur `Create VM` dans le coin supérieur droit.
- **General** :
  - Donnez un nom à votre VM.
- **OS** :
  - Sélectionnez le stockage où se trouve votre ISO et choisissez l'ISO de Windows Server 2022.
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

#### 3. Démarrer la VM et installer Windows Server 2022

- Sélectionnez la VM nouvellement créée dans le volet de gauche.
- Cliquez sur `Start` pour démarrer la VM.
- Cliquez sur `Console` pour accéder à la console de la VM.
- Suivez les étapes de l'assistant d'installation de Windows Server 2022.
  - Choisissez la langue, le format de l'heure, et la méthode de clavier.
  - Cliquez sur `Install Now`.
  - Entrez la clé de produit si nécessaire.
  - Sélectionnez la version de Windows Server 2022 à installer.
  - Acceptez les termes de licence.
  - Choisissez `Custom: Install Windows only (advanced)`.
  - Sélectionnez le disque et cliquez sur `Next` pour installer Windows Server 2022.

#### 4. Finaliser l'installation de Windows Server 2022

- Complétez l'installation de Windows Server en suivant les instructions à l'écran.
- Configurez les paramètres initiaux, tels que le mot de passe administrateur.

## Étape 3: Configuration et Installation de TightVNC

1. [Télécharger TightVNC](https://www.tightvnc.com/download.php) : Téléchargez la dernière version de TightVNC pour Windows 
   
   ![TightVNC](images/Installation_TightVNC_1.png)

2. Cliquez sur `Next`.

  ![TightVNC](images/Installation_TightVNC_2.png)

3. Acceptez les règles et cliquez sur `Next`.

  ![TightVNC](images/Installation_TightVNC_3.png)

4. Cliquez sur `Custom`.

  ![TightVNC](images/Installation_TightVNC_4.png)

5. Cliquez sur `TightVNC server` 

   ![TightVNC](images/Installation_TightVNC_11.png)

6. Cliquez sur `Next`.

   ![TightVNC](images/Installation_TightVNC_11.png)

7. Cliquez sur `Next`.

   ![TightVNC](images/Installation_TightVNC_7.png)

8. Cliquez sur `Install`.

   ![TightVNC](images/Installation_TightVNC_8.png)

9. Cliquez sur `Finish`.

   ![TightVNC](images/Installation_TightVNC_9.png)



## Étape 5: Désactiver les pare feux ou ouvrir les ports VNC (5800 et 5900) dans Windows Defender
  
  ### Solution 1 Désactiver les pare-feux :

 - Désactiver les pare-feux
   
     ![Pare_Feu](images/Pare_feu_server.png)
   
  ### Solution 2 : Ouvrir les ports VNC (5800 et 5900) dans Windows Defender
  
  #### 1. Ouvrir le Pare-feu Windows Defender avec sécurité avancée

  - Appuyez sur les touches `Windows + R` pour ouvrir la boîte de dialogue "Exécuter".
  - Tapez `wf.msc` et appuyez sur `Entrée`.
  
     ![Pare_Feu](images/Pare_feu1.png)
 
  #### 2. Ajouter une nouvelle règle pour le port 5800

  - Dans le volet de gauche, cliquez sur `Règles de trafic entrant`.

  - Dans le volet de droite, cliquez sur `Nouvelle règle...`.

     ![Pare_Feu](images/Pare_feu2.png)
 
  - Sélectionnez `Port` et cliquez sur `Suivant`.

      ![Pare_Feu](images/Pare_feu3.png)

  - Choisissez `TCP` et sélectionnez `Ports locaux spécifiques`. Entrez `5800` dans le champ et cliquez sur `Suivant`.

      ![Pare_Feu](images/Pare_feu4.png)
    
  - Sélectionnez `Autoriser la connexion` et cliquez sur `Suivant`.

      ![Pare_Feu](images/Pare_feu5.png)
    
  - Cochez les cases selon votre profil de réseau (`Domaine`, `Privé`, `Public`) et cliquez sur `Suivant`.

     ![Pare_Feu](images/Pare_feu6.png)
 
  - Donnez un nom à la règle, par exemple `Ouvrir Port 5800`, et cliquez sur `Terminer`.
    
     ![Pare_Feu](images/Pare_feu7.png)

  #### 3. Répéter pour le port 5900

  - Répétez les mêmes étapes que pour le port 5800, mais entrez `5900` à la place de `5800`.
  - Nommez la règle `Ouvrir Port 5900`.

   






  


