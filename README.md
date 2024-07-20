# crowdtsrikeCorrection
# Instructions pour la suppression du fichier affecté par CrowdStrike en mode sans échec

## Objectif
Supprimer le fichier `C-00000291*.sys` du répertoire `C:\Windows\System32\drivers\crowdstrike` pour corriger le problème lié à CrowdStrike.

## Étapes à suivre

### 1. Redémarrer Windows en mode sans échec
- **Redémarrez votre ordinateur.**
- Dès que le PC commence à démarrer, appuyez à plusieurs reprises sur la touche `F8` (ou `Shift + F8` sur certains systèmes) jusqu'à ce que le menu des options de démarrage avancées apparaisse.
- Dans le menu, sélectionnez `Mode sans échec` ou `Mode sans échec avec prise en charge réseau` en utilisant les touches fléchées et appuyez sur `Entrée`.

### 2. Ouvrir PowerShell en tant qu'administrateur
- Appuyez sur `Windows + X` pour ouvrir le menu Power User.
- Sélectionnez `Windows PowerShell (Admin)`.

### 3. Préparer le script PowerShell
- Créez un nouveau fichier texte et copiez-y le script suivant.
- Enregistrez le fichier avec l'extension `.ps1`, par exemple, `Remove-CrowdStrikeFiles.ps1`.
-coller le code du script  ( ou le cloner )

### 4. Exécuter le script
- Naviguez vers le répertoire où vous avez enregistré le script.
- Exécutez le script en entrant la commande suivante dans PowerShell :

```powershell
cd C:\chemin\vers\script
.\Remove-CrowdStrikeFiles.ps1   
```

### 5. Vérifier la suppression
- Après avoir exécuté le script, vérifiez le répertoire `C:\Windows\System32\drivers\crowdstrike` pour vous assurer que tous les fichiers correspondant au motif `C-00000291*.sys` ont été supprimés.

### 6. Redémarrer en mode normal
- Redémarrez votre ordinateur normalement.

## Notes supplémentaires
- **Droits administratifs** : Assurez-vous d'avoir les privilèges administratifs pour supprimer des fichiers système.
- **Sauvegarde** : Il est conseillé de sauvegarder les données critiques avant de modifier les fichiers système.
- **Tests** : Testez le script dans un environnement contrôlé avant de le déployer sur des systèmes de production.

En suivant ces étapes, vous pouvez efficacement supprimer les fichiers spécifiés de votre système pour corriger le problème lié à CrowdStrike.
