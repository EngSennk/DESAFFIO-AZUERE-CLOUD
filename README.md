Desafio DIO: Criando e Configurando uma Máquina Virtual no Microsoft Azure
🎯 Objetivo do Repositório
Este repositório foi criado como parte do desafio "Entendendo o Desafio de Projeto: Criando e Configurando uma Máquina Virtual no Microsoft Azure" da Digital Innovation One (DIO). O objetivo é documentar o processo de criação e configuração de uma máquina virtual (VM) na plataforma Microsoft Azure, servindo como material de estudo e consulta futura.

📚 Conteúdo
Este repositório contém:

Resumos e Anotações: Principais conceitos sobre máquinas virtuais no Azure, o processo de criação e configurações importantes.

Dicas: Sugestões e boas práticas para trabalhar com VMs no Azure.

Passo a Passo (Resumido): Um guia simplificado baseado na documentação oficial e na experiência prática.

Recursos Adicionais: Links úteis e referências.

📝 Meus Resumos e Anotações sobre Azure VMs
O que é uma Máquina Virtual no Azure?
Uma Máquina Virtual (VM) do Azure é um dos vários tipos de recursos de computação sob demanda e escalonáveis que o Azure oferece. Essencialmente, é um computador virtual que reside na nuvem e que você pode usar como se fosse um computador físico.

Flexibilidade: Você pode escolher o sistema operacional (Windows, Linux), o tamanho da VM (CPU, RAM, armazenamento) e a região geográfica onde ela será hospedada.

Controle: Você tem controle total sobre o sistema operacional e o software instalado na VM.

Escalabilidade: É possível aumentar ou diminuir os recursos da VM conforme a necessidade.

Casos de Uso Comuns:

Hospedagem de aplicações web e bancos de dados.

Ambientes de desenvolvimento e teste.

Execução de cargas de trabalho que exigem alta capacidade de processamento.

Recuperação de desastres.

Principais Componentes ao Criar uma VM
Ao criar uma VM no portal do Azure, você encontrará diversas opções de configuração. As principais incluem:

Grupo de Recursos: Um contêiner que mantém recursos relacionados para uma solução do Azure. É fundamental para organizar e gerenciar seus recursos.

Minha Anotação: Sempre crie um novo grupo de recursos para projetos distintos para facilitar o gerenciamento e a exclusão, se necessário.

Nome da Máquina Virtual: Um nome exclusivo para identificar sua VM.

Região: O local geográfico do data center onde sua VM será hospedada. Escolher uma região próxima aos seus usuários pode reduzir a latência.

Minha Anotação: Considere também os custos, pois podem variar entre regiões.

Opções de Disponibilidade: Configurações para garantir a resiliência da sua aplicação (Zonas de Disponibilidade, Conjuntos de Disponibilidade).

Imagem: O modelo usado para criar a VM, que inclui o sistema operacional e, às vezes, software pré-instalado. O Azure Marketplace oferece uma vasta gama de imagens.

Minha Anotação: Para este desafio, utilizei a imagem do Windows Server [ou a imagem Linux X, conforme sua escolha].

Tamanho da VM: Define a quantidade de CPU, RAM e capacidade de armazenamento temporário. A escolha do tamanho impacta diretamente o custo e o desempenho.

Minha Anotação: Comece com um tamanho menor e escale conforme a necessidade. Para o desafio, o tamanho [Nome do Tamanho Escolhido, ex: Standard_B1s] foi suficiente.

Conta de Administrador: Credenciais (nome de usuário e senha ou chave SSH para Linux) para acessar a VM.

Minha Anotação: Crie senhas fortes e armazene-as em local seguro.

Regras de Porta de Entrada (NSG - Network Security Group): Controlam o tráfego de rede de entrada para a VM. Por padrão, para VMs Windows, a porta RDP (3389) é geralmente habilitada, e para VMs Linux, a porta SSH (22).

Minha Anotação: Habilite apenas as portas estritamente necessárias para aumentar a segurança.

Discos:

Disco do SO: Onde o sistema operacional é instalado.

Discos de Dados (Opcional): Para armazenamento adicional.

Minha Anotação: Entenda os tipos de disco (HDD, SSD Standard, SSD Premium) e suas implicações de custo e desempenho.

Rede:

Rede Virtual (VNet): Uma rede privada isolada no Azure para suas VMs e outros recursos.

Sub-rede: Uma subdivisão da VNet.

Endereço IP Público: Necessário para acessar a VM pela internet.

Minha Anotação: O Azure cria esses recursos automaticamente com configurações padrão se você não especificar configurações avançadas.

🛠️ Processo de Criação da VM no Portal do Azure (Resumido)
Este é um resumo dos passos que segui, baseado no Início Rápido: Criar uma máquina virtual do Windows no Portal do Azure (ou o guia equivalente para Linux, se aplicável).

Acessar o Portal do Azure: portal.azure.com

Criar um Recurso:

Clique em "+ Criar um recurso".

Pesquise por "Máquina Virtual" e selecione.

Clique em "Criar".

Configurações Básicas:

Assinatura: Selecione sua assinatura do Azure.

Grupo de Recursos: Crie um novo ou selecione um existente.

Minha Experiência: Criei um novo grupo chamado [SeuNomeDeGrupoDeRecursos].

Nome da Máquina Virtual: [SeuNomeDeVM]

Região: [SuaRegiaoEscolhida]

Opções de Disponibilidade: [SuaOpcaoDeDisponibilidade] (para o desafio, "Nenhuma redundância de infraestrutura necessária" pode ser suficiente).

Imagem: [SuaImagemEscolhida, ex: Windows Server 2019 Datacenter]

Tamanho: [SeuTamanhoEscolhido, ex: Standard_B1s]

Conta de Administrador: Defina nome de usuário e senha.

Minha Experiência: Usuário [SeuUsuarioAdmin].

Regras de Porta de Entrada: Permita as portas selecionadas (ex: RDP para Windows, SSH para Linux).

Configurações de Disco (Padrão ou Personalizado):

Revise o tipo de disco do SO.

Minha Experiência: Mantive o padrão [TipoDeDiscoPadrao].

Configurações de Rede (Padrão ou Personalizado):

Revise a VNet, sub-rede, IP público.

Minha Experiência: Mantive as configurações de rede padrão para simplificar.

Gerenciamento, Avançado, Marcas (Opcional):

Explore essas abas se precisar de configurações mais específicas (ex: monitoramento, extensões, scripts personalizados).

Minha Experiência: Para este desafio, não precisei alterar muitas opções avançadas.

Revisar + Criar:

O Azure validará suas configurações.

Revise todos os detalhes.

Clique em "Criar".

Aguardar a Implantação: O processo pode levar alguns minutos.

Acessar a VM:

Após a implantação, vá para o recurso da VM.

Clique em "Conectar" e siga as instruções para RDP (Windows) ou SSH (Linux).

Minha Experiência: Conectei via RDP usando o IP público e as credenciais de administrador. [Adicione aqui uma captura de tela da sua VM conectada, se desejar, na pasta /images]

✨ Dicas e Boas Práticas
Segurança Primeiro:

Use senhas fortes e únicas para a conta de administrador.

Configure o Network Security Group (NSG) para permitir tráfego apenas das portas e IPs necessários. Considere o uso do Azure Bastion para acesso seguro sem expor portas RDP/SSH à internet.

Mantenha o sistema operacional e o software da VM atualizados.

Gerenciamento de Custos:

Escolha o tamanho da VM apropriado para sua carga de trabalho.

Desligue ou desaloque VMs quando não estiverem em uso para economizar custos (lembre-se que o armazenamento ainda será cobrado).

Utilize o Azure Cost Management para monitorar seus gastos.

Organização:

Use grupos de recursos para organizar seus projetos.

Adote uma convenção de nomenclatura consistente para seus recursos.

Use marcas (tags) para categorizar recursos e facilitar o gerenciamento e o faturamento.

Automação:

Para implantações repetitivas, considere o uso de modelos ARM (Azure Resource Manager), Azure PowerShell ou Azure CLI.

Backup:

Configure o Backup do Azure para proteger seus dados na VM.

📸 Capturas de Tela (Opcional)
Se você tirou capturas de tela durante o processo, pode organizá-las em uma pasta /images neste repositório e referenciá-las aqui.

Exemplo:

![Portal do Azure - Criação da VM](./images/01-portal-criacao-vm.png)
![Conexão RDP bem-sucedida](./images/02-conexao-rdp.png)

(Adicione aqui suas próprias capturas de tela e descrições)

💡 Minha Experiência e Aprendizados
[Descreva aqui sua experiência pessoal com o desafio. Quais foram os pontos mais fáceis? Quais foram os mais desafiadores?]

[Quais novos conceitos você aprendeu ou consolidou?]

[Como você pretende aplicar esse conhecimento no futuro?]

🔗 Recursos Úteis Adicionais
Documentação Oficial do Azure VMs: https://learn.microsoft.com/pt-br/azure/virtual-machines/

Calculadora de Preços do Azure: https://azure.microsoft.com/pt-br/pricing/calculator/

Microsoft Learn (Trilhas de Aprendizagem Azure): https://learn.microsoft.com/pt-br/training/azure/

Autor:Diego Sena

Data: 05/05/5025

