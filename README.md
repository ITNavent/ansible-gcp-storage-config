ansible-gcp-config-storage
=========

Este role crea directorios dentro de un storage de GCP.

Actualmente no usa la autenticacion comun de GCP con el key file en formato JSON, sino que usa las claves de la Interoperability API, que son por usuario de proyecto, no por proyecto.

Las claves de la Interoperability API se pueden encontrar en la seccion "Interoperability" en las opciones de los bucket de GCP. Ejemplo: console.cloud.google.com/storage/settings?organizationId=26359750934&project=ricrm-stg



Requirements
------------

- Ubuntu
- Ansible 2.4



Role Variables
--------------

```
storage_name: name of the storage
storage_directories: 
  - "path/of/directory/in/storage/1"
  - "path/of/directory/in/storage/2"
  - "..."
storage_access_key: "Access Key" of interoperability API
storage_secret_key: "Secret Key" of interoperability API
```

Example Playbook
----------------
```
#example to create directories in a bucket
storage_name: "ricrm-stg-bucket"
storage_access_key: "{{lookup('env','GS_ACCESS_KEY_ID')}}"
storage_secret_key: "{{lookup('env','GS_SECRET_ACCESS_KEY')}}"
storage_directories:
  - "/data"
  - "/imagenes"
  - "/imagenes2"
  - "/imagenes3/avisos/2/00"
  - "/imagenes3/avisos/9"
  - "/imagenes3/avisos/11"
  - "/imagenes3/avisos/13"
  - "/imagenes3/avisos/14"
  - "/imagenes3/avisos/18"
  - "/imagenes3/avisos/20"
  - "/data/shared_empresas"
  - "/iw01/avisos/2/01"
  - "/iw01/avisos/2/09"
  - "/iw02/avisos/2/10"
```



Author Information
------------------

Augusto Mendoza (amendoza@navent.com)

