create docint instance in azure f0 free tier

ai-studio document intellignece service endpoint is http://localhost:5000

e.g. endpoints
```
http://localhost:5000/api-docs/index.html
```

setup
```bash
mkdir shared logs onprem_folder onprem_db
```
run
```bash
podman compose down -v --remove-orphans -t 20
podman compose --env-file .env up -d 
```

```
NGINX_CONF_FILE=/home/vagrant/dev/ai/docint/nginx.conf

# Form Recognizer Custom Template container
FORM_RECOGNIZER_KEY=<key>
FORM_RECOGNIZER_ENDPOINT_URI=https://<name>.cognitiveservices.azure.com/

# Shared and output mount paths for custom-template
SHARED_MOUNT_PATH=/home/vagrant/dev/ai/docint/shared
OUTPUT_MOUNT_PATH=/home/vagrant/dev/ai/docint/logs

# AI Studio container
FILE_MOUNT_PATH=/home/vagrant/dev/ai/docint/onprem_folder
DB_MOUNT_PATH=/home/vagrant/dev/ai/docint/onprem_db
```
