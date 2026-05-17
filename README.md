# piscamx/.github

Repo org-level. Aloja reusable workflows de GitHub Actions y defaults org-wide
(perfil público, issue templates, etc.) para la organización [@piscamx](https://github.com/piscamx).

## Por qué existe este repo

GitHub trata de forma especial un repo llamado `.github` a nivel de organización:

- **`profile/README.md`** → aparece en `github.com/piscamx` como perfil público de la org.
- **`.github/workflows/`** → cualquier workflow aquí es invocable como *reusable workflow* desde cualquier otro repo de la org, sin configurar permisos de Actions por repo. Evita duplicar CI/CD en `piscamx/pisca-backend`, `piscamx/web`, `piscamx/mobile`, etc.

## Contenido

| Ruta | Qué es |
|------|--------|
| [`profile/README.md`](profile/README.md) | Perfil público de la org en GitHub |
| [`assets/logo-pisca.svg`](assets/logo-pisca.svg) | Logo placeholder (reemplazar con SVG final) |

## Reusable workflows

Todavía no hay workflows compartidos. Cuando se creen, irán en `.github/workflows/`
y se invocarán desde los repos de la org así:

```yaml
jobs:
  deploy:
    uses: piscamx/.github/.github/workflows/<workflow>.yml@main
    with:
      service: pisca-backend
    secrets:
      AWS_ROLE_ARN: ${{ secrets.AWS_ROLE_ARN }}
```

## Relacionado

- Stack e infra: [`piscamx/pisca-backend`](https://github.com/piscamx/pisca-backend)
- App web: [`piscamx/web`](https://github.com/piscamx/web)
- App móvil: [`piscamx/mobile`](https://github.com/piscamx/mobile)