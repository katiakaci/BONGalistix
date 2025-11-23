# BONGalistix 🕹️

**Bongalistix** est un jeu 2D basé sur la physique dans lequel vous contrôlez un lanceur et ajustez en temps réel l’angle ainsi que la force de tir grâce à la souris. Votre objectif : **atteindre la cible avant que le projectile ne s’immobilise**, à travers une série de niveaux mêlant précision, réflexion et trajectoires complexes.


Chaque niveau introduit une configuration différente de murs, obstacles et position de cible, nécessitant précision et stratégie pour réussir.
Voici un exemple d’un niveau en cours d’exécution :

<div align="center">
  <img width="328" height="400" alt="BONGalistix" src="https://github.com/user-attachments/assets/1ca5efa6-d234-41b8-b2a5-6319e4e76a32" />
</div>

## ⚙️ Système physique

Le projectile est soumis à plusieurs phénomènes réalistes :

### Gravité
Le projectile est attiré vers le bas (≈ 9.8 m/s²).

### Frottement de l’air
Basée sur le coefficient aérodynamique d’une sphère, la résistance de l’air réduit progressivement la vitesse.

### Rebonds réalistes
- rebonds selon l’orientation du mur (vertical / horizontal)  
- perte d’énergie selon un coefficient de restitution  
- léger décalage pour éviter que le projectile ne traverse les murs  

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

## 🎮 Contrôles

| Action | Description |
|--------|-------------|
| **Déplacer la souris** | Oriente et ajuste la force du tir |
| **Clic (bouton gauche)** | Déclenche un tir |

La longueur du lanceur représente directement la **vitesse initiale** du projectile.

