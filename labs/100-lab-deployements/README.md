# TP Kubernetes — Deployment

## Objectif

Créer et gérer des **Deployments** Kubernetes, comprendre le mécanisme de scaling et la gestion des réplicas.

---

## 1. Déploiement du service Auth

Créez le déploiement :

```bash
kubectl create -f auth.yaml
```

```bash
kubectl describe deployments auth
```

Créez le service correspondant :

```bash
```

---

## 2. Déploiement du service Hello

Idem pour le service Hello :

```bash
```

```bash
```

```bash
```

---

## 3. Déploiement du service Frontend

Et pour le service Frontend :

```bash
kubectl create configmap nginx-frontend-conf --from-file=configuration/nginx/
```

```bash
```

```bash
```

### Questions

* Comment le frontend a accès au service auth et hello ?

---

## 4. Scaling horizontal

On va maintenant augmenter le nombre de pods :

```bash
kubectl scale deployments hello --replicas=3
```

```bash
kubectl describe deployments hello
```

```bash
kubectl get pods
```

```bash
kubectl get replicasets
```

---

## 5. Modification du nombre de réplicas

Éditez le service frontend pour scaler à 2 replicas :

```bash
vim frontend.yaml
```

Déployer à nouveau le frontend.

---
