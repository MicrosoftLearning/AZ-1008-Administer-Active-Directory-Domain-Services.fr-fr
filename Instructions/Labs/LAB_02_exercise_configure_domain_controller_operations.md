---
lab:
  title: "Exercice\_: configurer des opérations du contrôleur de domaine"
  module: Guided Project – Administer Active Directory Domain Services
---
Dans cet exercice, vous allez promouvoir un serveur au contrôleur de domaine, transférer un rôle FSMO au nouveau contrôleur de domaine, créer un site et lui ajouter un sous-réseau.

## Installer Active Directory Domain Services (AD DS) et le promouvoir auprès du contrôleur de domaine

Dans cette tâche, vous allez promouvoir le serveur membre TAILWIND-MBR1 pour qu’il devienne un contrôleur de domaine dans le domaine TAILWINDSQLS. Pour effectuer cette tâche, procédez comme suit :

1.  Connectez-vous à TAILWIND-MBR1 en tant que TAILWINDSEES\\Administrateur avec le mot de passe : `Pa55w.rdPa55w.rd`.
2.  Dans le Gestionnaire de serveur, sélectionnez le menu Gérer, puis **Ajouter des rôles et des fonctionnalités**.
3.  Dans la page Avant de commencer de l’assistant Ajouter de rôles et des fonctionnalités, cliquez sur **Suivant**.
4.  Sur la page Sélectionner le type d’installation, sélectionnez **Installation basée sur un rôle ou une fonctionnalité**, et cliquez sur **Suivant**.
5.  Dans la page Sélectionner le serveur de destination, choisissez **Sélectionner un serveur dans le pool de serveurs**, assurez-vous que TAILWIND-MBR1 est sélectionné, puis cliquez sur **Suivant**.
6.  Dans la page Sélectionner des rôles de serveurs, cochez la case **Services de domaine Active Directory**. La page Ajouter des fonctionnalités s’ouvre. Sélectionnez **Ajouter des fonctionnalités**. Sélectionnez **Suivant**.
7.  Dans la page Sélectionner des fonctionnalités, cliquez sur **Suivant**.
8.  Dans la page Services de domaine Active Directory, puis cliquez sur **Suivant**.
9.  Dans la page Confirmer les sélections d’installation, cliquez sur **Installer**. Selon la vitesse de l’ordinateur, l’installation peut prendre plusieurs minutes. Une fois l’installation terminée, cliquez sur **Fermer**.
10. Dans le menu du Gestionnaire de serveur, sélectionnez l’icône de notification en regard du drapeau dans le coin supérieur droit (comme illustré dans la capture d’écran).

    ![Capture d’écran du menu du gestionnaire de serveur affichant l’icône d’alerte.](./Media/server-manager-menu.png)
13. Dans le menu qui s’ouvre lorsque vous sélectionnez l’icône de notification, sélectionnez **Promouvoir ce serveur en contrôleur de domaine**. L’assistant Configuration des services de domaine Active Directory sera lancé.
14. Dans la page Configuration du déploiement, sélectionnez **Ajouter un contrôleur de domaine à un domaine existant** et vérifiez que le nom de domaine est défini sur **tailwind clusters.internal**.
15. Vous devez authentifier à nouveau le compte d’administrateur. Sélectionnez **Changer**. Entrez `Administrator` pour le nom d’utilisateur et `Pa55w.rdPa55w.rd` pour le mot de passe. Cliquez sur **OK**. Sélectionnez **Suivant**.
16. Dans la page Options de contrôleur de domaine, acceptez les paramètres par défaut et fournissez un mot de passe en mode de restauration des services d’annuaire (DSRM). Pour ce faire, entrez le mot de passe suivant deux fois : `Pa55w.rdPa55w.rd`. Sélectionnez **Suivant**.
17. Dans la page Options DNS, cliquez sur **Suivant**.
18. Dans la page Options supplémentaires, cliquez sur **Suivant**.
19. Dans la page Chemins d’accès, cliquez sur **Suivant**.
20. Dans la page Examiner les options de, cliquez sur **Suivant**
21. Sur la page Vérification des conditions requises , cliquez sur **Installer**. L’installation prend plusieurs minutes en fonction de la vitesse de la machine virtuelle. La machine virtuelle redémarre.
22. Lorsque la machine virtuelle redémarre, connectez-vous en tant que `tailwindtraders\administrator` avec le mot de passe que vous avez configuré pour le compte administrateur par défaut (`Pa55w.rdPa55w.rd`)

## Transférer les rôles Flexible Single Master Operations

Dans cette tâche, vous allez transférer le rôle maître RID de TAILWIND-DC1 vers TAILWIND-MBR1. Pour effectuer cette tâche, procédez comme suit :

1.  Sur TAILWIND-MBR1, dans **Outils**, ouvrez Utilisateurs et ordinateurs Active Directory.<br>
2.  Dans le volet de navigation, cliquez avec le bouton droit sur Utilisateurs et ordinateurs Active Directory, pointez sur **Toutes les tâches**, puis cliquez sur **Maîtres d’opérations**.
3.  Dans l’onglet RID, sélectionnez **Modifier**, puis **Oui**, et cliquez sur **OK**.
4.  Cliquez sur **Fermer** pour fermer la boîte de dialogue Maîtres d’operations.

## Créer un site Active Directory et configurer un sous-réseau pour ce site

Dans cette tâche, vous allez créer un site Active Directory et configurer un sous-réseau associé à ce site. Pour effectuer cette tâche, procédez comme suit :

1.  Sur TAILWIND-DC1, connectez-vous en tant que `tailwindtraders\administrator` avec le mot de passe que vous avez configuré pour le compte administrateur par défaut (`Pa55w.rdPa55w.rd`).
2.  Dans le menu Outils, ouvrez Sites et services Active Directory.
3.  Cliquez avec le bouton droit sur Sites, sélectionnez **Nouveau site** et tapez `Sydney` comme nom de site.
4.  Pour le nom du lien, sélectionnez DEFAULTIPSITELINK, puis cliquez deux fois sur **OK**.
5.  Développez le dossier **Sites** .
6.  Cliquez avec le bouton droit sur **Sous-réseaux**, puis sélectionnez **Nouveau sous-réseau**.
7.  Pour le préfixe, tapez `172.16.1.0/24`, sélectionnez **Sydney** comme nom de site, puis cliquez sur **OK**.
8.  Fermez Sites et services Active Directory.
