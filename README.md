# Script-d-installation-de-th-mes-GRUB-Sleek-CyberRe-Vimix-Dark-
Ce script permet à l’utilisateur de personnaliser facilement l’écran GRUB de son Kali Linux avec des thèmes neutres, élégants et adaptés à une utilisation professionnelle .

🎯 Objectif

Le script a pour but de :

* Télécharger et installer trois thèmes GRUB populaires : Sleek, CyberRe, et Vimix Dark.
* Permettre à l’utilisateur de choisir facilement lequel appliquer.
* Mettre à jour la configuration de GRUB pour appliquer ce thème au démarrage.


⚙️ Pré-requis

* Distribution : Kali Linux (ou autre dérivée Debian/Ubuntu).
* Paquets nécessaires : `git`, `grub2` (déjà présent sur Kali).
* Droits administrateur (utilisation de `sudo`).

 🛠️ Étapes d’exécution

1. Téléchargement du script
   L’utilisateur sauvegarde le script sous le nom `install-themes.sh`.

2. Autorisation d’exécution
   Le script est rendu exécutable :

   ```bash
   chmod +x install-themes.sh
   ```

3. Lancement du script

   ```bash
   ./install-themes.sh
   ```

4. Exécution automatique :

   * Création d’un dossier temporaire `~/grub-themes`.
   * Téléchargement et installation des 3 thèmes :

     * Sleek (sobre et minimaliste).
     * CyberRe (style hacker/cyberpunk).
     * Vimix Dark (moderne et élégant).

5. Choix de l’utilisateur
   Le script affiche un menu interactif :

   ```
   1) Sleek (sobre et pro)
   2) CyberRe (style hacker/cyberpunk)
   3) Vimix Dark (moderne et élégant)
   ```

   → L’utilisateur saisit un chiffre (1, 2 ou 3).

6. Application du thème

   * Le chemin du thème choisi est écrit dans `/etc/default/grub` via la variable :

     ```bash
     GRUB_THEME="/boot/grub/themes/nom/theme.txt"
     ```

7. Mise à jour du GRUB
   Le script exécute :

   ```bash
   sudo update-grub
   ```

   Ce qui génère un nouveau menu GRUB avec le thème sélectionné.

8. Message final
   Le script confirme la réussite et recommande un redémarrage :

   ```
   ✅ Installation terminée !
   Redémarre ton PC pour voir ton nouveau GRUB.
   ```

 📊 Résultats attendus

* Après redémarrage, le menu GRUB affiche le thème choisi.
* L’utilisateur peut relancer le script à tout moment pour changer de thème.
* Aucun logo de distribution Linux n’apparaît (thèmes neutres).


## 🚨 Limites et remarques

* Si l’image choisie par un thème est trop lourde (> 8MB), GRUB pourrait refuser de l’afficher.
* Le script suppose que `git` est installé (sinon, installer avec `sudo apt install git`).
* Les thèmes modifient uniquement GRUB (bootloader), pas l’écran Plymouth ni le login.
