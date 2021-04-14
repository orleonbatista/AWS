# AWS
## Tipos de cloud computing
- IaaS : Infraestrutura como serviço, componentes básicos da IT na nuvem, ex aws, gcp e azure
- Paas : Plataforma como Serviço, nao precisa gerenciar infra, ex: go daddy, heruku etc
- SaaS : Software como serviço, exemplo GMAIL

## Cloud Deployments
- Public Cloud : aws, gpc, azure (onde qualquer um pode adquirir e utilizar)
- Hybrid : Junção entre public e private
- Private Cloud (on premise) : significa que você gerencia o próprio datacenter 

## AWS Services
- Aproximadamente mais de 200 serviços

## Global Infrastructure
- Regions - São os paises (us, br, etc)
- Avaliability zone - Data center dentro das regiões

# EC2 
## Tipos de instâncias EC2 - https://aws.amazon.com/pt/ec2/instance-types/
- São os tipos de maquinas que tem disponiveis para utilizar
- para as maquinas se conversarem dentro da rede interna, se utiliza o private IP, para comunicar fora da rede usa o Public IP
#### Windows
- para pegar acesso, selecionar a instância e clicar para pegar a senha
- para acessar internet, precisa alterar Local Server > IE enhanced Security
#### Linux
- Permitir SSH porta 22 para conseguir acessar
- Atualizar sudo su (alterar privilegio) > yum update -y (atualizar a maquina)
- subir serviço httpd : yum install httpd -y , service httpd start (subir httpd), acessar pasta cd/var/www/html colocar index la

### Volumes EBS (Elastic Block Store)
- É o disco virtual da nossa maquina na EC2 - chamado de EBS 
- facil upgrade
- Dois tipos de disco
- - HDD - mais recomendados para armazenamento de arquivos, baixa IOPS
- - SSD - mais utilizado normalmente para aplicações por ser mais rápido, rapida IOPS (IOI e GPS, IOI é o mais rapido e muito melhor)

## EC2 Pricing - https://aws.amazon.com/pt/ec2/pricing/
- Toda cobrança na AWS é feita por segundo
- 4 tipos :
- - On-demand - de acordo com a necessidade $$$
- - Reserved - você já tem a quantidade de processamento, memoria que vai precisar, 90% mais barato.
- - - 2 tipos reserved:
- - - - Standard : 75% mais barato, problema é que se voce escolhe o tipo de maquina, não consegue fazer o upgrade
- - - - Convertable : 50% mais barato, consegue mudar de maquina
- - Spot - Stock Market, você da uma oferta, mais ultilizado em um curto espaço de tempo
- - Dedicated host - mais seguro, nele você "aluga" o hardware, com dois tipos:
- - - on demand
- - - reserved 

## VPC
- O Objetivo da VPC é provisionar uma rede isolada, mesmo considerando que estamos utilizando um ambiente na internet
- cada VPC pode ter varias sub-redes, o que ajuda na organização da topologia do seu projeto
- VPC Padrão, cria uma VPC padrao com 3 subnets, cada uma em uma regiao de disponibilidade diferente

# Security Group
- como se fosse o firewall
- recomendado criar especifico para cada tecnologia
- por padrão vem co entrada toda bloqueada e saida toda liberada
- por padrão ping não é liberado
- pode liberar acesso de outros security groups
- recomendado sempre por uma descrição

# CloudWatch
- Utilizado para monitoração e gerar metricas de recursos
- ja vem ativo por default para todos serviços
- colocar um agente, para esse agente pegar os logs das maquinas e jogar para o cloud watch
#### Metricas
- Monitorações
#### Dashboards
#### Alertas
- toda vez que alcance 80% dentro de 5 minutos mandar um alerta
- não paga nada a mais por esses alertas
#### Eventos
- toda vez que um servidor foi criado, enviar um email por exemplo
#### Logs
- possivel criar um alerta criado com base de algum log
#### Escopo Regional
#### Métricas customizadas

# Load Balancer (ELB)
- Faz health check
- Existem 3 tipos:
#### Application
- Mais inteligente, ele enxerga a layer 7  (OSI)
- Conseguimos ver o que o usuário está acessando no webservice e direcionar a partir dessa informação
#### Network
- Camada 4, é possivel dividir a partir do tráfego
#### Classic
- Junção do network e do application, foi o primeiro criado pela AWS e não tem muita necessidade de utiliza-lo

# AutoScaling
- Cria novas instâncias de acordo com o tráfego de forma automática
- Quando o tráfego diminui, ele também diminui as maquinas
- possivel subir maquinas iguais
- possivel colocar o máximo de maquinas
#### 5 tipos de autoScaling
- All times : manter as instâncias atuais sempre a todo tempo
- Scale manually : define manualmente quantas instâncias (não muito usado)
- Schedule : consegue agendar por exemplo, segunda a sexta 5 maquinas, e sabado e domingo 2 maquinas, também possivel por hora
- on demand : de acordo com o processamento, passou do processamento é adicionado as maquinas
- predictive : pega metricas de outros serviços e manda para o autoscaling

# S3 - Simple Storage Service https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html
- Sistema de armazenamento de videos, fotos, arquivos, onde podemos fazer o upload e download de objetos
- Guardamos os arquivos dentro de um bucket
- nome do bucket tem que ser unico no planeta
- não é possivel instalar O.S
- arquivos de 0 bites até 5 TB, por arquivo
- não possui limite bucket
