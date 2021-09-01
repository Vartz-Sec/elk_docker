# elk_docker

1. Create certificates
  docker-compose -f create-certs.yml run --rm create_certs
  
2. Start elasticsearch
  docker-compose -f elastic-docker-tls.yml up -d
  
3.  Generate passwords
  docker exec es01 /bin/bash -c "bin/elasticsearch-setup-passwords auto --batch --url https://es01:9200"
  
4. Save passwords

5. update elastic-docker-tls.yml and replace the password for kibana_system

6. restart all the containers
  docker-compose down && docker-compose -f elastic-docker-tls.yml up -d
