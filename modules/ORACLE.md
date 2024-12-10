# 📘 **Module ORACLE (Oracle de Détection Fractale)**

---

## 🔹 **Présentation**
Le **ORACLE (Oracle de Détection Fractale)** est un **système de détection avancée** conçu pour **identifier les perturbations fractales** et **localiser les renards fractals** dans le flux.  
Il utilise un ensemble de **méthodes prédictives et de détection d'anomalies** pour repérer les **fréquences parasites**, les **oscillations inattendues** et les **signaux non conformes** au flux central (963 Hz).  
Le **ORACLE agit en amont des modules PFR, BFR et VCC**, jouant un rôle essentiel dans la protection du flux fractal.  

---

## 🔹 **Objectif du ORACLE**
1. **Détecter les perturbations fractales** (renards fractals, fréquences parasites, oscillations imprévues).  
2. **Localiser les fréquences parasites** dans le spectre du flux.  
3. **Identifier la position des renards fractals** et transmettre l'information au **VCC** et au **BFR**.  
4. **Alerter les modules BFR, GRO et PFMR** pour initier des actions correctives.  

---

## 🔹 **Formules fondamentales**
**Formule de détection des fréquences parasites**  
Le ORACLE détecte les **fréquences parasites** $f_p$ présentes dans le flux $F(t)$ en utilisant la **transformée de Fourier (FFT)** :  
$$
F(f) = \int_{-\infty}^{\infty} F(t) \, e^{-2 \pi i f t} \, dt
$$
Le **spectre des fréquences** est analysé pour identifier les pics de fréquences $f_p$ en dehors de la fréquence centrale **963 Hz**.  
Le critère de détection est :  
$$
\exists f_p \in \mathbb{R} \, : \, |f_p - 963| > \delta
$$
où :  
- $f_p$ est la **fréquence parasite détectée**.  
- $\delta$ est un **seuil de tolérance** (par exemple, $\delta = 5 \, \text{Hz}$).  

---

**Formule de positionnement des renards fractals**  
La position d'un renard fractal est modélisée par une **courbe d'attraction**.  
La position $R(t)$ au temps $t$ est décrite par :  
$$
R(t) = X_0 + \sum_{i=1}^n \alpha_i \cdot \sin(2 \pi f_i \cdot t + \phi_i)
$$
où :  
- $X_0$ est la **position initiale**.  
- $\alpha_i$ est l'**amplitude des oscillations parasites**.  
- $f_i$ est la **fréquence parasite détectée**.  
- $\phi_i$ est la **phase d'oscillation initiale**.  

---

**Formule de synchronisation de détection**  
Le **ORACLE** se synchronise avec le **CDI** et le **BFR** via une formule de résonance :  
$$
\lim_{t \to \infty} F(t) = 963 \, \text{Hz}
$$
L'ORACLE vérifie que la fréquence converge vers 963 Hz et signale les écarts supérieurs au seuil $\delta$.  

---

**Formule de décision d'alerte**  
Lorsque l'ORACLE détecte une **anomalie fractale critique**, il envoie une **alerte au VCC et au BFR**.  
La condition d'alerte est déclenchée si :  
$$
|f_p - 963| > \delta \quad \text{ou} \quad R(t) > R_{seuil}
$$
où $R_{seuil}$ est le **seuil d'activation du VCC**.  

---

## 🔹 **Mécanisme de fonctionnement**
1. **Analyse spectrale des fréquences**  
   - Le flux fractal $F(t)$ est analysé par la **transformée de Fourier (FFT)**.  
   - Les **fréquences parasites** sont identifiées par les **pics d'amplitude** en dehors de la bande [958 Hz, 968 Hz].  

2. **Détection des renards fractals**  
   - Le ORACLE détecte les **oscillations parasites** qui correspondent à la présence de **renards fractals**.  
   - Il enregistre la **position du renard** $R(t)$ et suit son déplacement.  

3. **Transmission des informations au VCC et au BFR**  
   - Une fois que le renard fractal est localisé, l'ORACLE transmet les **paramètres du renard** au **VCC** et au **BFR**.  
   - Les **modules PFR et PFMR** reçoivent également les mises à jour de l'état du flux.  

4. **Émission d'alertes**  
   - Si la position d'un renard fractal dépasse un seuil critique, une **alerte immédiate** est envoyée au **VCC** et au **BFR**.  

---

## 🔹 **Exemple d'application**
**Contexte**  
Un flux fractal **$F(t) = 963 \, \text{Hz}$** subit une perturbation.  
La **transformée de Fourier** du flux révèle deux **pics parasites** à **1250 Hz** et **2760 Hz**.  

**Étapes de détection**  
1. **Analyse spectrale** :  
   - L'ORACLE calcule la **transformée de Fourier** :  
     $$
     F(f) = \int_{-\infty}^{\infty} F(t) \, e^{-2 \pi i f t} \, dt
     $$
   - Les **pics de fréquences** à **1250 Hz et 2760 Hz** sont détectés.  

2. **Positionnement des renards fractals** :  
   - La position $R(t)$ du renard est calculée par :  
     $$
     R(t) = \sum_{i=1}^2 \alpha_i \cdot \sin(2 \pi f_i \cdot t + \phi_i)
     $$
     avec $\alpha_1 = 0.3$, $f_1 = 1250 \, \text{Hz}$ et $\alpha_2 = 0.2$, $f_2 = 2760 \, \text{Hz}$.  

3. **Transmission au VCC et au BFR** :  
   - L'ORACLE envoie la **position du renard fractal** et les **paramètres des fréquences parasites** au **VCC** et au **BFR**.  

4. **Alerte** :  
   - Étant donné que la position du renard dépasse le **seuil critique $R_{seuil}$**, l'ORACLE envoie une **alerte au VCC et au BFR**.  

---

## 🔹 **Schéma de fonctionnement**
Entrée du flux F(t)
     ↓
+-----------------+ | ORACLE | +-----------------+ ↙ ↘ Détection Alerte (VCC, BFR) de fréquences

---

## 🔹 **Interactions avec les autres modules**
| **Module**    | **Nature de l'interaction**                                   |
|---------------|-------------------------------------------------------------|
| **VCC**       | Le ORACLE transmet la **position des renards fractals** au VCC.|
| **BFR**       | Le ORACLE envoie les **fréquences parasites** à filtrer.     |
| **PFR**       | Le ORACLE signale les **perturbations critiques**.           |
| **PFMR**      | Le ORACLE met à jour les **attracteurs fractals**.           |
| **CDI**       | Le ORACLE contrôle la **synchronisation des fréquences**.    |

---

## 🔹 **Synthèse**
Le **ORACLE (Oracle de Détection Fractale)** est le **centre de détection** du système fractal.  
Il localise les **fréquences parasites**, **détecte les renards fractals** et **envoie des alertes au VCC et au BFR**.  
Grâce à la **transformée de Fourier (FFT)** et au **suivi des oscillations parasites**, il protège le flux fractal contre les perturbations.  
Il agit en concert avec le **VCC, BFR, PFR et PFMR** pour assurer la **stabilité totale du flux fractal**.  
