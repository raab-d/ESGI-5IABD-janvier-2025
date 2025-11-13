# TP Kubernetes — ConfigMap, Secret & Injection de fichiers

## Objectif

Manipuler des objets **ConfigMap** et **Secret**, les injecter dans un pod, puis interagir avec ce pod exposé en local.

---

## 1. Création d'une ConfigMap

Créez une ConfigMap à partir d’un fichier de configuration :

```bash
kubectl create configmap nginx-proxy-conf --from-file=nginx/proxy.conf
```

Inspectez son contenu :

```bash
kubectl describe configmaps nginx-proxy-conf
```

### Questions

* Combien y a-t-il d’éléments dans la ConfigMap `nginx-proxy-conf` ?
* Quel est le nom de ces éléments ?

---

## 2. Création d’un Secret

Créez un secret à partir d’un dossier contenant des certificats :

```bash
kubectl create secret generic tls-certs --from-file=tls/
```

Inspectez son contenu :

```bash
kubectl describe secrets tls-certs
```

### Questions

* Combien y a-t-il d’éléments dans le secret `tls-certs` ?
* Quel est le nom de ces éléments ?

---

## 3. Injection de fichiers dans un pod

Affichez le contenu du fichier de configuration du pod :

```bash
cat pod/secure-monolith.yaml
```

### Questions

* Comment le **secret** est-il injecté dans le pod ?
* Comment la **ConfigMap** est-elle injectée dans le pod ?

---

## 4. Création et test du pod

Créez le pod à partir du fichier YAML :

```bash
kubectl create -f pod/secure-monolith.yaml
```

Exposez le port 443 du pod sur votre machine locale :

```bash
kubectl port-forward secure-monolith 10443:443
```

Effectuez une requête HTTPS avec `curl` :

```bash
curl --cacert tls/ca.pem https://127.0.0.1:10443
```
