---
dg-publish: true
---
#aula #sistemas 
- Sistemas distribuidos são conjuntos de componentes autonomos (processadores, serivodres, dispositivos) que trabalham juntos
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