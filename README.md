# homelab-k3s Homelab: A GitOps-Powered K3s Cluster
Welcome to my homelab repository, where I manage my entire homelab infrastructure using a GitOps approach with Kubernetes (K3s) and ArgoCD. This repository serves as the single source of truth for all my applications, configurations, and infrastructure definitions.

🌟 Key Features
Declarative & Version-Controlled: The entire homelab is defined as code, version-controlled with Git, and managed through pull requests.

Fully Automated with GitOps: ArgoCD automatically syncs the state of the cluster with the manifests in this repository.

Lightweight & Efficient: K3s provides a lightweight yet powerful Kubernetes distribution, perfect for homelab environments.

Comprehensive Application Stack: A wide range of self-hosted applications for media, home automation, and development.

Secure & Scalable: Using modern tools and best practices to ensure a secure and scalable homelab setup.

🏛️ Architecture
At the core of this homelab is a K3s cluster with a GitOps-centric architecture. Here's a high-level overview of the components and how they interact:

Kubernetes (K3s): The container orchestration platform that runs all the applications.

ArgoCD: The GitOps continuous delivery tool that monitors the repository and applies changes to the cluster.

Traefik: The ingress controller that manages external access to the applications.

SMB CSI Driver: Provides persistent storage for stateful applications using an SMB share.

MetalLB: A network load-balancer for bare-metal Kubernetes clusters.

GitOps with ArgoCD
ArgoCD is the backbone of this homelab, implementing the GitOps methodology. The cluster/apps/argo-apps/root-app.yaml file defines the "app of apps" pattern, where a single ArgoCD application manages all the other applications in the cluster. This provides a centralized and automated way to manage the entire application stack.

Networking with Traefik and MetalLB
Traefik is used as the Ingress controller to expose services to the outside world. It is configured to use a LoadBalancer service, with a static IP assigned by MetalLB. This allows for easy and reliable access to the applications via subdomains.

🚀 Application Stack
This homelab runs a variety of self-hosted applications, all managed by ArgoCD. Here's a list of the applications and their configurations:

Application	Description	Namespace	Ingress Hostname
AdGuard Home	Network-wide ad-blocker	networking	adguard.homelab.local
Homepage	A highly customizable application dashboard	homepage	homepage.homelab.local
qBittorrent	A popular torrent client	media-stack	downloads.homelab.local
Sonarr	TV show management	media-stack	series.homelab.local
Radarr	Movie management	media-stack	movies.homelab.local
Lidarr	Music management	media-stack	music.homelab.local
Bazarr	Subtitle management	media-stack	bazarr.homelab.local
Prowlarr	Indexer manager for *arr stack	media-stack	prowlarr.homelab.local
Overseerr	Request management for media	media-stack	requests.homelab.local
n8n	Workflow automation	n8n	n8n.homelab.local
pgAdmin	PostgreSQL administration tool	database	pgadmin.homelab.local
Readeck	A read-it-later service	readeck	readeck.homelab.local
Commafeed	A self-hosted RSS reader	media-stack	rss.homelab.local
Prometheus	Monitoring and alerting	monitoring	prometheus.homelab.local
Grafana	Visualization and analytics	monitoring	grafana.homelab.local
Traefik Dashboard	Traefik's dashboard	traefik-system	traefik.homelab.local

Exportar a Hojas de cálculo
🔧 Repository Structure
The repository is structured to be easily managed and scaled. Here's a breakdown of the key directories:

cluster/apps: Contains the Kubernetes manifests for all the applications, organized by namespace and application name.

cluster/base: Includes base configurations for the cluster, such as StorageClasses.

cluster/apps/argo-apps: Holds the ArgoCD Application definitions that manage all the other applications.

💡 Future Plans
This homelab is an ever-evolving project. Here are some of the things I'm planning to add in the future:

Implement SSL/TLS with Let's Encrypt: Secure all the services with valid SSL certificates.

Add a Service Mesh: Explore using Linkerd or Istio for enhanced observability and security.

Integrate SOPS for Secrets Management: Encrypt secrets in the Git repository for better security.

Expand the Monitoring Stack: Add Loki for log aggregation and Tempo for distributed tracing.

🤖 AI Assistance
This project was brought to life with the assistance of several AI-powered tools. From generating boilerplate code and debugging complex configurations to creating documentation, AI has been an invaluable partner in this journey. This allowed me to focus on the architecture and the overall vision of the project, while the AI handled many of the tedious and time-consuming tasks.

🙏 Acknowledgements
A huge thanks to the open-source community and all the developers who create and maintain the amazing tools used in this project. This homelab wouldn't be possible without their hard work and dedication.