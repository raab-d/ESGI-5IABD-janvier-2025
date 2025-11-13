# TP Kubernetes — Créer un service

## Objectif

Créer un **Service** Kubernetes et comprendre le mécanisme de sélection des pods via les labels.

---

## 1. Lecture du manifest

Lisez le manifest de l'objet service :

```bash
```

---

## 2. Création du service

Créez le service :

```bash
```

---

## 3. Interaction avec le service

Listez les instances :

```bash
```

Prenez l'une des IPs externes et connectez-vous :

```bash
curl -k https://<EXTERNAL_IP>:31000
```

* Pourquoi la requête ne fonctionne-t-elle pas ?

Inspectez le service :

```bash
```

* Combien y a-t-il d'endpoints au service ?

---

## 4. Lister les pods par labels

Listez les pods par labels.

---

## 5. Labellisation d'un pod

On va labelliser un pod :

```bash
kubectl label pods secure-monolith "secure=enabled"
```

Et maintenant ?

```bash
kubectl describe services monolith
```

---
