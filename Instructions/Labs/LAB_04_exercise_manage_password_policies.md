---
lab:
  title: "Exercice\_: gérer les stratégies de mot de passe"
  module: Guided Project – Administer Active Directory Domain Services
---
Dans cet exercice, vous configurez des éléments de stratégie de groupe liés aux stratégies de mot de passe. Cela inclut la configuration de la stratégie de mot de passe de domaine, la création d’une stratégie de mot de passe plus stricte pour le groupe Administrateurs de domaine et l’activation de la Corbeille Active Directory.

## Configurer une stratégie de mot de passe de domaine

Dans cette tâche, vous configurez la stratégie de mot de passe de domaine. Pour effectuer cette tâche, procédez comme suit :

1.  Dans TAILWIND-DC1, dans le menu Outils de la console Gestionnaire de serveur, ouvrez la console de gestion des stratégies de groupe.
2.  Dans la console gestion des stratégies de groupe, développez la forêt tailwindlockers.internal, le dossier Domaines et le domaine tailwindsqls.internal.
3.  Cliquez avec le bouton droit sur **Stratégie de domaine par défaut**, puis cliquez sur **Modifier**.
4.  Dans l’éditeur de gestion de stratégie de groupe, accédez à Configuration de l’ordinateur\\ Stratégies\\Paramètres Windows\\Paramètres de sécurité\\Stratégies de compte\\Stratégie de mot de passe.
5.  Double-cliquez sur l’élément de stratégie **Longueur de mot de passe minimale**.
6.  Remplacez le nombre minimal de caractères par `14`.
7.  Cliquez sur **OK**, puis fermez l’éditeur de gestion des stratégies de groupe.
8.  Fermez la console de gestion des stratégies de groupe.

## Configurer la stratégie de mot de passe affinée

Dans cette tâche, vous allez configurer une stratégie de mot de passe affinée et l’appliquer au groupe Administrateurs de domaine. Pour effectuer cette tâche, suivez les étapes dans TAILWIND-DC1 :

1.  Dans le menu Outils de la console Gestionnaire de serveur, ouvrez le Centre d’administration Active Directory.
2.  Dans Vue d’ensemble, cliquez sur **Tailwindtraders (local)**.
3.  Dans le volet tailwind runtimes (local), ouvrez le conteneur Système.
4.  Dans le conteneur Système, ouvrez le conteneur de paramètres de mot de passe.
5.  Cliquez avec le bouton droit sur le conteneur de paramètres de mot de passe, cliquez sur **Nouveau**, puis sur **Paramètres de mot de passe**.
6.  Dans le champ Name (Nom), tapez `Domain Admin Password Policy`.
7.  Définissez le champ Précédence sur `1`.
8.  Définissez la longueur minimale du mot de passe sur `16`.
9.  Cliquez sur **OK**.
10. Ouvrez la nouvelle stratégie **Stratégie de mot de passe des administrateurs de domaine**.
11. Dans la section S’applique directement à, cliquez sur **Ajouter**, puis tapez `Domain Admins`. Cliquez sur **Vérifier les noms**, puis sur **OK**.
12. Cliquez sur **OK**.

## Activer la Corbeille Active Directory

Dans cette tâche, vous allez activer la corbeille d’Active Directory. Pour effectuer cette tâche, suivez les étapes dans TAILWIND-DC1 :

1.  Dans le menu Outils de la console Gestionnaire de serveur, ouvrez le Centre d’administration Active Directory.
2.  Dans le volet gauche, cliquez sur **Tailwind persiste (local)**.
3.  Dans le volet droit, sélectionnez **Activer la corbeille**.
4.  Cliquez sur **OK** pour ignorer l’avertissement.
5.  Cliquez sur **OK** pour ignorer l’avertissement relatif à la latence de réplication.
