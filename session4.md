# LAB4 : Outils CI/CD

---

## 1 : Générer une paire de clés

![lab4_image1](./images/lab4_image1.png)

Génération d'une paire de clés pour signer les images Docker.
---

## 2 : Signer une image Docker et la pousser sur GitLab

![lab4_image2](./images/lab4_image2.png)

---

## 3 :  Vérification de la signature réussie

![lab4_image3](./images/lab4_image3.png)

---

## 4 : Vérification de la signature (succès puis échec)

![lab4_image4](./images/lab4_image4.png)

---

## 5 : Construction d’une image vulnérable

![lab4_image5](./images/lab4_image5.png)

Cette image est construite avec une version vulnérable de curl, afin d'être scannée avec Trivy pour détecter cette vulnérabilité.

---

## Réponses

### Quels sont les résultats des deux commandes de vérification Cosign ?
Succès, car c’est l’image d’origine signée.
Echec, car l’image a été modifiée après signature.

### Faites un git push et observez votre pipeline. Tout est passé ?
Oui, tout est passé.

### À quelle étape la pipeline échoue ? Pourquoi ?
Elle échoue à l'étape `scan` car Trivy détecte une vulnérabilité critique dans la version de `curl` spécifiée.
