sudo snap install amazon-ssm-agent --classic

sudo systemctl enable snap.amazon-ssm-agent.amazon-ssm-agent.service
sudo systemctl start snap.amazon-ssm-agent.amazon-ssm-agent.service

check if it is available in systems manager managed nodes

deoloy.sh
#!/bin/bash

IMAGE="uhkarthik/simple-python-flask-app:latest"

docker pull $IMAGE

docker rm -f flask-app 2>/dev/null || true

docker run -d \
  --name flask-app \
  -p 5000:5000 \
  $IMAGE
