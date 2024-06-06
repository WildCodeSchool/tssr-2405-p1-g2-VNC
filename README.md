# Projet 1 - VNC

## **Objectif :** Configurer un accès sécurisé pour l’administration à distance d’un serveur depuis un client.

### Mise en pratique des compétences suivantes :

- Mettre en place un serveur
- Installer et configurer un logiciel/un service
- Réaliser un projet en équipe
- Documenter toutes les étapes
- Faire une démonstration de la réalisation finale

### **Éléments à implémenter :**

- Un client Windows 10 ou Linux Ubuntu
- Un serveur Debian ou Windows Server 2022 (choix : Windows Server 2022)
- Documentations destinées aux administrateurs
- Documentations destinées aux utilisateurs

### **Répartitions des rôles et des tâches :**

SM : Scrum master / PO : Product owner / dev : équipe developpement 

| Rôles       | Tâches Semaine 1                                                                                                                      | Tâches Semaine 2                                                                                                                 |
|-------------|--------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------|
| **SM**      | Mina : Rédaction du guide utilisateur                                                                                          | Mohamed : Création d'un tableau de bord de pilotage des tâches via la plateforme "Jira", appui aux membres du groupe     |
| **PO**      | Joris : Installation de VNC sur le poste client                                                                                | Ronan : Finalisation du guide administrateur, du fichier README.md, préparation du support de présentation 2              |
| **dev**     | Ronan : Rédaction du guide administrateur                                                                                      | Mina : Finalisation du guide utilisateur                                                                                   |
| **dev**     | Mohamed : Installation et configuration d'une VM Windows Server sur Proxmox ainsi que VNC Server                              | Joris : Installation de PuTTY pour créer une connexion SSH    



## Choix de l'OS et des logiciels :

|             | **Avantages**                                                                                                                                                                                                                                                                                                                                                     | **Inconvénients**                                                                                                                                                                                                                                                                                                                                      |
|-------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Proxmox** | - Hyperviseur de niveau 1, offrant des performances optimales pour la gestion des machines virtuelles. <br> - Permet de faire communiquer nos deux machines virtuelles sur un même réseau local, ce qui a facilité la prise en main à distance TightVNC. <br> - Permet plusieurs connexions simultanées à des machines virtuelles sur un serveur dédié, facilitant ainsi la collaboration et le travail d'équipe. | - Nécessite une configuration initiale approfondie et une certaine courbe d'apprentissage pour les nouveaux utilisateurs. <br> - Peut être complexe à gérer sans une connaissance préalable des systèmes de virtualisation et des réseaux.                                                         |
| **Debian**  | - Gratuité et open source. <br> - Sécurité et stabilité grâce aux mises à jour régulières de la communauté de sécurité active. <br> - Flexibilité et personnalisation, large choix de logiciels permettant de personnaliser l'installation de sécurité. <br> - Faible consommation de ressources, idéal pour tous types de serveurs.                                               | - Interface utilisateurs qui peut être difficile à appréhender. <br> - Pas beaucoup de compatibilité logicielle comparé à Windows Serveur 2022. <br> - Besoin de connaissances approfondie afin de pouvoir faire des configurations avancées.                                                                                             |
| **Windows Server 2022** | - Plus de sécurité grâce aux fonctionnalités Secured Core Server et Defender For Endpoint. <br> - Meilleur support et maintenance pour les entreprises grâce aux supports Microsoft et à un meilleur écosystème d'entreprises. <br> - Intégration avec les produits Microsoft avec Active Directory, Azure et les autres applications Microsoft telles que Exchange Server, SharePoint ou encore SQL Server. | - Consommation de ressources plus importantes. <br> - Dépendance à l'écosystème Microsoft. <br> - Sous licences et coût assez élevé, mais des ISO de version d'essai existent (nous l'utiliserons car il est plus adapté pour notre projet).                                                     |
| **RealVNC** | - Sécurité renforcée grâce au chiffrement de bout en bout, VNC cloud et 2FA (authentification à deux facteurs). <br> - Simplicité de l'installation et configurations faciles à faire. <br> - Meilleures performances grâce à l'optimisation de la bande passante et un support multiplateforme (Windows, MacOS, Linux, Android et iOS). <br> - Fonctionnalités avancées comme la gestion centralisée, le transfert de fichiers et le chat intégré pour communiquer avec les utilisateurs pendant une session. | - Licences payantes et coûts assez élevés (c'est la raison pour laquelle on ne l'utilise pas dans ce projet, mais si vous êtes une entreprise, il est conseillé d'utiliser RealVNC).                                                                                                                                                                                           |
| **TightVNC**| - Gratuité et open source, personnalisable selon les besoins (c'est pour cela que l'on utilise durant le projet). <br> - Simplicité de l'installation et configurations faciles à faire. <br> - Fonctionnalités de base solides pour le contrôle à distance et le transfert de fichiers.                                                                                                                                                           | - Moins de fonctionnalités de sécurité comme le chiffrement de bout en bout natif ou le 2FA. <br> - Fonctionnalités limitées comme la gestion centralisée, le chat intégré et d'API pour les intégrations personnalisées. <br> - Mises à jour et maintenance moins fréquentes comparées aux solutions commerciales.                                     |

### **Conclusion pour le choix de l'OS et de VNC :**

 - **Nous utiliserons Windows Server 2022 car il est plus adapté à l'installation du VNC  ( grâce aux fonctionnalités de sécurisation avancés ) mais surtout grâce à l'interface graphique qui nous permettra d'installer plus facilement une VNC. En parlant de la VNC , le choix que l'on a fait est TightVNC grâce à sa gratuité même si RealVNC est bien meilleur en termes de fonctionnalités mais il y a une licence.**

## Problèmes recontrés et Solutions trouvés :

| Problèmes rencontrés           | Solutions trouvées                                                         |
|--------------------------------|----------------------------------------------------------------------------|
| Problèmes de Compatibilité    | Utilisation de versions compatibles de VNC et gratuite TightVNC           |
| Configuration du Pare-feu     | Ouverture des ports nécessaires (par défaut, le port 5900 pour VNC) dans le pare-feu |
| Problèmes de Sécurité         | Utilisation de tunnels SSH pour sécuriser la connexion VNC                |

## Tests Réalisés et Résultats obtenus :

#### Tests de performances :

- Mesure de la latence de connexion et du temps de réponse lors de l'utilisation de l'application VNC
- Vérification de la sécurisation de la connexion via SSH

#### Tests de compatibilités : 

- Vérification de la compatibilité entre différentes versions de VNC et les environnements de bureau
- Tests sur différents systèmes d'exploitation (Windows, Linux,)

#### Résultats Obtenus

- Connexion Établie : Connexion VNC réussie après ouverture des ports nécessaires et configuration appropriée du serveur et du client
- Bonne Performance : Latence acceptable et bonne fluidité d'affichage sur des réseaux locaux
- Sécurité Améliorée : Connexion sécurisée via un tunnel SSH, empêchant les interceptions non autorisées

#### Suggestions d’Améliorations Futures :

- Automatisation : Création de scripts pour automatiser l'installation et la configuration de VNC server et client, incluant la configuration du pare-feu et la mise en place de tunnels SSH

- Amélioration de la Sécurité : Intégration de méthodes d'authentification avancées comme l'utilisation de certificats SSL/TLS pour sécuriser les connexions VNC


