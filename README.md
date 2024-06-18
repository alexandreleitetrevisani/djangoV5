projeto django com docker mais nginx como load balancer seção 54

ETAPAS DO PROCESSO DE DEPLOY:

1 - Imagens e containers ok, docker-compose up -d rodando normalmemnte no localhost;

2 - acessar a conta da AWS e adiquirir em "security credencial e ID e o SECRET, e region"

3 - docker-machine create --driver amazonec2 --amazonec2-region "" fusion

4 - docker-machine env fusion

4 - eval $(docker-machine env fusion)

5- ir em instancia em execução fusion no ec2 da AWS, em grupos de segurança configurar a porta HTTP 80 de entrada. (há um servidor web)

6 - docker-compose up -d. Subindo a aplicação

7 - criando as tabelas lá na nuvem --> docker exec -it fusion1 python manage.py migrate

8 - ver se a app está rodando com o IPV4 público disponível na internet

9 - após atribuição de domínio usando o serviço de gerenciamento de DNS da AWS chamado Route 53, acessar a app no endereço ""
