# Automatique
_This note is mainly in French._
> Principal References are textbooks from ECPK while small changes are made according to classes taught at ECM.  
> _These should be just the differences between different notations_

- [Automatique](#automatique)
  - [I. Base de connaissances](#i-base-de-connaissances)
    - [I.1 quelques notations utiles](#i1-quelques-notations-utiles)
    - [I.2 Transformée de Laplace](#i2-transformée-de-laplace)
    - [I.3 Système du $`1^{er}`$ ordre et $`2^{e}`$ ordre](#i3-système-du-1er-ordre-et-2e-ordre)
    - [I.4 Diagrammes fréquentiels](#i4-diagrammes-fréquentiels)
  - [II Méthodes de détermination des performances du système](#ii-méthodes-de-détermination-des-performances-du-système)
    - [II.1 Stabilité](#ii1-stabilité)

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
  $` H(p)=\frac{S(p)}{E(p)}=\frac{K}{1+\tau p} `$  
  K est le gain statique; $`\tau`$ est la constante de temps
- Système du $`2^{e}`$ ordre:  
  $`H(p)=\frac{S(p)}{E(p)}=\frac{K}{1+2\xi\frac{p}{\omega_0}+\frac{p^2}{\omega_0^2}}`$  
  K est le gain statique; $`\omega_0`$ est la pulsation propre;  
  $`\xi`$ est le facteur d'amortissement; $`Q=\frac{1}{2\xi}`$ est le facteur de qualité.    

  __les notations importantes__  
  ![automatique/Notation.jpg](https://github.com/adamadong/Notes/blob/main/automatique/Notation.jpg)

  ### I.4 Diagrammes fréquentiels
  - Diagramme de Bode 
      $`G_{dB}(\omega)=20\log A(\omega)`$ et $`\varphi(\omega)`$    
      ![Bode](https://github.com/adamadong/Notes/blob/main/automatique/Bode.jpg) 
      __Pulsation de coupure__$`\omega_{c0}`$ et __Pulsation d'opposition de phase__$`\omega_{\pi}`$

  - Diagramme de Black 
      $`G_{dB}(\omega)`$ en fonction de $`\varphi(\omega)`$    
      ![[Black](automatique/Black.jpg)](https://github.com/adamadong/Notes/blob/main/automatique/Black.jpg)
  - Diagramme de Nyquist
      $`Re[H(j\omega)]`$ en fonction de $`Im[H(j\omega)]`$    
      ![[Nyquist](automatique/Nyquist.jpg) ](https://github.com/adamadong/Notes/blob/main/automatique/Nyquist.jpg)  
    __Pulsation de cassure/coupure à -3dB__  
    Pour un système du premier ordre : $`\omega_c=\frac{1}{\tau}`$    
    ![[Bode1](automatique/Bode1.jpg) ](https://github.com/adamadong/Notes/blob/main/automatique/Bode1.jpg)  
    _Pulsation de résonance_  
    Pour un système d'ordre 2 tel que $`0\leq\xi<\frac{\sqrt{2}}{2}`$ : $`\omega_r=\omega_0\sqrt{1-2\xi^2}`$  
    __Tracer les diagrammes__  
    $`H(p)=\frac{K}{p^{\alpha}}e^{-\tau p}\prod(1+\tau_ip)^{\alpha_i}\prod(1+2\xi\frac{p}{\omega_0}+\frac{p^2}{\omega_0^2})^{\beta_i}`$  
    Bode asymptotique:  
    D'abord  
    ![[First](automatique/step1.jpg) ](https://github.com/adamadong/Notes/blob/main/automatique/step1.jpg) 
    Puis  
    ![[Second](automatique/step2.jpg) ](https://github.com/adamadong/Notes/blob/main/automatique/step2.jpg) 
    <strong style="color:red">ATTENTION!</strong>  
    A ECM, l'asymptote pour la phase est tracé <strong style="color:red">différemment</strong>:  
    soit $`\omega_i`$ la pulsation propre d'un composant:  
    $`\varphi(\omega_i)=\varphi(\frac{\omega_i}{10})+\alpha_i\frac{\pi}{4}=\varphi(10\omega_i)-\alpha_i\frac{\pi}{4}`$  
    Il s'agit d'une ligne diagonale et non d'une ligne droite.

## II Méthodes de détermination des performances du système

  ### II.1 Stabilité
  __Condition nécessaire et suffisante de stabilité__  
  Un système est stable si et seulement si <strong style="color:red">tous les pôles</strong> de sa fonction de transfert sont à <strong style="color:red">partie réelle strictement négative</strong>.  
  __table de Routh__
  ![Routh](automatique/Routh.jpg)  
  Un système est stable si et seulement si les deux conditions ci-après sont vérifiées :  
  tous les coefficients de son équation caractéristique sont <strong style="color:red">de même signe</strong>;  
  tous les termes de <strong style="color:red">la première colonne</strong>, dite colonne des pivots, de la table de Routh de son équation caractéristique sont <strong style="color:red">de même signe</strong>   
  _tout changement de signe dans cette colonne correspond à l’existence d’un pôle à partie réelle positive._





