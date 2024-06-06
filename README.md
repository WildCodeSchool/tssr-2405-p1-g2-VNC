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

### Prérequis :

- Serveur Windows Server 2022 avec un environnement de bureau installé
- Serveur SSH installé et configuré
- Logiciel TightVNC installé sur le serveur
- Client VNC installé sur la machine locale

### **Répartitions des rôles et des tâches :**

#### **Semaine 1 :**

- Mina : Scrum master
- Joris : Product Owner

#### **Semaine 2 :**

- Mohamed : Scrum Master
- Ronan : Product Owner

#### Répartition des tâches :

- Mina : Ecrire la documentation du USER_GUIDE.md fournissant des instructions détaillé sur l'installation de VNC chez les utilisateurs
- Joris : Installation et configuration d’une VM Windows Server , de VNC sur le serveur et d'établir une connexion SSH
- Mohamed : Installation et configuration d’une VM Windows Server , de VNC sur le serveur et d'établir une connexion SSH
- Ronan : Rédiger la documenation d'INSTALL.md fournissant des instructions détaillées sur la gestion et l'administration présentant le projet. Mais aussi d'un fichier README.md pour introduire les membres du groupe, les rôles dans le groupe (par sprint), les difficultés rencontrées, les solutions trouvées, les tests réalisés, etc
## Choix de l'OS et des logiciels :

### Proxmox :
**Problématique : Nous ne pouvions pas faire communiquer nos machines à distance pour la virtualisation, ce qui nous empêchait de collaborer efficacement sur notre projet**

**Solution : Proxmox, une plateforme de virtualisation open source, permet de gérer des machines virtuelles sur un serveur dédié. Grâce à Proxmox, nous avons pu collaborer et travailler ensemble sur la même machine virtuelle, facilitant ainsi l'avancement de notre projet**

### Debian :

**Avantages :**

- Gratuité et open source
- Sécurité et stabilité grâce aux mises à jour régulières de la communauté de sécurité active
- Flexibilité et personnalisation, large choix de logiciels permettant de personnaliser l'installation de sécurité
- Faible consommation de ressources, idéal pour tous types de serveurs

**Inconvénients :**

- Interface utilisateurs qui peut être difficile à appréhender
- Pas beaucoup de compatibilité logicielle comparé à Windows Serveur 2022
- Besoin de connaissances approfondie afin de pouvoir faire des configurations avancées 

### Windows Server 2022 :

**Avantages :**

- Plus de sécurité grâce aux fonctionnalités Secured Core Server et Defender For Endpoint
- Meilleur support et maintenance pour les entreprises grâce aux supports Microsoft et à un meilleur écosystème d'entreprises
- Intégration avec les produits Microsoft avec Active Directory, Azure et les autres applications Microsoft telles que Exchange Server, SharePoint ou encore SQL Server

**Inconvénients :**

- Consommation de ressources plus importantes
- Dépendance à l'écosystème Microsoft
- Sous licences et coût assez élevé, mais des ISO de version d'essai existent (nous l'utiliserons car il est plus adapté pour notre projet)

### RealVNC :

**Avantages :**

- Sécurité renforcée grâce au chiffrement de bout en bout, VNC cloud et 2FA (authentification à deux facteurs)
- Simplicité de l'installation et configurations faciles à faire
- Meilleures performances grâce à l'optimisation de la bande passante et un support multiplateforme (Windows, MacOS, Linux, Android et iOS)
- Fonctionnalités avancées comme la gestion centralisée, le transfert de fichiers et le chat intégré pour communiquer avec les utilisateurs pendant une session
- Support technique performant et documentation très complète
- Adaptation à toutes tailles d'entreprises grâce à des licences flexibles et des fonctionnalités pour des environnements assez importants

**Inconvénients :**

- Licences payantes et coûts assez élevés (c'est la raison pour laquelle on ne l'utilise pas dans ce projet, mais si vous êtes une entreprise, il est conseillé d'utiliser RealVNC)

### TightVNC :

**Avantages :**

- Gratuité et open source, personnalisable selon les besoins (c'est pour cela que l'on utilise durant le projet)
- Simplicité de l'installation et configurations faciles à faire
- Fonctionnalités de base solides pour le contrôle à distance et le transfert de fichiers

**Inconvénients :**

- Moins de fonctionnalités de sécurité comme le chiffrement de bout en bout natif ou le 2FA
- Fonctionnalités limitées comme la gestion centralisée, le chat intégré et d'API pour les intégrations personnalisées
- Mises à jour et maintenance moins fréquentes comparées aux solutions commerciales



### **Conclusion pour le choix de l'OS et de VNC :**

 - **Nous utiliserons Windows Server 2022 car il est plus adapté à l'installation du VNC  ( grâce aux fonctionnalités de sécurisation avancés ) mais surtout grâce à l'interface graphique qui nous permettra d'installer plus facilement une VNC. En parlant de la VNC , le choix que l'on a fait est TightVNC grâce à sa gratuité même si RealVNC est bien meilleur en termes de fonctionnalités mais il y a une licence.**

## Problèmes recontrés et Solutions trouvés :

#### Problèmes recontrés :

- Problèmes de Compatibilité : Différentes versions de VNC (RealVNC vs Tight Vnc) et tight vnc que partie serveur 
- Configuration du Pare-feu : Bloquage des ports nécessaires par le pare-feu, empêchant la connexion VNC
- Problèmes de Sécurité : Connexion non sécurisée (non chiffrée), exposant le trafic VNC à des attaques potentielles

#### Solutions Trouvées :

- Compatibilité : Utilisation de versions compatibles de VNC et gratuite TightVNC
- Pare-feu : Ouverture des ports nécessaires (par défaut, le port 5900 pour VNC) dans le pare-feu
- Sécurité : Utilisation de tunnels SSH pour sécuriser la connexion VNC

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


