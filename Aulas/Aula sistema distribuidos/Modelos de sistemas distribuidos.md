#aula #sistemas 
- Sistemas distribuidos são conjuntos de componentes autonomos (processadores, serivodres, dispositivos) que trabalham juntos
---
# Tres perspectivas principais:
**1 - Modelos fisicos**
- Descrevem a organização fisica dos componentes (hardware, rede).
- Exemplos:
	- Sistemas clusterizados
	- Grid computing
	- cloud computing

**2 - Modelos arquiteturais**
- Definem como os componentes iteragem.
- Exemplos:
	- Clinete-servidor
	- P2P
	- Microserviços
**3 - Modelos fundamentais**
- Abordam propriedades essenciais do sistema.
- Exemplos: 
	- Modelo de falha
	- Modelo de comunicacao
	- Modelo de consistencia
---

**Desafios em sistemas distribuídos**
- variação dos modos de uso/manipulação
- **problema**: cargas de trabalho imprevisíveis
- **exemplo**: um servidor web pode ter picos de acesso
- **solução**: balanceamento de carga e escalabilidade dinâmica

**Problemas internos**
- Ausencia de relogio global:
	- Dificuldade em orgenar eventos

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


---
