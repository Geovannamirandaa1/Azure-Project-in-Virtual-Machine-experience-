Documentação Base para o Projeto 

Criação de Virtual Machine no Azure com Terraform 

1. Introdução 

Este projeto ilustra a criação de uma máquina virtual (VM) no Azure utilizando o Terraform. O objetivo é fornecer um guia prático e didático para iniciantes, introduzindo conceitos básicos de infraestrutura como código (IaC). 

  

2. Estrutura do Repositório 

O repositório é organizado para facilitar o entendimento e a manutenção do projeto. Abaixo está a estrutura dos diretórios e arquivos: 

AZURE-VM/ 

│ 

├── desktop.ini       # Arquivo de configuração local para o diretório 

├── locals.tf         # Definição de variáveis locais (tags comuns) 

├── main.tf           # Configuração principal do Terraform e do backend remoto 

├── outputs.tf        # Declaração das saídas, como o IP público da VM 

├── variables.tf      # Declaração de variáveis reutilizáveis 

└── vm.tf             # Recursos Terraform para criar a infraestrutura (VM, rede, etc.) 

  

3. Descrição dos Arquivos 

3.1 desktop.init 

Arquivo interno do sistema, usado para personalizar o diretório. Neste projeto, ele não tem impacto direto na execução do Terraform, mas está incluído para demonstração de organização. 

  

3.2 locals.tf 

Contém variáveis locais, como tags padrão aplicadas aos recursos. Essas tags ajudam a identificar o proprietário e o método de gerenciamento dos recursos. 

  

3.3 main.tf 

Arquivo principal do projeto. Nele, são configurados: 

- Versão mínima do Terraform. 

- Provedor Azure Resource Manager (azurerm). 

- Backend remoto para armazenar o estado do Terraform. 

- Referências a estados remotos (como rede e segurança). 

  

3.4 outputs.tf 

Define as saídas do Terraform, como o endereço IP público da VM criada. Estas informações podem ser usadas para conectar à VM ou integrar com outros sistemas. 

  

3.5 `variables.tf 

Declara variáveis reutilizáveis para facilitar a parametrização do projeto. Inclui, por exemplo, a região padrão onde os recursos serão criados. 

  

3.6 `vm.tf` 

Arquivo onde estão definidos todos os recursos necessários para a criação da VM, incluindo: 

- Grupo de recursos. 

- IP público. 

- Interface de rede. 

- Configuração da máquina virtual com chave SSH. 

  

  

  

Explicação para fluxo de trabalho como desenvolver passo a passo alguns sendo feito manualmente pelo usuário  

4. Fluxo de Trabalho  

1. **Clonar o Repositório**: Baixe o repositório localmente para começar. 

   ```bash 

   git clone <URL_DO_REPOSITORIO> 

   cd AZURE-VM 

   ``` 

  

2. Inicializar o Terraform 

   Prepare o ambiente Terraform no diretório do projeto. 

   ```bash 

   terraform init 

   ``` 

  

3. Validar Configurações 

   Confirme que os arquivos estão configurados corretamente. 

   ```bash 

   terraform validate 

   ``` 

  

4. Planejar e Aplicar 

   Gere um plano de execução e aplique as configurações. 

   ```bash 

   terraform plan 

   terraform apply 

   ``` 

  

5. Verificar Saídas 

   Após a aplicação, o endereço IP da VM será exibido como saída. 

  

6 Requisitos 

- Conta Azure ativa com permissões administrativas. 

- Terraform instalado (versão 1.3.0 ou superior). 

- Chave SSH pública gerada e disponível localmente (`azure-key.pub`). 

  

7 Expansões Futuras 

- Configurar monitoramento da máquina virtual com Azure Monitor. 

- Adicionar regras de segurança específicas no grupo de segurança da rede. 

- Automatizar a inicialização da VM com scripts de provisionamento. 

  

Diagrama  