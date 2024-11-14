---
lab:
  title: "Exercice\_: configurer des opérations de gestion des utilisateurs "
  module: Guided Project – Administer Active Directory Domain Services
---
Dans cet exercice, vous effectuez des opérations de gestion des utilisateurs.

## Créer des unités d’organisation

Dans cette tâche, vous allez créer trois unités d’organisation : Sydney, Melbourne et Brisbane. Pour effectuer cette tâche, procédez comme suit :

1.  Dans TAILWIND-DC1, à partir du menu Outils de la console Gestionnaire de serveur, ouvrez Utilisateurs et ordinateurs Active Directory.
2.  Cliquez avec le bouton droit sur le domaine **tailwindtraders.internal**.
3.  Sélectionnez **Nouveau**, puis **Unité d’organisation**.
4.  Dans la boîte de dialogue Nouvel objet - Unité d’organisation, définissez le nom sur `Sydney` et cliquez sur **OK**.
5.  Répétez ce processus pour créer les unités d’organisation `Melbourne` et `Brisbane`.

## Créer des utilisateurs

Dans cette tâche, vous allez créer un utilisateur et configurez des propriétés de compte telles que la date d’expiration du compte. Pour effectuer cette tâche, procédez comme suit :

1.  Dans TAILWIND-DC1, ouvrez Utilisateurs et ordinateurs Active Directory (ou Centre d’administration).
2.  Cliquez avec le bouton droit sur l’unité d’organisation Sydney.
3.  Sélectionnez **Nouveau**, puis **Utilisateur**.
4.  Tapez `SydneyContractor` dans les champs Nom complet et Nom d’ouverture de session utilisateur, puis cliquez sur **Suivant**.
5.  Spécifiez un mot de passe, par exemple `Pa55w.rdPa55w.rd`, puis confirmez le mot de passe.
6.  Cliquez sur **Suivant** et **Terminer**.
7.  Sélectionnez l’unité d’organisation Sydney. Dans l’unité d’organisation Sydney, double-cliquez sur le compte d’utilisateur SydneyContractor.
8.  Dans l’onglet Compte, dans la section **Expiration du compte**, sélectionnez **Fin :** et définissez la date du **1er janvier 2030**. Cliquez sur **OK**.
9.  Cliquez avec le bouton droit sur l’utilisateur SydneyContractor, puis sélectionnez **Copier**.
10. Tapez `MelbourneContractor` dans les champs Nom complet et Nom d’ouverture de session utilisateur. Sélectionnez **Suivant**.
11. Spécifiez un mot de passe, par exemple `Pa55w.rdPa55w.rd`, puis confirmez le mot de passe.
12. Cliquez sur **Suivant** et **Terminer**.
13. Cliquez avec le bouton droit sur l’utilisateur SydneyContractor, puis sélectionnez **Copier**.
14. Tapez `BrisbaneContractor` dans les champs Nom complet et Nom d’ouverture de session utilisateur. Sélectionnez **Suivant**.
15. Spécifiez un mot de passe, par exemple `Pa55w.rdPa55w.rd`, puis confirmez le mot de passe.
16. Cliquez sur **Suivant** et **Terminer**.
17. Faites glisser l’utilisateur MelbourneContractor vers l’unité d’organisation Melbourne.
18. Si un avertissement sur les objets en mouvement s’affiche, cliquez sur **Oui**.
19. Faites glisser l’utilisateur BrisbaneContractor vers l’unité d’organisation Brisbane.
20. Si un avertissement sur les objets en mouvement s’affiche, cliquez sur **Oui**.


## Créer le groupe Administrateurs de Sydney

Dans cette tâche, vous allez créer un groupe de sécurité nommé Administrateurs Sydney. Pour effectuer cette tâche, procédez comme suit :

1.  Dans TAILWIND-DC1, ouvrez Utilisateurs et ordinateurs Active Directory.
2.  Cliquez avec le bouton droit sur l’unité d’organisation Sydney, sélectionnez **Nouveau**, puis **Groupe**.
3.  Tapez `Sydney Administrators` dans le nom du groupe et sélectionnez **Universel** dans l’étendue du groupe. Cliquez sur **OK**.
4.  Dans l’unité d’organisation Sydney, double-cliquez sur le compte d’utilisateur SydneyContractor.
5.  Dans l’onglet Membre de, cliquez sur **Ajouter**.
6.  Tapez `Sydney Administrators`.
7.  Cliquez sur **Vérifier les noms**.
8.  Cliquez sur **OK** puis sur **OK**.

## Configurer un utilisateur en tant qu’utilisateur protégé

Dans cette tâche, vous allez configurer le compte d’utilisateur SydneyContractor en tant qu’utilisateur protégé. Pour effectuer cette tâche, procédez comme suit :

1.  Dans TAILWIND-DC1, ouvrez Utilisateurs et ordinateurs Active Directory (ou Centre d’administration).
2.  Accédez à l’unité d’organisation Sydney et double-cliquez sur le compte d’utilisateur SydneyContractor.
3.  Dans l’onglet Membre de, cliquez sur **Ajouter**.
4.  Tapez `Protected Users`.
5.  Cliquez sur **Vérifier les noms**.
6.  Cliquez sur **OK** puis sur **OK**.

## Déléguer des autorisations de sécurité d’une unité d’organisation à un groupe de sécurité

Dans cette tâche, vous allez déléguer la possibilité de réinitialiser les mots de passe et de forcer la modification du mot de passe au groupe Administrateurs Sydney pour les comptes dans l’unité d’organisation Sydney. Pour effectuer cette tâche, procédez comme suit :

1.  Dans TAILWIND-DC1, ouvrez Utilisateurs et ordinateurs Active Directory.
2.  Cliquez avec le bouton droit sur l’unité d’organisation Sydney, puis cliquez sur **Déléguer le contrôle**.
3.  Dans la page de bienvenue de l’assistant Délégation de contrôle, cliquez sur **Suivant**.
4.  Cliquez sur **Ajouter**, puis tapez `Sydney Administrators`.
5.  Cliquez sur **Vérifier les noms**.
6.  Cliquez sur **OK**, puis sur **Suivant**.
7.  Dans la page Tâches à déléguer, sélectionnez l’option **Réinitialiser les mots de passe utilisateur et forcer le changement de mot de passe à la prochaine ouverture de session**. Cliquez sur **Suivant**.
8.  Cliquez sur **Terminer**.

## Configurer l’attribut Ville pour un utilisateur

Dans cette tâche, vous allez configurer un attribut Ville pour un compte d’utilisateur, puis utilisez l’attribut Rechercher pour vérifier que l’utilisateur est présent. Pour effectuer cette tâche, procédez comme suit :

1.  Dans TAILWIND-DC1, ouvrez Utilisateurs et ordinateurs Active Directory.
2.  Sélectionnez l’unité d’organisation Sydney, cliquez avec le bouton droit sur le compte d’utilisateur SydneyContractor, puis cliquez sur **Propriétés**.
3.  Dans l’onglet Adresse des propriétés de SydneyContractor, définissez le champ Ville sur `Sydney` et cliquez sur **OK**.
4.  Dans Utilisateurs et ordinateurs Active Directory, cliquez avec le bouton droit sur Tailwindtrader.internal, puis cliquez sur **Rechercher**.
5.  Dans l’onglet Avancé de la boîte de dialogue Rechercher des utilisateurs, des contacts et des groupes, sélectionnez **Champ**, puis Utilisateur **, et ****Ville**. Définissez la condition sur **Est (exactement)**. Définissez la valeur sur **Sydney**. Cliquez sur **Rechercher**.
6.  Cliquez sur **Oui** dans la fenêtre contextuelle Rechercher dans le répertoire.
7.  Vérifiez que l’utilisateur SydneyContractor est répertorié dans les **résultats de la recherche**.
8.  Fermez la boîte de dialogue Rechercher des utilisateurs, des contacts et des groupes.

## Désactiver l’utilisateur prestataire Melbourne

Dans cette tâche, vous allez désactiver l’utilisateur MelbourneContractor. Pour effectuer cette tâche, procédez comme suit :

1.  Dans TAILWIND-DC1, ouvrez Utilisateurs et ordinateurs Active Directory, puis ouvrez l’unité d’organisation Melbourne.
2.  Dans l’unité d’organisation Melbourne, cliquez avec le bouton droit sur **MelbourneContractor**, puis cliquez sur **Désactiver le compte**.
3.  Cliquez sur **OK**.

## Réinitialiser le mot de passe de l’utilisateur du prestataire Brisbane

Dans cette tâche, vous allez réinitialiser le mot de passe de l’utilisateur BrisbaneContractor. Pour effectuer cette tâche, procédez comme suit :

1.  Dans TAILWIND-DC1, ouvrez Utilisateurs et ordinateurs Active Directory, puis ouvrez l’unité d’organisation Brisbane.
2.  Cliquez avec le bouton droit sur l’utilisateur BrisbaneContractor, puis sélectionnez **Réinitialiser le mot de passe**.
3.  Dans la boîte de dialogue Réinitialiser le mot de passe, tapez le mot de passe `Pa66w.rdPa66w.rd` deux fois et sélectionnez **OK**. Cliquez à nouveau sur **OK** dans la boîte de dialogue qui vous informe que le mot de passe a été modifié.
