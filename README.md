# Bongalistix  🕹️

**Bongalistix** est un jeu 2D basé sur la physique : vous contrôlez un lanceur, réglez l’angle et la force du tir avec la souris, et tentez d’atteindre une cible avant que le projectile ne s’immobilise à travers une série de niveaux. 🎯

Le projectile est soumis à :
- la **gravité**  
- la **résistance de l’air**  
- des **rebonds** contre les murs  
- une **perte d’énergie** progressive  

Chaque niveau introduit une configuration différente de murs, obstacles et position de cible, nécessitant précision et stratégie pour réussir.

Voici un exemple d’un niveau en cours d’exécution :

<div align="center">
  <img width="328" height="400" alt="BONGalistix" src="https://github.com/user-attachments/assets/1ca5efa6-d234-41b8-b2a5-6319e4e76a32" />
</div>

## ⚙️ Système physique

Le moteur du jeu applique plusieurs phénomènes réalistes :

### ✔ Gravité
Le projectile est attiré vers le bas (≈ 9.8 m/s²).

### ✔ Frottement de l’air
Basé sur le coefficient aérodynamique d’une sphère, ce qui réduit progressivement la vitesse.

### ✔ Rebonds réalistes
- rebonds selon l’orientation du mur (vertical / horizontal)  
- perte d’énergie selon un coefficient de restitution  
- léger décalage pour éviter que le projectile ne traverse les murs  

Les collisions utilisent des calculs d’intersection de segments et d’équations de droites, fournis par la librairie géométrique (`geometrie.c`).

## 🗂️ Structure des niveaux

Chaque niveau est défini dans un fichier texte contenant :
- les dimensions de la zone
- des segments verticaux
- des segments horizontaux
- la position du lanceur
- la position et taille de la cible

Les fichiers sont situés dans :  
```
Niveaux/niveau1.txt
Niveaux/niveau2.txt
...
Niveaux/niveau18.txt
```

La lecture est gérée par :  
```c
lire_fichier_niveau(...)
```

## 🎮 Contrôles

| Action | Description |
|--------|-------------|
| **Déplacer la souris** | Oriente et ajuste la force du tir |
| **Clic (bouton gauche)** | Déclenche un tir ou avance après un résultat |
| **Fermer la fenêtre** | Quitte le jeu |

La longueur du lanceur représente directement la **vitesse initiale** du projectile.

