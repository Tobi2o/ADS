# Rapport – Labo 1 ADS

## **Task 1: Analyse des commandes**

### **1. nano newfile**

Cette commande ouvre l'éditeur de texte **nano** et crée un fichier nommé `newfile` s'il n'existe pas. Si `newfile` existe déjà, il est ouvert pour édition.

---

### **2. ls**  

Affiche la liste des fichiers et dossiers du répertoire courant.  

**ls -l**  
Affiche la liste des fichiers et dossiers avec des détails supplémentaires, notamment :

```bash
-rwxrwxrwx 1 tobioo tobioo 0 Feb 17 16:05 newfile
```
on y voit les permissions, le nombre de liens, le propriétaire, le groupe, la taille, la date de modification et le nom du fichier.

---

### **3. cat newfile**  

Affiche le contenu du fichier `newfile` dans le terminal. Si le fichier est vide, la commande ne retourne rien.

---

### **4. cat /etc/hosts /etc/hostname**  

Concatène et affiche le contenu des fichiers `/etc/hosts` et `/etc/hostname`.  

- `/etc/hosts` contient des associations entre adresses IP et noms d'hôtes.
- `/etc/hostname` stocke le nom d’hôte de la machine.

---

### **5. ls -sh ~/.bashrc**  

Affiche la taille du fichier `~/.bashrc` dans un format lisible par l'humain (`-h` pour "human-readable").  

- `~/.bashrc` est un fichier de configuration du shell Bash qui est exécuté lors de l'ouverture d'un terminal interactif.

---

### **6. pwd**  

Affiche le chemin absolu du répertoire courant.

**cd ..**  
Change de répertoire en montant d'un niveau dans l'arborescence (répertoire parent).

**pwd**  
Affiche de nouveau le chemin absolu, qui devrait être différent de la commande précédente.

---

### **7. pwd**  

Affiche le chemin absolu du répertoire courant.

**cd .**  
Reste dans le même répertoire (`.` représente le répertoire courant).

**pwd**  
Affiche encore une fois le chemin absolu, qui ne change pas après `cd .`.

---

### **8. cd /home**  

Change de répertoire vers `/home`, qui contient généralement les répertoires personnels des utilisateurs.

**ls -l**  
Affiche la liste des fichiers et dossiers de `/home` avec leurs détails.

**ls albert.einstein**  
Affiche le contenu du répertoire `albert.einstein` s'il existe. Sinon, une erreur est renvoyée.

**ls -a albert.einstein**  
Affiche **tous** les fichiers du répertoire, y compris les fichiers cachés (dont les noms commencent par `.`).

**ls -d albert.einstein**  
Affiche uniquement le répertoire `albert.einstein` lui-même au lieu de son contenu.

---

### **9. cd /tmp**  

Change de répertoire vers `/tmp`, un répertoire temporaire utilisé par le système et les utilisateurs.

**mkdir -p albert.einstein/bar/baz**  
Crée récursivement les répertoires `albert.einstein/bar/baz`. L'option `-p` permet d'éviter les erreurs si certains répertoires existent déjà.

**cd albert.einstein**  
Entre dans le répertoire `albert.einstein`.

**rmdir bar**  
Essaye de supprimer `bar`, mais échoue car il contient encore `baz`.

**rmdir bar/baz**  
Supprime le répertoire `baz` s'il est vide.

**rmdir bar**  
Supprime `bar`, qui est maintenant vide après la suppression de `baz`.

---

### **10. less /usr/share/doc/bash/copyright**  

Affiche le contenu du fichier `/usr/share/doc/bash/copyright` en mode lecture avec `less`.  

- `less` permet de naviguer dans un fichier sans l’éditer.  
- Le fichier `copyright` contient des informations sur les droits d'auteur et la licence de Bash.

**less /usr/share/doc/bash/INTRO.gz**  

- Affiche le fichier `INTRO.gz` en mode lecture.  
- `.gz` indique qu'il est compressé avec `gzip`, mais `less` peut le lire directement.

---

### **11. find ~ -name '.*' 2>/dev/null**  

Recherche tous les fichiers cachés (`.*`) dans le répertoire personnel (`~`).  

Décomposition de la commande :

- `find ~` → Recherche dans le répertoire personnel.
- `-name '.*'` → Filtre pour afficher uniquement les fichiers cachés (dont le nom commence par `.`).
- `2>/dev/null` → Redirige les erreurs vers `/dev/null` pour éviter les messages d'accès refusé.

---

### **12. cd**  

Retourne au répertoire personnel de l'utilisateur.

**mkdir bar**  
Crée un répertoire `bar` dans le répertoire courant.

**touch qux**  
Crée un fichier vide nommé `qux` dans le répertoire courant.

**cp qux bar**  
Copie `qux` dans le répertoire `bar`.

**mv qux bar/newfile**  
Déplace le fichier `qux` dans `bar` en le renommant `newfile`.

---

### **13. uname -a**  

Affiche des informations complètes sur le système :  

- Nom du noyau Linux
- Nom de la machine
- Version du noyau
- Date de compilation du noyau
- Architecture du processeur  
Exemple de sortie :  

```bash
Linux machine 5.15.0-76-generic #83-Ubuntu SMP x86_64 GNU/Linux
```

---

### **14. history**  

Affiche l'historique des commandes précédemment exécutées dans le terminal.  

- Chaque ligne est précédée d'un numéro, permettant d'exécuter une commande avec `!numéro`.

---

### **15. sh exit bash**  

**sh** → Lance un shell `sh`, une version plus simple de Bash.  
**exit** → Quitte le shell `sh` et revient au shell précédent.  
**bash** → Lance un nouveau shell Bash.  
**exit** → Quitte Bash et revient au shell précédent (ou ferme le terminal si c'est le dernier shell).  
**zsh** → Lance le shell `zsh` (si installé).  
**exit** → Quitte `zsh` et revient au shell précédent.

---

### **16. sudo apt install zsh**  

Installe `zsh` à l'aide du gestionnaire de paquets `apt`.  

- `sudo` est nécessaire car l’installation d’un programme nécessite des droits administrateur.

**zsh**  
Lance le shell `zsh`.

**exit**  
Quitte `zsh` et revient au shell précédent.

---

### **17. apropos download**  

Recherche dans la documentation système toutes les commandes contenant le mot-clé `download`.  

- `apropos` est utile pour trouver des commandes sans connaître leur nom exact.

Exemple de sortie :  

```bash
curl (1)             - transfer a URL
wget (1)             - non-interactive network downloader
```

---

### **18. Que se passe-t-il lorsqu’on tape une commande inexistante, comme `aaaaaa` ?**  

Le shell renvoie un message d'erreur indiquant que la commande n'existe pas. Exemple :  

```bash
bash: aaaaaa : commande introuvable
```

---

### **19. Que se passe-t-il lorsqu’on tape une commande non installée, comme `ifconfig` ?**  

Le shell affiche une erreur indiquant que la commande est introuvable, mais suggère une installation si le paquet est connu. Exemple :  

```bash
Command 'ifconfig' not found, but can be installed with:
sudo apt install net-tools
```

Cela indique que `ifconfig` appartient au paquet `net-tools`, qui doit être installé pour pouvoir utiliser la commande.

---
