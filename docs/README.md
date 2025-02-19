# Documentação sobre Docker

Este diretório contém anotações e explicações sobre Docker.

## O que é Docker?

Docker é uma plataforma criada para construir, rodar e transferir aplicações do seu ambiente de teste ou desenvolvimento para o ambiente em produção.

## O que é um container?

Um container é um pacote de software que contém tudo o que é necessário para executar uma aplicação, como bibliotecas, dependências e código.

## Qual a utilidade dos containers no Docker?

Os containers são úteis para desenvolver, implantar e executar aplicações em diferentes sistemas de forma leve e portátil.

## Bare Metal vs VMs (Virtual Machine) vs Containers

- **Bare Metal**: Servidor físico direto, sem virtualização, com máximo desempenho e controle, mas menos flexível.
- **VM (Máquina Virtual)**: Emula um sistema operacional completo sobre um hypervisor, oferecendo isolamento e flexibilidade, mas com overhead.
- **Container**: Compartilha o mesmo kernel do sistema operacional, sendo leve, rápido e eficiente, mas com menos isolamento que VMs.

## Docker e OCI (Open Container Initiative)

- **Docker**: Plataforma para criar, empacotar, distribuir e executar containers, com ferramentas próprias como Docker CLI e Docker Hub.
- **OCI (Open Container Initiative)**: Padrão aberto que define especificações para runtimes e formatos de imagens de containers, garantindo compatibilidade entre diferentes tecnologias.

### Qual o melhor entre eles?

- Para **desenvolvimento e facilidade** → Docker é melhor, pois oferece uma experiência completa e amigável.
- Para **produção em ambientes complexos** (ex.: Kubernetes) → OCI é essencial, pois permite usar diversos runtimes além do Docker.

## Principais Tecnologias Subjacentes do Docker

- **Namespaces (Linux)**: Isolam processos para que cada container tenha seu próprio ambiente.
  - Exemplos: PID (processos), NET (rede), MNT (sistema de arquivos), UTS (hostname), IPC (comunicação).
- **Cgroups (Control Groups)**: Controlam e limitam o uso de recursos (CPU, memória, I/O, etc.) pelos containers.
- **UnionFS (Sistema de Arquivos em Camadas)**: Permite imagens leves e reutilizáveis através de camadas imutáveis.
  - Tecnologias usadas: AUFS, OverlayFS, Btrfs, ZFS.
- **Container Runtime**: Responsável por criar e gerenciar containers.
  - Docker usa **containerd**, que por sua vez usa **runc** (compatível com OCI).
- **Bridge Networking e Virtual Ethernet (veth)**: Permitem comunicação entre containers e com o host via redes virtuais.
- **Docker Registry (Ex.: Docker Hub, Harbor, Quay)**: Armazena e distribui imagens de containers.

### Resumo

Docker combina:
- **Namespaces e Cgroups** para isolamento;
- **UnionFS** para eficiência;
- **containerd/runc** para execução;
- **Redes virtuais** para conectividade.
