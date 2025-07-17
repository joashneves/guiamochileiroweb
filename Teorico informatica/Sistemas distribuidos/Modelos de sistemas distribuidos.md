---
dg-publish: true
---
#aula #sistemas 
- Sistemas distribuidos são conjuntos de componentes autonomos (processadores, servidores, dispositivos) que trabalham juntos
# Sistemas Distribuidos :
- Definimos um sistema distribuido como auqele no qual os componentes de hardware ou software, localizados em computadores interligados em rede, comunicam-se e coordenam suas ações apenas enviando mensagens entre si. Essa definição simples abrange toda a gama de sistemas nos quais computadores interligados em rede podem ser distribuidos de maneira util.
## Software 
- Coleção de processos e threads que se encontram distribuidos em difrerentes computadores.
## Hardware
- Coleção de computadores independentes comunicados em rede. Passando uma aparencia aos usuarios como um sistema unico e coerente.
## Distancia entre computadores
- OS computadores em uma rede podem estar separados por grandes distencias ou muito proximos, como no mesmo predio ou sala. A localização fisica não limita a comunicação em sistemas distribuidos.
## Concorrencia
- Em uma rede, é comum que varios programas sejam executados simultaneamente em diferentes maquinas. Isso permite que usuarios compartilhem recursos como arquivos e paginas web. A capacidade do sistema pode ser aumentada com a inclusão de novo computadores. A coordenação entre programas concorrentes é um desafio importante nesses ambientes.
## Inexistencia de relogio global
- Os computadores de uma rede não conseguem manter uma sincronização de tempo perfeita. Por isso, não há uma noção unica e global de tempo. A coordenação entre ações dos programas depende da troca de mensagens, o que pode gerar desafios de sincronização.
## Falhas independentes 
- Cada componente do sistema distribuído pode falhar separadamente. Um computador pode parar ou uma rede pode falhar, mas os demais componentes continuam funcionando. Muitas vezes, essas falhas não são detectadas imediatamente, exigindo que o sistema seja projetado para lidar com incertezas e isolamento de forma eficiente.

---
# Tedencias em sistemas distribuidos
- As mudanças significativas devido as tedencia influentes que impacta na evolução dos sistemas distribuidos.
- O surgimento da tecnologia de redes pervasivas.
- O Surgiemento da computação ubiqua, combinado ao distribuidos.
- A crescente demanda por serviços multimidia.
- A visão dos sistemas distribuidos como um serviço publico.
---
# Desafios
## Heterogeneidade em sistemas distribuidos
### Diversidade na internet
- A internet é composta por muitos tipos de redes diferentes.
- Mascarada pelos protocolos de internet que permitem a comunicação entre todos os dispositivos.
### Protocolos inernet como padronização
- Cada tipo de rede( ex: Ethernet, Wifi ) tem sua propria implementação dos protocolos internet.
- Isso permite a interoperabilidade entre redes distintas.
### Diferenças de Hardware
- Dados como inteiros podem ser representados de forma diferente entre sistemas :
- Ordem dos bytes pode varias (mais significativo primeiro ou ultimo).
- Essas diferenças precisam ser tratadas para garantir comunicação correta entre programas e diferentes maquinas.
### Sistemas operacionais e protocolos
- Todos os computadores na internet precisam ter implementações dos protocolos internet
- Nem todos os sistemas operacionais oferecem os mesmos serviços de rede, o que aumenta a complexidades.
---
# Computação em cluster (Cluster computing)
- Ambiente Homogeneo
- Interconexão de hardwares atraves da rede LAN
- Cada nodo possui instalado um mesmo SO local e estão conectados com o mesmo tipo de rede. Esses nodos são controlados e gerenciados pelo nodo mestre, responsavel por alocar os nodos auxiliares para um determinado programa paralelo, gerenciar uma fila de lotes de trabalhos e oferecer uma interface de sistema para os usuarios interagirem.
- Os clusters computacionais, conhecidos como **supercomputadores**, possuem uma coleção de computadores dedicados e ligados por meio de uma rede de interconexão de alta velocidade.
---
# Computação em grade (Grip computing)
- Hardwares distintos e dispersos entre elas
- Sistemas formados por sites geograficamente distribuidos, interligados pela internet.
- Funcionam como um unico sistema virtual, integrando recursos de diferentes locais.
## Heterogeneidade elevada:
- Redes, sistemas operacionais, poliitcas de segurança e dominios administrativos diretes.
## Compartilhamento de recursos:
- Supercomputadores, armazenamento em larga escala e bancos de dados.
## Organização virtual:
- Recursos de multiplas instituições são disponibilizados para um grupo de usuarios (Tanenbaum & Van Steen, 2007)
## Objetivos das grades Computacionais:
- Permitir que organizações distintas compatilhem recursos computacionais de forma colaborativa.
- Criar um ambiente unifaco, mesmo com infraestruturas hetegeneas.
#### Exemplos : 
- Supercomputadores (Capacidade de processamentos)
- Sistemas de armazenamento (grandes volumes de dados)
- Bancos de dados distribuidos
## Diferença em relação a clusters:
- Clusters são homogeneos (mesmo dominos administrativo, hardware e SO)
- Grades são heteronegeas e geograficamente dispersas.
## Semelhança com computação em nuvem:
- Grades focam mais em integração de recursos do que em serviço sob demanda 
---
# Computação em nuvem(Cloud computing)
- Modelo de sistema distribuido que oferta recursos computacionais como um serviço, eguindo um modelo de "pay-per-use" (pague pelo que usar)
- Analogia com serviços de utilidade publica (agua, eletricidade)
- Fisicos : Armazenamento, processamento, redes
- Logicos : Serviço de software (email, agendas, banco de dados)
## Modelos de implatanção
### Nuvem publica :
- Recursos disponiveis para o publico geral
### Nuvem privada:
- Infraestrutura exclusiva para uma unica organização
### Nuvem hibrida:
- Combinação de nuvens publica e privada (parte dos recursos é compartilhada, outra é nterna)
### Nuvem comunitária :
- Integração de nuvem de diferentes organizações para colaboração e compartilhamento
## Modelos de Serviço
### LaaS (Infrastructure as a service)
- Oferece infraestrutura basica (maquinas virutais, armazenamento, redes)
- Ex : Aws Ec2, Microsoft Azure VMs
### PasS (Platform as a Service)
- Fornece plataformas para desenvolvimento e implantação de aplicações
- Ex : Google App, Vercel
### SaaS (Software as a Service)
- Disponibiliza aplicações prontas para uso via navegador
- EX : Gmail, Microsoft 365
## Beneficios da computação em nuvem
- **Escalabilidade:** Ajuste dinamico de recursos conforme demanda.
- **Redução de custo:** Eliminina necessidade de infraestrutura fisica propria
- **Acessibilidade:** Serviços disponiveis de qualquer lugar com internet.
- **Alta disponibilidade:** Tolerancia a falhas e redundancia distribuida.
___
# Middleware
- O termo Middleware se aplica a uma camada de software que fornece uma abstração de programação, assim como o mascaramento da heterogeneidade das redes, do hardware, dos sistemas operacionais e das linguagens de programação subjacentes.
- Alem de resolver os problemas de heterogeneidade, o middleware fornece um modelo computacional uniforme para ser usado pelos programadores de serviços e de aplicativos distribuidos.
---
# Sistemas abertos em sistemas distribuidos
- Os sistemas projetados a partir de padrões públicos são chamados de sistemas distribuídos abertos, para reforçar o fato de que eles são extensíveis. Eles podem ser ampliados em nível de hardware, pela adição de computadores em uma rede, e em nível de software, pela introdução de novos serviços ou pela reimplementação dos antigos, permitindo aos programas aplicativos compartilharem recursos. Uma vantagem adicional, frequentemente mencionada para sistemas abertos, é sua independência de fornecedores individuais.
- Os sistemas abertos são caracterizados pelo fato de suas principais interfaces serem publicadas.
- Os sistemas distribuidos abertos são baseados na estipulação de um mecanismo de comunicação uniforme e eme interfaces publicadas para acessos ao recursos compartilhados.
- Os sistemas distribuidos abertos podem ser construidos a partir de hardwares e software heterogeneo, possivelmente de diferentes fornecedores. Para que um sistema funcione corretamente, a compatibilidade de cada componente com o padrão publicado deve ser cuidadosamente testada e verificada.
- MUitos recursos de informação que se tornam disponiveis e são mantidos em sistemas distribuidos tem um alto valor intrinseco para seus usuarios. Portanto, sua segurança é de consideravel importancia.
## Tres pilares da segurança :
 - **Confidencialidade :** Proteção contra acesso não autorizado
 - **Integridade :** Proteção contra alterações indevidas
 - **Disponibilidade :** Garantia de acesso aos recursos
---
# Escalabilidade em sistemas Distribuidos
- Um sistema distribuido deve ser escalavel, ou seja, precisa ser capaz de aumentar a capacidade de recursos e usuarios, os quais tambem podem estar e aumentar geograficamente.
## Desafios :
- Controle de custo de expansão (Hardware/software)
- Controle de perda de desenpenho (Ex: Uso de DNS hierarquico)
- Prevenção do esgotamento de recursos (Ex: endereços IP)
- Evitar gargalos centralizados (Ex : arquivos unicos de mapeamento)
## Soluções aplicadas
- Replicação de dados
- Uso de cache
- Distribuição de servidores e execução concorrente
---
# Tratamento de falhas em Sistemas distribuidos
- As vezes, os sistemas de computador falham. Quando ocorrem falhas no hardware ou no software, os programas podem produzir resultados incorretos ou podem produzir resultados incorretos ou podem parar antes de terem concluido a computação pretendida.
- Falhas em sistemas distribuidos são parciais (nem todos os componentes falham)
## **Tecnicas de tramentos**
- Detecção de falhas (Ex: soma de verificação)
- Recuperação de falhas (reexecução ou replicação de tarefas)
- Mascaramento de falhas (ex: replicação com consenso)
- Desafios incluem falhas silenciosas e limitações na detecção em redes amplas
---
# Concorrencia em sistemas dstribuidos
- Tantos os serviços como os aplicativos fornecem recursos que podem ser compartilhados pelos clientes em um sistema distribuido. Portanto, existe a possibilidade de que varios clientes tentem acessar um recurso compartilhado ao mesmo tempo.
## Compartilhamento de recursos : 
- Serviços e aplicativos distribuem recursos entre multiplos clientes.
- Exemplos : Estrutura de dados de lances em leilões pode ser acessadas simultaneamente por varios usuarios.
## Acesso concorrente : 
- Varios clientes podem tentar acessr o mesmo recurso ao mesmo tempo
- Tratar um pedido por vez limita o desempenho
## Processamento concorrente :
- Sistemas permitem multiplos pedidos sendo processados simultaneamente.
- Cada recursos pode ser encapsulados como um objeto acessados por diferetes threads/processos.
## Riscos de inconsistência :
- Acesso simultaneo pode gerar conflitos e resultados incorretos.
- Ex : Entrelaçamento de lances pode trocar valores entre usuarios.
## Responsabilidade de objetos compartilado: 
- O objeto deve garantir comportamento correto em ambiente concorrente.
- Programadores precisam considerar isso mesmo em objetos que não foram originalmente projetados para sistemas distribuidos
## Garantia de coerencia 
- Operações devem ser sincronizadas para manter a consistencia dos dados
- Tecnicas como semaforos podem ser utilizadas para controle de concorrencia
---
# Transparencia em sistemas distribuidos
- A transparencia é definida como a ocultação, para um usuario final ou para um programador de aplicativos, da separação dos componentes em um sistema distribuido, de modo que o sistema seja percebido como um todo, em vez de como uma coleção de componentes independetes. As implicações da trasnparencia tem grande influencia sobre o projto do software de sistema
- **Transparencia de acesso:** Permite que recursos locais e remotos sejam acessados com o uso de operações identicas.
- **Transparencia de localização:** Permite que os recursos sejam acessados sem conhecimento de sua localização fisica ou em rede (por exemplo, que predio ou endereço ip)
- **Transparencia de concorrencia:** Permite que varios processos operem concorrentemente, usando recursos compartilhados sem interferencia entre eles.
- **Transparencia de replicação:** Permite que varias instancia dos recursos sejam usadas para aumentar a confiabilidade e o desempenho, sem conhecimento das replicas por parte dos usuarios ou dos programadores de aplicativos.
- **Transparencia de falhas:** Permite a ocultação de falhas, possibilitando que usuarios e programas aplicativos concluam suas tarefas, a despeito da falha de componentes de hardware ou software.
- **Transparencia de mobilidade:** Permite a movimentação de recursos e clientes dentro de um sistema, sem afetar a operação de usuarios ou de programas.
- **Transparência de desempenho:** Permite que o sistema seja reconfigurado para melhorar o desempenho à medida que as cargas variam.
- **Transparencia de escalabilidade:** Permite que o sistema e os aplicativos se expanda em escala, sem alterar a estrutura do sistema ou os algoritmos de aplicação.
- As duas transparencia mais importantes são a de acesso e a de localização; sua presença ou ausencia afeta mais fortemente a utilização de recursos distribuidos. As vezes, elas são referidas em conjunto como transparência de rede.
---
# Tres perspectivas principais:
**1 - Modelos fisicos**
- Descrevem a organização fisica dos componentes (hardware, rede).
- Exemplos:
	- Sistemas clusterizados  (grupo de máquinas interligadas)
	- Grid computing  (recursos distribuídos geograficamente).
	- cloud computing (virtualização de recursos sob demanda).

**2 - Modelos arquiteturais**
- Definem como os componentes iteragem.
- Exemplos:
	- Clinete-servidor (solicitação-resposta).
	- P2P (Peer-to-Peer) (todos os nós são clientes e servidores)
	- Microserviços (sistemas modulares independentes)
**3 - Modelos fundamentais**
- Abordam propriedades essenciais do sistema.
- Exemplos: 
	- Modelo de falha (como o sistema lida com erros)
	- Modelo de comunicacao (síncrono vs. assíncrono)
	- Modelo de consistencia (como dados são sincronizados)
---

**Desafios em sistemas distribuídos**
- variação dos modos de uso/manipulação
- **problema**: cargas de trabalho imprevisíveis
- **exemplo**: um servidor web pode ter picos de acesso
- **solução**: balanceamento de carga e escalabilidade dinâmica

**Ameaças Externas**
- Ataques de negação de serviços (DDoS): Sobrecarregam o sistema.
- Codigos moveis maliciosos: Scripts que exploram vulnerabilidades.
- Solução: Firewalls, autenticação, criptografia.

**Elementos basios**
- Processos e Threads : unidades de execução concorrentes.
- Diferença entre sistemas paralelos e distribuidos

Um estilo arquitetonico é determinado atraves dos:
- Componetnes : unidade modular com interfaces requeridas e fornecidas bem definidas que é substituivel dentro de seu ambiente.
- COnexões : o modo como os componentes estão ligados
- Dados intercambiados : forma de troca dos dados entre componentes
- Formas de cofiguração
---
## Tipos de estilo arquitetonicos
- Arquiteturas em camadas
- baseadas em objetos
- centradas em dados
- baseadas em eventos
### Em camadas
- Tipo de estrutura arquitetonicos:
	- O componente me um camada so pode chamar a camada abaixo e receber sua resposta
	- modelo basico cliente/servidor
- **Visão tradicional em 3 camadas**
- Nivel de interface
- Nivel de processamento
- Nivel de dados
### Orientada a objeto
Arquiteturas baseadas em ojetos e orienteadas a serviços
- Objetos correspondem as definições de componentes
- objetos (componentes) são conectados por meio de chamadas de procedimento remotas
- um tipo de organização mais solta
### Centradas em dados
Arquiteturas centradas em dados;
- O sistema distribuido é visto como uma coleção de recursos gerenciados individualmente pelo compentes. Os recursos podem ser adicionados, removidos, recuperados e modificados por aplicação(remotas)
- Componentes se comunicam atraves de um repositorio comum como se fosse uma "caixa postal"
### Baseada em eventos
Sistemas publish-subscribe
- Componentes publicam eventos e certificam que somente os subscreveram recebem estes eventos
- Fracamente acoplados: Não invocam explicitamente um ao outro.
- Nesse modelo, os processos se comunicam pela propagação de eventos e tambem podem transportar dados. Caracteriza-se como um sistema subescrever/publicar, isto é, clientes publicam interesse em determinado evento realizando uma inscrição enviada parau ma entidade intermediaria denominada broker(middleware)

---

# Processos
- **Definição** : Um processo é uma instancia de um programa em execução
- **Execução independente** : Cada processo possui seu proprio espaço de  endereçamento na memoria
- **Processadores virtuais** : O SO cria processadores virtuais para gerenciar a execução de múltiplos processos
- **Processos independentes** : Executam de forma isolada, mas podem competir por recursos
- **Recursos compartilhados** : 
	- **Hardware** : Nucleos de processamento, memoria (cache, RAM, disco), dispositivos de E/S
	- **Software** : Variaveis compartilhadas, arquivos, sockets
- **Papel do SO** : Garantir a concorrência segura e eficiente entre processos.
- **Desafios adicionais** : 
	- Comunicação entre processos em maquinas diferentes
	- Sincronização distribuida
	- Tolerancia a falhas e consistencia de dados
- **Exemplos de tecnicas
	- Troca de mensagens (RPC, sockets)
	- Algoritmos de exclusão mutua distribuida
	- Protocolos de consenso (Paxos, Raft)
# Threads
- **Definição** : Unidade basica de execução dentro de um processo, compartilhando o mesmo espaço de memoria.
- **Relação com Processos :**
	- Um processo pode ter uma ou multiplas threads
	- Theds de um mesmo rocesso compartilham recursos (memoria, arquivos), mas tem fluxo de execução indepedentes
- **Efeiciencia :
	- Criação e destruição mais rapidas
	- Custo reduzido : troca de contexto entre threads é menos custosas que entre processos
- **Paralelismo :
	- Software : Permite concorrencia em aplicações
	- Hardware : Aproveita multiplos nucleos de CPU para execuçãlo paralela
- **Desempenho :
	- Comunicação entre threads (via memoria compartilhada) é mais eficiente que entre processos (IPC).
- **Aplicações
	- Servidores concorrentes (ex : Multiplas conexões em paralelo)
	- Processamento distribuido (ex : divisão de tarefas entre nós)
- **Modelos de Threads
- 1:1 (Kernel-Level) : Cada thread do usario mapeada para uma thread do SO
- N:1 (User-level) : Multiplas Threads do usuario gerenciadas por uma thread do SO
- M:n (hibrido) : Combina vantagens dos dois modelos
## Processos x Threads
- Um processo servidor de arquivos com um unico fluxo faz uma requisição do disco e espera pelo resultado
- O mesmo servidor de arquivo com multiplos fluxos pode atender a solicitações de outros usuarios
## Clientes multithreads
- Clientes podem executar diversos fluxos em paralelo usando as Threads
- User não necessita esperar ate que todos os componentes sejam carregados
- **Servidores Multithreads
	- Cada requisição que chega passa por uma thread despachante
	- Server escolhe um thread operario
	- o thread despachante pode ser selecionado para fazer o trabalho, caso todos estejam ocupados
# Servidores multiThreads
- Alem de simplificar o codigo do servidor, explora paralelismo para obter alto desempenho, mesmo em sistemas monoprocessadores
- **Servidor de arquivos
	- Espera um requisição, executa e devolve a resposta
	- Uma organização possivel é usar o modelo despachante/operario
	- Um thread despachante deve ler requisições que entram para operações de arquivo
	- o servidor escolhe um thread 
	- Suponha que o servidor de arquivos tenha sido implementado com ausencia de threads
	- o servidor obtem uma requisição, examina e executa ate a conclusão 
	- servidores monothread não poderiam atender a um segundo usuario enquanto leem disco!
	- CPU fica ociosa, enquanto o servidor de arquivos estiver esperando pelo disco
# Virtualização
- Treadhs e processos passam uma ilusão de realizar tarefas ao mesmo tempo
- Em computadores com uma CPU, a execução simultanea é uma ilusão:
	- Unica CPU : somente uma thread ou processo sera executada por vez
	- A ilusão de paralelismo é dada pelo chaveamento rapido entre threads e processos
- Virtualizar recursos : fingir que um determinado recurso esta replicado no sistema