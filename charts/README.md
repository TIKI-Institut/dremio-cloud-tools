# Dremio charts

## Login

run the following command to login to your registry:

```bash
make login <your-registry>
# Login Succeeded
```

## Package

create a Helm chart package with cmd:

```bash
make package
# Successfully packaged chart and saved it to: ...dremio-cloud-tools/charts/dremio-2.0.0-tiki.tgz
```

## Publish

To publish the Helm chart package, then run the following command:

```bash
make publish REGISTRY=oci://<your-registry>
# Pushed: <your-registry>/dremio:2.0.0-tiki
```