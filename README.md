# ecommerce-devops-lab

Projet de laboratoire DevOps : déploiement automatisé d'une application e-commerce
(frontend, backend, base de données) avec **Terraform**, **Ansible** et un pipeline
**GitHub Actions**.

## Objectifs

- Provisionner l'infrastructure avec Terraform (Infrastructure as Code)
- Configurer les serveurs et déployer l'application avec Ansible
- Automatiser les vérifications et le déploiement via GitHub Actions

## Architecture

| Composant | Outil | Rôle |
|---|---|---|
| Infrastructure | Terraform | Création des ressources (machines, réseau, règles de pare-feu) |
| Configuration | Ansible | Installation de Docker, déploiement de l'application |
| CI/CD | GitHub Actions | Validation et déploiement automatiques |

## Structure du projet

```
ecommerce-devops-lab/
├── .github/workflows/   # pipeline CI/CD
├── terraform/           # code d'infrastructure
├── ansible/             # playbooks et inventaire
├── .gitignore
└── README.md
```

## Prérequis

- Terraform
- Ansible
- Git
- Accès SSH aux machines cibles

## Utilisation

### 1. Provisionner l'infrastructure

```bash
cd terraform
terraform init
terraform plan
terraform apply
```

### 2. Configurer et déployer

```bash
cd ansible
ansible-playbook -i inventory.ini playbook.yml
```

### 3. Supprimer l'infrastructure

```bash
cd terraform
terraform destroy
```

## Pipeline CI/CD

Le workflow GitHub Actions (dossier `.github/workflows`) s'exécute à chaque push
sur la branche `main`.

## Sécurité

Les fichiers sensibles (`*.tfstate`, `terraform.tfvars`, `*.pem`) sont exclus
du dépôt via `.gitignore`.

## Auteur

Mayssa Khmiri
