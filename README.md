# keycloak-docker-compose

Project just for run keycloak on docker in mode http

#gerando certificado linux
Instalando o certbot: sudo snap install --classic certbot
Gerando o certificado: sudo certbot certonly --standalone -d domain.com

obs.: o dominio tem que estar apontando(DNS tipo A for ip)
para o servidor que deseja gerar o certificado Open /etc/letsencrypt/live/domain.com directory.

Gerar o .p12: openssl pkcs12 -export -in fullchain.pem -inkey privkey.pem -out keystore.p12 -name tomcat -CAfile chain.pem -caname root
senha: your-secret-pass

Ativar renovacao automatica: sudo certbot renew --dry-run
Para forcar renovacao: certbot renew --force-renewal

Configure does file then..

sudo docker-compose  up&


References
https://keycloak.discourse.group/t/need-help-to-start-with-keycloak-19-andpostgres-in-docker-compose/16749
https://www.keycloak.org/server/containers
