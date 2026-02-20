# COMANDOS GIT — DOCUMENTACIÓN Y GUÍA DE USO

Guía práctica para consultar cambios, comparar ramas, copiar archivos modificados y mantener ramas actualizadas en proyectos con Git.

**Documentación oficial de referencia:**  
https://www.atlassian.com/es/git/tutorials/setting-up-a-repository/git-clone

---

# GIT — CONSULTA, COMPARACIÓN Y COPIA DE ARCHIVOS

Sección enfocada en inspección de cambios, comparación entre ramas/commits y automatización de copiado de archivos modificados.

---

## Ver cambios desde la última confirmación (commit actual sin confirmar)

```bash
git diff

GIT — CONSULTA, COMPARACIÓN Y COPIA DE ARCHIVOS
Ver cambios desde la última confirmación

```bash
git diff
```

## Obtener la ruta de los archivos modificados en el último commit

```bash
git diff --name-only HEAD~1 HEAD
```

## Ver diferencias entre dos ramas específicas

```bash
git diff --name-only release/V34.0.0..development
```

## Comparar tu rama fix/MA2019-1743 con master

```bash
git diff master...fix/MA2019-1743 --name-only
```

## Copiar archivos modificados entre master y tu rama

```bash
for name in $(git diff master...fix/MA2019-1743 --name-only --pretty); do
rsync -R "$name" "/Users/dev-hypersoft/Documents/FRONT";
done
```

## Copiar archivos del último commit

```bash
for name in $(git diff --name-only HEAD~1..HEAD); do
rsync -R "$name" "/Users/dev-hypersoft/Documents/FRONT";
done
```

##  archivos modificados en las últimas 2 horas

```bash
for name in $(git diff HEAD "@{2.hours.ago}" --name-only); do
rsync -R "$name" "/Users/dev-hypersoft/Documents/FRONT";
done
```

## Copiar archivos modificados el día de hoy

```bash
for name in $(git log --since="midnight" --pretty=format: --name-only --diff-filter=AM release/v34.0.0); do
rsync -R "$name" "/Users/dev-hypersoft/Documents/FRONT";
done
```

## Ver diferencias del último día

```bash
git diff --name-only $(git rev-list -n 1 --before="1 days ago" release/V34.0.0)..release/V34.0.0
```

## Ver diferencia por cantidad de commits

```bash
git diff --name-only HEAD~6..HEAD
```

## Copiar archivos de los últimos 4 commits

```bash
for name in $(git diff --name-only HEAD~4..HEAD | sort -u); do
rsync -R "$name" "/Users/dev-hypersoft/Documents/Envio_Archivos/front";
done
```

## Comparar un commit específico contra su padre

```bash
git diff 63ccc97^ 63ccc97 --name-only --pretty
```

## Actualizar rama local

```bash
git pull --rebase --autostash
git push
```

## Buenas prácticas antes de trabajar con ramas
## Actualizar ramas base

```bash
git checkout master && git pull
git checkout development && git pull
```

## Crear nueva rama

```bash
git checkout -b fix/MA2019-1743
```

## Forzar push con seguridad

```bash
git push --force-with-lease
```
# AWS S3 — DESPLIEGUE Y SINCRONIZACIÓN

## Ver buckets disponibles

```bash
aws s3 ls
```

## Listar contenido de un bucket

```bash
aws s3 ls s3://dev.hypersoft.co
```

## Sincronizar carpeta local hacia S3

```bash
aws s3 sync "/Users/dev-hypersoft/Documents/FRONT/public" s3://dev.hypersoft.co --exact-timestamps
```

## Simular sincronización

```bash
aws s3 sync "/Users/dev-hypersoft/Documents/FRONT/public" s3://dev.hypersoft.co --dryrun
```

## Sincronizar eliminando archivos sobrantes

```bash
aws s3 sync "/Users/dev-hypersoft/Documents/FRONT/public" s3://dev.hypersoft.co --delete --exact-timestamps
```

## Subir un archivo puntual

```bash
aws s3 cp index.html s3://dev.hypersoft.co/index.html
```

## Descargar archivos desde S3

```bash
aws s3 sync s3://dev.hypersoft.co ./backup-s3
```

## Eliminar un archivo

```bash
aws s3 rm s3://dev.hypersoft.co/archivo.js
```

## Eliminar una carpeta completa

```bash
aws s3 rm s3://dev.hypersoft.co/carpeta --recursive
```

## Validar identidad AWS activa

```bash
aws sts get-caller-identity
```
