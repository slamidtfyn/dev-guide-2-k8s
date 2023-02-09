# Hello World

Med `kubectl` kan man oprette en deployment, hvor der angives et docker-image, samt parametre der beskriver hvordan denne deployment er skaleret.

```bash
$ kubectl create deployment hello-world --image=hello-world --replicas 3
```

Her oprettes der en deployment med 3 pods med docker image hello-world. Listen over disse pods kan ses med

```bash
$ kubectl get pods
```

For at se output fra disse pods kan der enten vises logs fra hver enkelt pod med 

```bash
$ kubectl logs <pod-navn-fra-get-pods>
```

eller for alle sammen vha label app som `kubectl create deployment` sætter til navnet på deployment

```bash
$ kubectl logs --selector app=hello-world
```

`kubectl create deployment` har mange begrænsninger og er ikke anvendelig i scenarier hvor man vil kunne starte den samme deployment på flere servere.

For bedre at kunne styre dette, kan der istedet anvendes en yaml fil der beskriver en deployment.

I [src/1-hello-world.md](../src/1-hello-world/hello-world.yml) er der et eksempel på en konfiguration der tilsvarer den manuelt oprettede hello-world deployment

Først sletter vi den tidligere oprettede deployment og laver derefter en ny på baggrund af denne konfiguration

```bash
$ kubectl delete deployment hello-world
$ kubectl apply -f src/1-hello-world/hello-world.yml
```

Med `get pods`kan man nu se at der er startet de samme 3 pods

[Forrige side](config.md) | [Næste side](2-eget-docker-image.md)

