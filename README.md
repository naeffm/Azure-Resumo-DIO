DIA 1

Microsoft Azure - Localizando Serviços por Categoria:

-> É possível mudar idioma e tema de toda a interface como dark, light e etc.

-> Ouvi falar sobre o bastião (bastions) que é um método de conexão seguro para acesso das máquinas

Benefícios da nuvem:

-> Alta disponibilidade: Acordos de nível de serviço (SLA) feitos para garantir a disponibilidade do serviço com uma %, nenhuma vai funcionar 100% do tempo.

-> Escalabilidade: Capacidade de ajustar recursos (como RAM, CPU e armazenamento) conforme a demanda podendo aumentar (escala vertical/horizontal) ou diminuir, otimizando o uso e os custos.

-> Elasticidade: Capacidade de ajustar automaticamente os recursos computacionais, como adicionar ou remover VMs e contêineres conforme as flutuações na demanda, garantindo desempenho

-> Confiabilidade: Nuvem disponível em várias regiões do mundo, mesmo que ocorra uma catástrofe em uma região, as outras regiões ainda vão funcionar.

-> Previsibilidade: Confiança e desempenho influenciados pelo Microsoft Azure Well-Architected Framework

-> Segurança: A Azure oferece diversos recursos de segurança, como políticas, configurações de conformidade, controle de acesso baseado em função (RBAC), criptografia de dados em repouso e em trânsito, além de ferramentas para garantir a privacidade e integridade das informações.

-> Governança: Permite organizar e controlar recursos por meio de políticas, restrições, grupos de gerenciamento e controle de acesso, garantindo conformidade e segurança.

-> Gerenciabilidade: Capacidade de gerenciamento como, por exemplo, escalar automaticamente a implantação de recursos (usando APIs e PowerShell)

-> Sla: 99% representa inatividade por 1,68 hora por semana | 7,2 horas no mês | 3,65 dias por ano
        99,9% repesenta 10,1 minutos por semana | 43,2 minutos mês | 8,76 horas ano
        99,95% representa 5 minutos por semana | 21,6 minutos mês | 4,38 horas ano
        99,99% 1,01 minuto por semana | 4,32 minutos mês | 52,56 minutos ano
        99,999% 6 segundos por semana | 25,9 segundos mês | 5,26 minutos ano

DIA 2

Tipos de Serviço de Nuvem na Azure

-> IAAS (Infraestrutura como serviço): Aonde o cliente se envolve mais, alugando maquinas virutias, servidores, armazenamento.

-> PAAS (Plataforma como serviço): Quando se quer apenas o banco de dados por exemplo, o cliente quer apenas um ambiente para criação, sem focar no gerenciamento da infraestrutura.

-> SAAS (Software como serviço): Usuarios se conectam e usam aplicativos alocado na nuvem pela internet exemplo: Microsoft Office 365, email, calendarios.

DIA 3 

Componentes de Arquitetura do Azure

-> Regiões: Cada região pode ter vários datacenters para garantir redundância e disponibilidade.

-> Zona de disponibilidade: Uma Zona de Disponibilidade é composta por um ou mais datacenters. Caso uma zona falhe, outra zona pode assumir o tráfego sem impacto para o cliente.

-> Pares de Regiões: Minimo de 300 milhas de distancia entre os pares, replicação automática para alguns serviços, recuperação de região priorizada em casos de interrupção 

-> Azure na china: 21Vianet o nome.

-> Grupo de Recursos: Conjunto aonde se localiza o Banco de dados, VMs, armazenamento. Voce agregaos recursos em uma unica unidade. Os recursos podem existir em apenas um grupo de recursos, os recursos podem existir em diferentes regiões. Podem ser movidos para diferentes GR. Os aplicativos podem utilizar varios grupos de recursos.

-> Assinatura do Azure: Uma Assinatura do Azure representa uma conta com uma fatura separada para os recursos consumidos. Uma conta pode ter várias assinaturas, sendo que cada uma pode estar associada a um ambiente específico (produção, desenvolvimento, etc.). As assinaturas podem ser associadas a um único diretório do Azure Active Directory e são o principal ponto de cobrança e controle de custos dos recursos. Embora cada assinatura tenha seu próprio conjunto de recursos, elas são usadas em conjunto com Grupos de Recursos para organizar o uso de recursos.

-> Grupos de Gerenciamento: São usados para organizar várias assinaturas em uma estrutura hierárquica, permitindo o controle centralizado sobre elas. Isso ajuda a aplicar políticas de governança, controle de acesso e limites de custo de forma mais eficiente em larga escala.

DIA 4

Serviços de computação do Azure

-> Computação do Azure: Serviço sob demanda que fornece recursos de computação, como VMs, Conteiner Instâncias, Area de trabalho remota*.

-> Máquinas Virtuais do Azure: Emulações de software de computadores fisicos.

-> Conjuntos de dimensionamento de VMs: Oferecem balanceamento de carga para dimensionar os recursos automaticamente.

-> Conjuntos de Disponibilidade de VM: 
        Dominio de falha 0 -> 3 VMs
        Dominio de falha 1 -> 3 VMs
        Dominio de falha 2 -> 3 Vms
        
Usando um Availability Set, o Azure espalha suas VMs automaticamente em diferentes servidores físicos, racks, e fontes de energia dentro do mesmo datacenter. Assim, se uma falhar, a outra continua funcionando.

-> Area de trabalho Virtual: Um ambiente completo de virtualização da Área de trabalho sem precisar executar outros servidores de Gateway, o funcionario só precisa esta conectado a internet.

-> Contêineres: Quando você usa VMs, você precisa subir um sistema operacional inteiro (tipo um Windows ou Linux), instalar as dependências, e aí sim rodar seu programa. Mas com containers você pula essa parte. Eles rodam só o seu programa, com as dependências mínimas, usando o sistema do host que já tá rodando.

-> Azure Functions: Oferta do PaaS, O código baseado em eventos é executado quando chamado, sem exigir uma infraestrutura de servidor durante preiodos inativos.

-> Serviço de aplicativos: Plataforma totalmente gerenciada para criar, implantar e dimensionar aplicativos Web e APis. .NET, Node.js, Java, Python. OFERTA DO PAAS.

-> Gateway de VPN: Enviar trafego criptografado entre uma rede virtual do azure e uma no local pela internet publica.

-> Express Route: Uma conexão via cabo que vai direto da empresa até o servidor do azure. CARO DEMAIS

DIA 5

Identidade, Acesso e Segurança

-> Microsoft entra ID: Gerenciamento de identidade na Azure, quem faz a autentificação da conta.

-> B2B Negocios para Negocios: igual quando logamos com o google em outros sites.

-> Dominio gerenciado (Domain Services): O Entra Domain Services conecta as VMs da nuvem ao login da empresa, sem precisar instalar um Active Directory manualmente.

-> Acesso Condicional: Local do ip, dispositivo, aplicativo, detecção de risco.

-> Controle de acesso baseado em Função (RBAC): Gerenciamento de acesso de granularidade fina, só autoriza o que voce realmente precisa.

-> Confiança zero: Sempre vai supor qeu algo foi violado.

-> Defender for cloud: monitora e protege contra ameças nos datacenters do Azure Locais.

DIA 6 

Dominando o Armazenamento na Azure

-> Nome de conta de armazenamento: deve ser unico no MUNDO

-> Standard ou Premium: Standard para uso geral, Premium para baixa latência. 

-> LRS, GRS, ZRS, GZRS: LRS - Replicação local, 3 copias dos dados.
                        GRS - Replicação entre regiões (Primária e secundaria a centenas de km), 3 cópias na região Pri, 3 cópias na regiao secundaria.
                        ZRS - Replicação em zonas de disponibilidade (Na mesma região), 1 cópia em 3 data centeres diferentes mas na mesma região.
                        GZRS - junta o ZRS  e LRS.











