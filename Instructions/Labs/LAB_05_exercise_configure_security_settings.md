---
lab:
  title: "Exercice\_: configurer les paramètres de sécurité"
  module: Guided Project – Administer Active Directory Domain Services
---
Dans cet exercice, vous configurez les paramètres liés à la sécurité, notamment la désactivation de l’authentification NTLM pour les comptes de domaine, l’audit de l’activité de gestion du compte et le refus de connexion en tant que service pour les membres d’un groupe de sécurité.

## Restreindre l’authentification NTLM

Dans cette tâche, vous allez restreindre l’authentification NTLM. Pour effectuer cette tâche, suivez les étapes dans TAILWIND-DC1 :

1.  Dans le menu Outils de la console Gestionnaire de serveur, ouvrez la console Gestion des stratégies de groupe.
2.  Dans la console gestion des stratégies de groupe, développez la forêt tailwindlockers.internal, le dossier Domaines et le domaine tailwindsqls.internal. Développez ensuite les objets de stratégie de groupe.
3.  Cliquez avec le bouton droit sur **Stratégie des contrôleurs de domaine par défaut**, puis cliquez sur **Modifier**.
4.  Accédez à Configuration de l’ordinateur\\Stratégies\\Paramètres Windows\\Paramètres de sécurité\\Stratégies locales\\Options de sécurité.
5.  Sélectionnez et double-cliquez sur **Sécurité réseau : restreindre NTLM: authentification NTLM dans ce domaine**.
6.  Cochez la case **Définir ces paramètres de stratégie**.
7.  Sélectionnez la valeur **Tout refuser**, puis cliquez sur **OK**.
8.  Dans la boîte de dialogue Confirmer la modification du paramètre, cliquez sur **Oui**.
9.  Fermez l’Éditeur de gestion des stratégies de groupe.

## Auditer la gestion des comptes d’utilisateur à Sydney

Dans cette tâche, vous allez activer l’audit de la gestion des comptes d’utilisateur dans l’unité d’organisation Sydney. Pour effectuer cette tâche, suivez les étapes dans TAILWIND-DC1 :

1.  Dans le menu Outils de la console Gestionnaire de serveur, choisissez Console de gestion des stratégies de groupe.
2.  Dans la console de gestion des stratégies de groupe, développez le domaine Tailwindlockers.internal.
3.  Accédez à l’unité d’organisation Sydney, cliquez avec le bouton droit puis sélectionnez **Créer un objet GPO dans ce domaine et le lier ici…**.
4.  Nommez le nouvel objet GPO `SydneyOUPolicy`.
5.  Cliquez sur **OK**.
6.  Cliquez avec le bouton droit sur SydneyOUPolicy et sélectionnez **Modifier**.
7.  Accédez à Configuration de l’ordinateur\\Stratégies\\Paramètres Windows\\Paramètres de sécurité\\Configuration de la stratégie d’audit avancée\\Stratégies d’audit\\Gestion de compte.
8.  Sélectionnez et double-cliquez sur **Auditer la gestion des comptes d’utilisateur**.
9.  Cochez la case **Configurer les événements d’audit suivants**.
10.  Sélectionnez les valeurs **Réussite** et **Échec**, puis cliquez sur **OK**.
11.  Fermez l’éditeur de gestion des stratégies de groupe.

## Refuser l’ouverture de session en tant que service

Dans cette tâche, vous allez configurer l’option de sécurité Refuser l’ouverture de session en tant que service. Pour effectuer cette tâche, suivez les étapes dans TAILWIND-DC1 :

1.  Dans le menu Outils de la console Gestionnaire de serveur, ouvrez la console Gestion des stratégies de groupe.
2.  Développez le domaine Tailwind clusters.internal.
3.  Accédez à l’unité d’organisation Sydney et cliquez avec le bouton droit sur SydneyOUPolicy. Sélectionnez **Modifier**.
4.  Accédez à Configuration de l’ordinateur\\Stratégies\\Paramètres Windows\\Paramètres de sécurité\\Stratégies locales\\Attribution des droits utilisateur.
5.  Sélectionnez et double-cliquez sur la stratégie **Refuser l’ouverture de session en tant que service**.
6.  Sélectionnez le paramètre **Définir cette stratégie**.
7.  Cliquez sur **Ajouter un groupe ou un utilisateur**.
8.  Cliquez sur **Parcourir**, puis sur **Avancé**, et sur **Rechercher maintenant**.
9.  Sélectionnez le groupe **Administrateurs Sydney**.
10. Cliquez sur **OK** jusqu’à ce que les boîtes de dialogue soient fermées (quatre ou cinq validations peuvent être nécessaire).
