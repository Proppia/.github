# Cómo contribuir

Gracias por considerar contribuir a un repositorio de Proppia. Este documento cubre lo esencial para colaboradores invitados a un repositorio específico.

## Acceso al repositorio

Si llegaste aquí desde un repositorio al que fuiste invitado como colaborador, tu contacto en Proppia gestiona tus permisos. Escríbele si no puedes ver el repositorio o no puedes hacer push.

## Commit signing (obligatorio)

Todos los commits en repositorios de Proppia deben estar firmados criptográficamente. Esta es una regla aplicada automáticamente en todas las ramas — un commit sin firmar es rechazado por el servidor.

La firma garantiza la veracidad del autor de cada commit.

### Opción A — SSH signing (recomendado si ya usas SSH para push)

```bash
git config --global gpg.format ssh
git config --global user.signingkey ~/.ssh/id_ed25519.pub
git config --global commit.gpgsign true
git config --global tag.gpgsign true
```

Luego agrega la misma SSH key como **signing key** en GitHub:

Settings → SSH and GPG keys → New SSH key → Key type: `Signing Key`.

### Opción B — GPG signing

```bash
# Generar GPG key
gpg --full-generate-key
# (RSA 4096, expiración a elección, email de GitHub)

# Listar keys
gpg --list-secret-keys --keyid-format=long

# Configurar git
git config --global user.signingkey <KEY-ID>
git config --global commit.gpgsign true

# Exportar la pública para GitHub
gpg --armor --export <KEY-ID>
```

Agrega el output en GitHub: Settings → SSH and GPG keys → New GPG key.

### Verificar que funciona

```bash
git commit -m "Test signing"
git log --show-signature -1
```

Debe mostrar `Good signature`. En GitHub, los commits firmados aparecen con un badge **Verified** junto al hash.

## Convenciones de branching

Cuando trabajes en un issue asignado, usa el nombre de branch que tu contacto en Proppia te indique. Si el repositorio sigue una convención automática (por ejemplo, generada por un sistema de tracking), respétala — es parte de la trazabilidad interna.

Si no tienes indicación específica, usa `kebab-case` con un nombre descriptivo:

```
agregar-validacion-email
corregir-bug-checkout
```

## Workflow de cambios

1. Crea un branch a partir de `main` (o la rama de integración que el proyecto use).
2. Haz commits firmados, claros, en imperativo.
3. Abre un pull request cuando el trabajo esté listo para revisión.
4. Completa el template del PR — incluye contexto suficiente para quien revise.
5. Espera review y checks verdes antes de mergear.

## Estrategia de merge

El default en repositorios de Proppia es **squash and merge** para mantener la historia de `main` limpia. Casos específicos pueden usar merge commits; seguir la indicación del owner del repositorio.

## Reportar un problema

Para bugs o sugerencias técnicas, abre un issue si el repositorio los acepta, o escribe a tu contacto en Proppia.

Para vulnerabilidades de seguridad, sigue el proceso descrito en [`SECURITY.md`](./SECURITY.md) — no las abras como issue público.

---

**Hazlo tuyo, hazlo Proppia.**
