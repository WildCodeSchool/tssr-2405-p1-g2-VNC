## Installation de Windows Server 2022 avec TightVNC et une connexion SSH


### Étape 1 : Préparation

1. [Télécharger l'ISO de Windows Server 2022](https://www.microsoft.com/en-us/evalcenter/evaluate-windows-server-2022) : Allez sur le site officiel de Microsoft pour télécharger l'ISO de Windows Server 2022.
2. [Télécharger VirtualBox](https://www.virtualbox.org/wiki/Downloads) : Télécharger et Installer VirtualBox : Téléchargez VirtualBox depuis VirtualBox.org et installez-le. 

### Étape 2 : Création de la VM

1. **Création de la VM :**

   - Ouvrez VirtualBox et cliquez sur "New".
   - Nom : Windows Server 2022.
   - Type : Microsoft Windows.
   - Version : Windows 2022 (64-bit).
   - Mémoire : Attribuez au moins 2048 Mo (2 Go).
   - Disque Dur : Créez un nouveau disque virtuel (VDI) avec une taille dynamique, minimum 50 Go.

2. **Configuration de la VM :**

   - Sélectionnez votre VM et cliquez sur "Settings".
   - Storage : Sous "Controller: IDE", ajoutez le fichier ISO de Windows Server 2022.
   - Network : Configurez l'adaptateur réseau en mode "Bridged" ou "NAT" selon vos besoins.

### Étape 3: Installation de Windows Server 2022

1. **Démarrage de la VM :** Cliquez sur "Start" pour démarrer la VM avec l'ISO. Suivez les instructions pour installer Windows Server 2022, en choisissant les options par défaut à moins que vous ayez des préférences
   spécifiques.
   
[Vidéo Tuto comment installer Tight VNC sur Windows Server 2022](https://openclassrooms.com/fr/courses/1733046-prenez-le-controle-a-distance-dun-poste-linux-windows-avec-vnc/5576651-installez-tightvnc-sous-windows-et-linux#/id/video_Player_2)
### Étape 4: Configuration et Installation de TightVNC

1. [Télécharger TightVNC](https://www.tightvnc.com/download.php) : Téléchargez TightVNC pour Windows et installez-le sur votre Windows Server 2022.
2. **Configuration de TightVNC :** Lors de l'installation, configurez un mot de passe pour l'accès VNC. Assurez-vous que TightVNC démarre avec le système.
3. **Ouverture du Port VNC dans le Pare-feu :** Ouvrez le pare-feu Windows Defender. Ajoutez une règle pour autoriser les connexions entrantes sur le port 5900 (port par défaut pour VNC).

### Étape 5: Configuration de TightVNC 

1. **Configurer TightVNC pour démarrer automatiquement :** Une fois l'installation terminée, assurez-vous que TightVNC est configuré pour démarrer automatiquement avec le système. Vous pouvez généralement trouver cette option dans les paramètres de démarrage ou de services de Windows.

2. **Configurer le mot de passe VNC :** Lors du premier démarrage de TightVNC, vous serez invité à définir un mot de passe pour l'accès VNC. Assurez-vous de choisir un mot de passe sécurisé et de le garder en sécurité.

3. **Tester la connexion VNC :** Avant de passer à la prochaine étape, assurez-vous de tester la connexion TightVNC en utilisant le client VNC depuis une machine distante. Assurez-vous que vous pouvez vous connecter au serveur Windows Server 2022 à l'aide du nom d'utilisateur et du mot de passe que vous avez configurés.

### Étape 6: Configuration de la connexion SSH

1. **Vérifier la disponibilité de SSH :** Assurez-vous que le service SSH est en cours d'exécution sur votre serveur Windows Server 2022. Vous pouvez le vérifier en recherchant le service "OpenSSH SSH Server" dans la liste des services Windows.

2. **Configurer les autorisations SSH :** Si nécessaire, configurez les autorisations SSH pour permettre la connexion à distance en utilisant des clés SSH ou des identifiants de connexion.

3. **Testez la connexion SSH :** Utilisez un client SSH tel que PuTTY ou OpenSSH pour vous connecter à votre serveur Windows Server 2022. Assurez-vous que la connexion fonctionne correctement en vous connectant avec les identifiants appropriés.





  


