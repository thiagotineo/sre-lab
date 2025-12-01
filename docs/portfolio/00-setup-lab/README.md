# Infra: Setup local SRE Lab (Docker + Minikube + Helm)

**Descrição:**  
Instalei Docker 29.1.1, Minikube 1.x e Helm 3.x em ambiente Ubuntu 25.10.  
Motivo: simular produção local com um control plane Kubernetes real e ferramentas de empacotamento e observabilidade.  
Este setup serve como base para práticas SRE (deploy, observabilidade, confiabilidade e automação).

**Decisões:**  
- **Docker:** isolar serviços e reproduzir o ambiente de produção com containers.  
- **Minikube:** escolhido por fornecer cluster Kubernetes real de um nó, com baixo custo de recursos e fácil reinicialização.  
- **Helm:** facilitar instalação e atualização de stacks completas (como Prometheus/Grafana).  

**Problemas encontrados e soluções:**  
- **Permissão Docker:** `docker ps` exigia `sudo`.  
  - Solução: adicionei o usuário ao grupo docker:  
    ```bash
    sudo usermod -aG docker $USER && newgrp docker
    ```
- **Driver Minikube:** erro “docker driver not found”.  
  - Solução: reiniciei o Docker e executei:  
    ```bash
    minikube delete && minikube start --driver=docker
    ```
- **Helm não encontrado:** faltava PATH após instalação manual.  
  - Solução: adicionado ao `.bashrc`:  
    ```bash
    export PATH="/usr/local/bin:$PATH"
    ```

**Comandos executados:**  
```bash
minikube start --driver=docker
minikube status
docker ps
helm version
