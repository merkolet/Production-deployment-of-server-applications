# ДЗ 2 — Keycloak
## На 6

```bash
cd 1_dev
docker compose up -d
```

http://localhost:8080, логин `kcadmin` / `kcadmin`.

## На 8

```bash
cd 2_prod
cp .env.example .env   # задать пароли
docker compose up -d --build
```

http://localhost:8080, логин `kcadmin`, пароль — `KEYCLOAK_ADMIN_PASSWORD` из `.env`.