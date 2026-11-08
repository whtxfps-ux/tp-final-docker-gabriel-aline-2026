# CloudLab — TP Final

Aplicação de demonstração com dois serviços HTTP orquestrados pelo Docker Compose:

- **Site**: página estática publicada por uma imagem personalizada baseada em Nginx.
- **Diagnóstico**: serviço `traefik/whoami`, que responde com informações da requisição HTTP.

## Pré-requisitos

- Docker Desktop instalado e em execução (ou Docker Engine com o plugin Compose).

## Executar

No PowerShell, abra esta pasta e inicie os serviços:

```powershell
docker compose up --build -d
docker compose ps
```

O primeiro início baixa as imagens necessárias e pode levar alguns minutos.

## Testar

- Site: [http://localhost:8080](http://localhost:8080)
- Serviço de diagnóstico: [http://localhost:8081](http://localhost:8081)

No PowerShell, também é possível conferir as respostas com:

```powershell
curl.exe -i http://localhost:8080
curl.exe -i http://localhost:8081
```

## Comandos para explorar

```powershell
docker compose logs -f
docker compose ps
docker compose exec site sh
```

Para encerrar e remover os contêineres e a rede criada pelo Compose:

```powershell
docker compose down
```
