create docint instance in azure f0 free tier

ai-studio document intellignece service endpoint is nginx entry point http://localhost:5000

only endpoints in the nginx config are exposed. e.g.
```
http://localhost:5000/api-docs/index.html
```
setup
```bash
mkdir shared logs files db
```
run
```bash
podman compose down -v --remove-orphans -t 20
podman compose --env-file .env up -d 
```

```
NGINX_CONF_FILE=./nginx.conf

# Form Recognizer Custom Template container
FORM_RECOGNIZER_KEY=<key>
FORM_RECOGNIZER_ENDPOINT_URI=https://<name>.cognitiveservices.azure.com/

# Shared and output mount paths for custom-template
SHARED_MOUNT_PATH=./shared
OUTPUT_MOUNT_PATH=./logs

# AI Studio container
FILE_MOUNT_PATH=./files
DB_MOUNT_PATH=./db
```
