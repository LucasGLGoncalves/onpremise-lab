# onpremise-lab

criar um cluster kubernetes usando contaniners individuais docker com imagem ubunto realiznado join manual

subir um registry local

subir um vault local

criar uma rede interna com wireguard

---

DOCUMENTAÇÔES UTILIZADAS
	- https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/install-kubeadm/
	- https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/create-cluster-kubeadm/
	- https://highfalutin-vulture-304.notion.site/Instala-o-com-Kubeadm-8ce4f709872342ff848a4df77e53618d

---

10.0.0.5 - ControlPlane01

10.0.0.6 - WorkerNode01

10.0.0.7 - WorkerNode02

10.0.0.8 - WorkerNode03


ssh -i ~/.ssh/Tars_machines ubuntu@10.0.0.x


Checklist
Feito - acesso ssh às maquinas

Feito - instalação container runtime (ContainerD ou ~CRI-O~)

Feito - instalação kubeadm

Feito - instalação kubelet

Feito - instalação kubectl

Feito - iniciar cluster kubernetes

Feito - join de worker nodes

Feito - instalação do CNI (Calico)

Feito - instalação metrics server

Feito - instalação kubectx e kubens

---

### METRICS SERVER
https://github.com/kubernetes-sigs/metrics-server

para ignorar a obrigatoriedade no metrics server
- wget https://github.com/kubernetes-sigs/metrics-server/releases/latest/download/components.yaml
incluir a linha "- --kubelet-insecure-tls" no deploy do metrics server e executar kubectl apply -f components.yaml

### COMANDOS METRICS SERVER

kubectl top nodes

kubectl top pod

---

### KUBECTX
https://github.com/ahmetb/kubectx/

tentar subir aplicação, registry e vault no cluster

---

Subir firewall com iptables ou configuração de ingress
