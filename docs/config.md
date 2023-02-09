# Konfiguration

## Opsætning

Følgende skal være installeret for at kunne følge denne guide på eget system:

* Visual Studio Code (vscode)
* Docker Desktop eller Docker Engine (docker)

Herefter kan projektet hentes vha `git clone https://github.com/slamidtfyn/dev-guide-2-k8s.git` og åbnes med vscode


eller det kan åbnes direkte som et [codespace fra github](https://docs.github.com/en/codespaces/developing-in-codespaces/creating-a-codespace-for-a-repository)

## Test opsætning

Når projektet er åbnet og initaliseret - det kan godt tage et stykke tid første gang, kan der i et vscode terminal vindue kontrolleres at alt er klart:

```bash
$ minikube status
minikube
type: Control Plane
host: Running
kubelet: Running
apiserver: Running
kubeconfig: Configured

$ kubectl get pods
No resources found in default namespace.
```

Den første kommando viser at minikube er startet. Den næste kommando henter status for pods i minikube clusteret

[Forrige side](../readme.md) | [Næste side](1-hello-world.md)