# 0192163-javier-quintero-iac-aws

Proyecto de Infraestructura como Código (IaC) para la asignatura **Cloud Computing** — Ingeniería de Sistemas, UFPS Ocaña.

**Estudiante:** Javier Quintero Clavijo — 0192163
**Docente:** Wilder Andrés Duarte Neira

## Descripción

Cada `push` a la rama `main` ejecuta un flujo de GitHub Actions que despliega con AWS CloudFormation:

- Una instancia **EC2** con Amazon Linux 2023.
- Un **Security Group** que solo permite HTTP (puerto 80); no se habilita SSH.
- Un servidor **Apache** con una página HTML personalizada, creado mediante **User Data**.

## Estructura

```
.
├── .github/
│   └── workflows/
│       └── deploy.yml      # Flujo de GitHub Actions
├── templates/
│   └── template.yaml       # Plantilla de CloudFormation
└── README.md
```

## Configuración

| Tipo | Nombre | Uso |
|---|---|---|
| Secreto | `AWS_ACCESS_KEY_ID` | Clave de acceso de AWS |
| Secreto | `AWS_SECRET_ACCESS_KEY` | Clave secreta de AWS |
| Variable | `AWS_REGION` | Región del despliegue (`us-east-1`) |
| Variable | `SUBNET_ID` | Subred pública donde se crea la instancia |

## Acceso al sitio

Stack: `proyecto-web-iac`

Repositorio: https://github.com/javierquinterocl/0192163-javier-quintero-iac-aws

Sitio web: **http://IP_PUBLICA** (se actualiza tras el despliegue)
