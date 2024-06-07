# Vue d'Ensemble du Système TightVNC

## Guide Utilisateur :

- Instructions pour installer et configurer le client VNC.
- Procédure pour se connecter au serveur de manière sécurisée.

TightVNC se présente comme une application puissante et flexible dédiée au contrôle à distance des ordinateurs. En qualité de solution de prise en main à distance, elle offre une interface conviviale et s'accorde parfaitement avec divers systèmes d'exploitation. Cet outil se révèle particulièrement précieux pour les administrateurs système, les équipes de support technique, ainsi que les utilisateurs cherchant à accéder à leurs ordinateurs de manière sécurisée et efficiente, où qu'ils se trouvent.

## Vue d'Ensemble du Système et Objectif 

Le système TightVNC repose essentiellement sur deux composants majeurs : le serveur TightVNC et le client TightVNC. Le serveur TightVNC trouve sa place sur l'ordinateur objet du contrôle, tandis que le client TightVNC est employé pour y accéder à distance. L'objectif principal de TightVNC consiste à faciliter la gestion et la surveillance distantes des systèmes informatiques, tout en assurant une connexion stable et sécurisée dès le démarrage du système.

### Objectifs Principaux: 

- **Faciliter l'Administration à Distance** : TightVNC permet aux administrateurs système de surveiller, gérer et dépanner les ordinateurs à distance, réduisant ainsi les temps d'arrêt et les interventions physiques requises. 

- **Renforcer la Sécurité** : Par le biais de la personnalisation des paramètres de sécurité, les administrateurs peuvent garantir que les connexions à distance sont protégées contre tout accès non autorisé. 

- **Améliorer l'Efficacité** : En offrant la possibilité de gérer plusieurs systèmes depuis une seule interface, TightVNC optimise le temps et les ressources nécessaires à la gestion des infrastructures informatiques. 

En suivant scrupuleusement les étapes détaillées dans ce guide, vous serez en mesure de configurer et utiliser TightVNC de manière efficace pour répondre à vos besoins spécifiques de contrôle à distance, assurant ainsi une gestion fluide et sécurisée de vos systèmes informatiques.

Lorsque le service TightVNC est enregistré et lancé, vous pouvez contrôler son état en suivant les indications ci-dessous :

## Étape 1 : Utilisation du Client TightVNC

Pour accéder à votre serveur TightVNC, veuillez suivre les directives ci-dessous avec attention :

### Procédure :

1. **Lancement du Client TightVNC** : Démarrez l'application Client TightVNC sur votre ordinateur. L'interface affichée devrait être similaire à celle-ci :

![](https://github.com/WildCodeSchool/tssr-2405-p1-g2-VNC/blob/main/images/vnc-prise-main-distance-TightVNC.png)

2. **Dans le champ "Remote Host", entrez l'adresse IP ou le nom de domaine du serveur auquel vous souhaitez vous connecter.

3. **Si un port spécifique est nécessaire, assurez-vous d'utiliser la syntaxe adéquate en choisissant entre ces deux options :
    - `"Nom-de-domaine::port"` (si un nom de domaine est utilisé)
    - `"IPv4::port"` (en cas d'utilisation d'une adresse IP)

4. **Cliquer sur "Connect" pour établir la connexion avec le serveur TightVNC.

5. **Entrer le mot de passe :

Une fois que vous avez cliqué sur "Connect", une fenêtre vous demandera de saisir le mot de passe. Entrez le mot de passe fourni par votre administrateur : Azerty1*.

6. **Vérification du port** : Veillez à utiliser le même port que celui paramétré sur votre serveur TightVNC. Par défaut, la requête client est envoyée sur le port 5900 ; toutefois, si vous avez défini un port différent, veuillez le spécifier dans le champ approprié.

En suivant ces étapes simples, vous serez en mesure de vous connecter aisément à votre serveur TightVNC depuis le client, en utilisant l'adresse IP ou le nom de domaine approprié, ainsi que le port configuré spécifiquement pour votre serveur.

Double-clic sur l'icône de lancement située sur le bureau 

![](https://github.com/WildCodeSchool/tssr-2405-p1-g2-VNC/blob/main/images/tight_vnc.png)

### Utilisation Avancée 

1. **Qualité de l'affichage** : Veuillez recourir à l'option "Qualité de l'image" pour ajuster avec précision la qualité de l'affichage selon vos exigences. Vous avez le choix entre différentes valeurs telles que "Élevée", "Moyenne" ou "Basse", en fonction de la qualité de votre connexion.

2. **Compression des données** : Activez l'option de compression des données afin de réduire la bande passante utilisée lors de la connexion. Ceci peut potentiellement optimiser les performances sur des liaisons à faible débit.

3. **Résolution de l'écran** : Ajustez minutieusement la résolution de votre écran pour qu'elle s'accorde parfaitement avec les dimensions de votre écran local et celles du terminal distant. Il vous est possible d'opter pour une résolution moindre afin d'atténuer la consommation en bande passante.

4. **Sécurité** : Explorez scrupuleusement les diverses options sécuritaires, notamment le chiffrement des données, dans le but d'assurer une connexion distante sécurisée à l'ordinateur distant.

5. **Redirection des ports** : Configurez adéquatement la redirection des ports pour acheminer les ports locaux vers ceux du terminal distant si nécessaire, afin d'accéder à des services spécifiques sur cet ordinateur distant.

6. **Gestion des couleurs** : Ajustez méticuleusement les paramètres relatifs à la gestion des couleurs selon vos préférences. Vous pouvez choisir entre une meilleure qualité d'image ou davantage de performances, en fonction de vos impératifs.

7. **Déconnexion et gestion des sessions** :
    - **Déconnexion** : Pour mettre fin à votre session sur l'ordinateur distant, veuillez cliquer sur "Déconnecter" dans le menu TightVNC.
    - **Gestion des sessions** : TightVNC offre la possibilité de gérer plusieurs sessions simultanément. Il est possible de naviguer entre les différentes sessions ouvertes en utilisant les onglets situés en haut de la fenêtre.
    - **Clôture de session** : Dans l'éventualité où vous n'avez pas l'intention de vous reconnecter à une session, vous pouvez la clôturer en optant pour l'option "Fermer" dans le menu TightVNC.

## Dépannage 

### 1. Problème de connexion :

- Veuillez vérifier que le serveur TightVNC est actif sur l'ordinateur distant.
- Assurez-vous que l'adresse IP ou le nom d'hôte du serveur TightVNC est correctement spécifié dans le client TightVNC.
- Contrôlez les paramètres des pare-feu et des logiciels antivirus sur le serveur et le client pour garantir que TightVNC est autorisé à communiquer à travers le réseau.

### 2. Pour les problèmes d'affichage :

- Si l'affichage à distance est flou ou pixelisé, ajustez les paramètres de qualité d'image et de compression dans le client TightVNC pour améliorer la clarté visuelle.
- Assurez-vous que la résolution d'écran est correctement configurée sur le serveur TightVNC afin de répondre aux besoins de l'utilisateur.

### 3. En cas de problèmes de performance :

- Si TightVNC fonctionne lentement, réduisez la qualité d'image, augmentez la compression ou diminuez la résolution d'écran pour optimiser les performances.
- Surveillez la charge réseau et processeur sur le serveur TightVNC et le client afin d'identifier toute contrainte potentielle.

### 4. Concernant les problèmes liés à l'impression :

- Veuillez vous assurer que l'imprimante est correctement configurée et partagée sur le serveur TightVNC.
- Veillez à ce que les pilotes d'imprimante soient installés et à jour sur le serveur TightVNC.
- Assurez-vous que les utilisateurs distants disposent des autorisations appropriées pour accéder à l'imprimante partagée.

### 5. Problèmes de sécurité :

- En cas de difficultés liées à la sécurité, veuillez vérifier si TightVNC est configuré pour utiliser des connexions sécurisées, telles que le chiffrement SSL ou l'utilisation d'un tunnel VPN.
- Consultez les journaux de sécurité de TightVNC afin de repérer toute activité suspecte ou tentative d'accès non autorisé.

### 6. Problèmes de compatibilité :

- Si des problèmes de compatibilité surviennent avec certaines applications ou environnements, assurez-vous d'utiliser la version la plus récente de TightVNC et d'avoir installé toutes les mises à jour disponibles.

En suivant ces étapes de dépannage, vous devriez être en mesure de résoudre la plupart des problèmes courants rencontrés lors de l'utilisation de TightVNC. Si des difficultés persistent, nous vous recommandons de consulter la documentation associée à TightVNC ou de contacter le support technique pour obtenir une assistance supplémentaire.
