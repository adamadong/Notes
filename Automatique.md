# Automatique
_This note is mainly in French._
> Principal References are textbooks from ECPK while small changes are made according to classes taught at ECM.  
> _These should be just the differences between different notations_

- [Automatique](#automatique)
  - [I. Base de connaissances](#i-base-de-connaissances)
    - [I.1 quelques notations utiles](#i1-quelques-notations-utiles)
    - [I.2 Transformée de Laplace](#i2-transformée-de-laplace)
    - [I.3 Système du $`1^{er}`$ ordre et $`2^{e}`$ ordre](#i3-système-du-1er-ordre-et-2e-ordre)

## I. Base de connaissances
### I.1 quelques notations utiles
 En régime permanent:
 **Stabilité,Précision, Robuste**
 >_Les deux dernières notations ne sont pas requis pour le semestre S7_

En régime transitoire:
**Temps de réponse à 5%** : $`\forall t>t_{5\%},\frac{\lvert s(t)-s_{\infty} \rvert}{s_{\infty}}<0.05 `$   
**Gain statique**  
**Valeur de résonnance**  
**Bande Passante** ：des fréquences où  la valeur en cette fréquence vaut la valeur maximale $`-3dB`$

### I.2 Transformée de Laplace  
$`F(p)=\mathcal{L}[f(t)]=\int_{0^-}^{+\infty}{f(t)e^{-pt}dt}`$  
fonction de transfert: $`H(p)=\frac{K}{p^{\alpha}}\frac{N(p)}{D(p)}`$ $`\frac{Zéros}{Pôles}`$  
propriétés importantes:   
- Valeur initiale : $`f(0^+)=\lim_{p\rightarrow+\infty}{pF(p)}`$
- Valeur Finale : $`\lim_{t\rightarrow+\infty}{f(t)}=\lim_{p\rightarrow 0}{pF(p)}`$  
  
![propriétés importantes](automatique/Laplace.jpg)  
Voici les transformées de Laplace usuelles:  

![transformées de Laplace usuelles](automatique/Laplaceusuelles.jpg)

__Formule de Black__:
Pour un système à boucle fermé:  

![boucle fermé](automatique/schemaBlack.jpg)

La fonction de transfert: $`H(p)=\frac{X(p)}{X_C(P)}=\frac{F_1(P)}{1+F_1(P)F_2(P)}`$  
_Ici, le + dans la fonction de transfert correspond au - dans le schéma._

### I.3 Système du $`1^{er}`$ ordre et $`2^{e}`$ ordre
- Système du $`1^{er}`$ ordre:
  $$` H(p)=\frac{S(p)}{E(p)}=\frac{K}{1+\tau p} `$$
  K est le gain statique; $`\tau`$ est la constante de temps

