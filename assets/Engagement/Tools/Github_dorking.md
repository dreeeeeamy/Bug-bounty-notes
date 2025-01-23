### Github dorking

**Descripción:** GitHub puede ser una fuente valiosa para encontrar credenciales y configuraciones expuestas.

En esta sección encontrarás términos clave y ejemplos para buscar y explotar configuraciones sensibles, credenciales y archivos críticos durante un engagement de bug bounty. Se organizan por categorías para facilitar su referencia.

A continuación, se explica cómo utilizar el panel de búsqueda de GitHub para encontrar datos sensibles de un objetivo.

---

**Ejemplo de uso:**
```bash
org:target.com language:python password
```
Este filtro buscará archivos .py en la organización target.com que contengan la palabra clave password.

## Índice
- [Credenciales y configuraciones generales](#credenciales-y-configuraciones-generales)
- [Claves y tokens](#claves-y-tokens)
- [Archivos sensibles](#archivos-sensibles)
- [Servicios específicos](#servicios-específicos)
  - [Amazon Web Services (AWS)](#amazon-web-services-aws)
  - [Google Cloud Platform (GCP)](#google-cloud-platform-gcp)
  - [Azure](#azure)
  - [Otros servicios cloud](#otros-servicios-cloud)
- [Bases de datos](#bases-de-datos)
- [FTP, SSH y redes](#ftp-ssh-y-redes)
- [Emails y servicios de mensajería](#emails-y-servicios-de-mensajería)
- [Otros ejemplos específicos](#otros-ejemplos-específicos)
- [Otros términos genéricos útiles](#otros-términos-genéricos-útiles)

---

### Credenciales y configuraciones generales
Busca términos comunes asociados con contraseñas y configuraciones predeterminadas:
- `password`
- `pass`
- `pwd`
- `auth`
- `login`
- `credentials`
- `username`
- `user_password`
- `admin_password`
- `default_password`

---

### Claves y tokens
Identifica claves y tokens que puedan permitir acceso a servicios o datos:
- `api_key`
- `apikey`
- `api_secret`
- `access_token`
- `secret_token`
- `auth_token`
- `oauth_token`
- `client_secret`
- `client_id`
- `jwt_secret`
- `bearer_token`
- `private_key`
- `public_key`

---

### Archivos sensibles
Detecta archivos que suelen contener información confidencial:
- `.env`
- `.yml`
- `.config`
- `.ini`
- `.json`
- `.pem`
- `id_rsa`
- `config.php`
- `settings.py`
- `web.config`
- `application.properties`

---

### Servicios específicos

#### Amazon Web Services (AWS)
Claves y configuraciones comunes para AWS:
- `aws_access_key`
- `aws_access_key_id`
- `aws_secret_access_key`
- `aws_session_token`

#### Google Cloud Platform (GCP)
Términos relacionados con GCP:
- `gcp_key`
- `gcp_project`
- `google_api_key`
- `google_application_credentials`

#### Azure
Credenciales y claves para Azure:
- `azure_storage_account`
- `azure_storage_key`
- `azure_client_id`
- `azure_client_secret`

#### Otros servicios cloud
Claves comunes para servicios cloud:
- `s3_bucket`
- `digitalocean_token`
- `linode_token`

---

### Bases de datos
Contraseñas y configuraciones de bases de datos:
- `db_user`
- `db_password`
- `database_password`
- `mysql_password`
- `postgres_password`
- `mongo_uri`
- `db_host`

---

### FTP, SSH y redes
Credenciales y configuraciones de red:
- `ftp_user`
- `ftp_password`
- `ssh_password`
- `ssh_key`
- `vpn_password`
- `rsa_private_key`

---

### Emails y servicios de mensajería
Claves para servicios de correo y mensajería:
- `smtp_password`
- `email_password`
- `imap_password`
- `twilio_auth_token`
- `slack_token`
- `telegram_bot_token`

---

### Otros ejemplos específicos
Términos relacionados con servicios populares:
- `stripe_api_key`
- `paypal_secret`
- `github_token`
- `gitlab_token`
- `bitbucket_password`
- `npm_token`
- `docker_password`
- `api_id`
- `firebase_config`

---

### Otros términos genéricos útiles
Busca términos genéricos relacionados con la seguridad:
- `master_key`
- `secure_key`
- `encryption_key`
- `app_key`
- `keystore_password`
- `backup_password`
- `recovery_key`
