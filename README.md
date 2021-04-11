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
- VPC Padrão, cria uma VPC padrao com 3 subnets, cada uma em uma regiao de disponibilidade diferente

# Security Group
- como se fosse o firewall
- recomendado criar especifico para cada tecnologia
- por padrão vem co entrada toda bloqueada e saida toda liberada
- por padrão ping não é liberado
- pode liberar acesso de outros security groups
- recomendado sempre por uma descrição
