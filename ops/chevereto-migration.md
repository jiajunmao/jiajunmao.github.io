# Chevereto image migration

The 289 JPEG and PNG files under `/gfs-rep/brick1/chevereto/data/images` were copied to `s3://chevereto-images/images/` on `https://minio.iungo.ink`. Their date-based paths and Chevereto thumbnail variants were preserved. The source directory remains in place as a backup.

Only `images/*` has anonymous `s3:GetObject` access. The [bucket policy](chevereto-public-read-policy.json) grants no anonymous listing, upload, or delete permission. The classification CSV, model, and other non-image files were excluded. The site gallery uses the exact 31-photo Chevereto cats album order in `data/cats.yaml`.

For future image additions, run this on `colo.srv.iungo.ink` with a securely supplied AWS credentials file:

```sh
AWS_SHARED_CREDENTIALS_FILE=/path/to/credentials \
  aws --endpoint-url https://minio.iungo.ink s3 sync \
  /gfs-rep/brick1/chevereto/data/images s3://chevereto-images/images/ \
  --exclude '*' --include '*.jpg' --include '*.png' --no-progress
```

Keep the credentials file outside this repository with mode `0600`. Do not use `--delete` while the source directory is the only backup. MinIO returned `NotImplemented` for bucket versioning on this deployment, so the retained Chevereto directory is the recovery copy.
