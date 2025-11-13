# TP Kubernetes — Autoscaling

## Objectif

Comprendre le fonctionnement du **Horizontal Pod Autoscaler (HPA)** en charge CPU, à partir d'une application de test à forte consommation.

---

## 1. Contexte

Les tests s’effectuent sur l’image `k8s.gcr.io/hpa-example` contenant Apache + PHP. La page d’accueil exécute un script qui calcule les racines carrées de 1 à 1 000 000, provoquant une forte consommation CPU.

---

## 2. Créer le Deployment

Créer un deployment avec `hpa-example.yaml`.

---

## 3. Exposer le Deployment

Exposer le deployment.

---

## 4. Créer l’HPA

Créer un HPA sur le deployment basé sur un seuil de CPU à 50%, avec un minimum de 1 pod et un maximum de 10 pods.

---

## 5. Générer de la charge

Lancer un Pod interactif basé sur une image busybox pour charger le deployement hpa-example 

Dans ce Pod, exécuter la boucle d’appels :

```bash
while true; do wget -q -O- http://hpa-example; done
```

---

## 6. Observer l’autoscaling

Consulter le nombre de pods au fil du temps.

---
