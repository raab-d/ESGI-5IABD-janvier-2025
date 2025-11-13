# TP Kubernetes — Volumes

## Objectif

Déployer un **WordPress** avec **MySQL** persistant.

---

## 1. Secret MySQL

Générer un secret avec un mot de passe MySQL en utilisant l’option `--from-literal`.

---

## 2. Volumes persistants

Créer les volumes décrits dans :

- `mysql-volumeclaim.yaml`
- `wordpress-volumeclaim.yaml`

---

## 3. Base de données MySQL

Créer la base MySQL et le service associé :

- `mysql.yaml`
- `mysql-service.yaml`

---

## 4. Application WordPress

Créer l’instance WordPress et exposer le service :

- `wordpress.yaml`
- `wordpress-service.yaml`

---

## 5. Accès à l’application

Récupérer l’adresse IP de votre WordPress et y accéder.

---

## 6. Test de persistance

Dé­truire les pods MySQL et WordPress.

Question : Que se passe-t-il ? (un peu de patience quand même ;) )

---
