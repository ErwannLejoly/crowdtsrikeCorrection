### Instructions pour la suppression du fichier affecté par CrowdStrike en mode sans échec avec BitLocker activé

Si vous ne pouvez pas désactiver BitLocker avant de redémarrer en mode sans échec à cause d'un écran bleu, vous pouvez suivre les étapes suivantes pour déverrouiller BitLocker et supprimer les fichiers problématiques. Cela nécessite d'accéder à l'environnement de récupération de Windows (WinRE).

#### Objectif
Supprimer le fichier C-00000291*.sys du répertoire C:\Windows\System32\drivers\crowdstrike pour corriger le problème lié à CrowdStrike.

### Étapes à suivre

#### 1. Démarrer en environnement de récupération de Windows (WinRE)

1. **Démarrer l'ordinateur et accéder à WinRE** :
   - Si vous avez un disque ou une clé USB d'installation de Windows :
     1. Insérez le média d'installation et redémarrez votre ordinateur.
     2. Appuyez sur la touche nécessaire pour accéder au menu de démarrage (généralement F12, Esc, ou une autre touche spécifique à votre ordinateur).
     3. Sélectionnez le média d'installation pour démarrer à partir de celui-ci.
     4. Cliquez sur Réparer l'ordinateur au lieu d'installer Windows.

   - Si vous n'avez pas de média d'installation :
     1. Redémarrez votre ordinateur.
     2. Dès le démarrage, appuyez plusieurs fois sur F11 ou la touche dédiée pour accéder aux options de récupération (cela peut varier en fonction du fabricant).

2. **Accéder à l'Invite de commandes** :
   - Dans WinRE, allez dans Dépannage > Options avancées > Invite de commandes.

#### 2. Déverrouiller BitLocker dans WinRE

1. **Déverrouiller le lecteur avec BitLocker** :
   - Dans l'invite de commandes, entrez la commande suivante pour déverrouiller le lecteur :
     
powershell
     manage-bde -unlock C: -RecoveryPassword VOTRE-CLE-DE-RECUPERATION

   - Remplacez VOTRE-CLE-DE-RECUPERATION par votre clé de récupération BitLocker.

2. **Désactiver temporairement BitLocker** :
   - Pour désactiver BitLocker, entrez la commande suivante :
     
powershell
     manage-bde -protectors -disable C:


#### 3. Supprimer le fichier problématique

1. **Naviguer vers le répertoire des pilotes CrowdStrike** :
   - Entrez les commandes suivantes pour naviguer vers le répertoire et supprimer le fichier problématique :
     
powershell
     cd C:\Windows\System32\drivers\crowdstrike
     del C-00000291*.sys


2. **Confirmer la suppression** :
   - Vérifiez que les fichiers correspondants ont été supprimés en listant les fichiers dans le répertoire :
     
powershell
     dir


#### 4. Redémarrer en mode normal

1. **Réactiver les protecteurs BitLocker** :
   - Entrez la commande suivante pour réactiver BitLocker :
     
powershell
     manage-bde -protectors -enable C:


2. **Redémarrer l'ordinateur** :
   - Tapez exit pour fermer l'invite de commandes.
   - Redémarrez votre ordinateur normalement.

### Notes supplémentaires

- **Droits administratifs** : Assurez-vous d'avoir les privilèges administratifs pour exécuter ces commandes.
- **Clé de récupération BitLocker** : Ayez toujours votre clé de récupération BitLocker à portée de main en cas de problème.
- **Sauvegarde** : Avant de désactiver BitLocker ou de modifier des fichiers système, assurez-vous de sauvegarder vos données.

En suivant ces étapes, vous pouvez résoudre les problèmes liés à BitLocker et supprimer les fichiers spécifiés de votre système pour corriger le problème lié à CrowdStrike.
