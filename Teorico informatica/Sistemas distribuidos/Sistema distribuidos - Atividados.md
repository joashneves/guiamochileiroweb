---
dg-publish: true
---
## 1 - Defina o que é um sistema distribuído
> Um sistema distribuído é um conjunto de computadores independentes que se apresenta ao usuário como um sistema único e coerente.
## 2 - Quais são as principais caracteristicas do hardware e do software em um sistema distribuido?
> - Hardware: Computadores interconectados por rede, podendo ser heterogêneos (diferentes arquiteturas e SOs).
> - Software: Middleware que oferece serviços como comunicação, segurança e sincronização.
## 3 - Explique o desafio da inexistência de um relógio global em sistemas distribuídos.
> Sem um relógio global, eventos em diferentes nós não podem ser ordenados com precisão. Isso afeta a consistência de dados e controle de concorrência.
## 4 - Cite e explique dois tipos de transparência em sistemas distribuídos
> - Transparência de acesso: Esconde diferenças na representação de dados e métodos de acesso.
> -  Transparência de localização: O usuário não precisa saber onde o recurso está.
> - Transparência de falhas, replicação, mobilidade, desempenho, etc.
## 5 - Qual é a importância do middleware em sistemas distribuidos?
> - Middleware atua como camada intermediária que facilita comunicação, interoperabilidade e abstrações entre aplicações e a rede.
## 6 - Explique o conceito de concorrência e um risco associado a ela.
> - Concorrência é a execução simultânea de processos que acessam recursos compartilhados.
## 7 - Quais são os tres pilares da segunrança em sistemas distribuidos?
> - Confidencialidade: Garantir que apenas partes autorizadas tenham acesso à informação.
 >- Integridade: Garantir que os dados não sejam alterados indevidamente.
> - Disponibilidade: Garantir que o sistema esteja acessível quando necessário.
## 8 - o que torna um sistema distruibuido "aberto"?
> - Um sistema aberto é aquele que segue padrões abertos e permite interoperabilidade entre diferentes sistemas.
## 9 - Cite tres desafios enfrentados para garantir a escalabilidade em sistemas distruibuidos
> -Gerenciamento de carga.
>- Latência da comunicação.
>- Manutenção da consistência.
>- Particionamento e replicação.
>- Balanceamento dinâmico.
## 10 - Explique como a falha de um componente afeta (ou não) um sistema distruibuido 
> - A falha de um componente pode afetar o sistema parcialmente, dependendo do nível de tolerância a falhas implementado.
## 11 - Defina o conceito de grade computacional e diferencie-a de um cluster tradicional
>- Grade (grid) computacional é o uso coordenado de recursos geograficamente dispersos. Clusters são grupos de computadores localizados fisicamente próximos.
>- Grids: heterogeneidade, geograficamente distribuídos.
>- Clusters: alta disponibilidade, mesmo local físico.
## 12 - Quais sao os tres modelos de serviços em computacao em nuvem segundo o NIST? De  um exemplo real de cada um
>- IaaS (Infraestrutura como Serviço): Ex: Amazon EC2
>- PaaS (Plataforma como Serviço): Ex: Google App Engine
>- SaaS (Software como Serviço): Ex: Google Workspace
## 13 - Por que a interoperabilidade é um desafio critico em sistemas de informação distribuidos
>- Porque os sistemas podem usar diferentes linguagens, protocolos e formatos de dados.
## 14 - Compare RPC/RMI com MOM (Publish/subscribe) em termos de sincronia e tolerancia a falhas
>- RPC/RMI: Comunicação síncrona, baixa tolerância a falhas.
>- MOM (Pub/Sub): Comunicação assíncrona, mais tolerante a falhas.
## 15 - Liste duas caracteristicas essenciais de sistemas pervasivos distribuidos, segundo tanenbaum e van steen(2007)
>- Capacidade de adaptar-se ao ambiente.
>- Funcionamento com pouca ou nenhuma intervenção humana
## 16 - por que sistemas pervasivos exigem menos abstração que sistema distribuidos tradicionais?
>- Porque operam em contextos mais específicos e previsíveis, com menos camadas e mais direto ao hardware.
## 17 - Qual middleware é mais adequado para dispotivios lot com restrição de energia? justifique
>- MQTT: Leve, baseado em publish/subscribe, com baixo overhead e ideal para redes com largura de banda limitada.
## 18 - descreva um cenario onde uma nuvem hibrida seria a melhor opção de implementação
> - Empresas que mantêm dados sensíveis localmente (privado) e usam a nuvem pública para escalabilidade de aplicações.
>- Hospitais com prontuários internos e app de agendamento na nuvem.
## 19 - Como o modelo publish/subscribe facilita a integração em sistemas corporativos?
>-Permite que componentes publiquem ou assinem eventos sem conhecimento mútuo, promovendo desacoplamento e escalabilidade.
>- Integração de sistemas heterogêneos.
>- Redução de dependências diretas.
## 20 - Explique o coneceito de "Operação espontanea" em sistemas pervasivos, usando o  exemplo da smarthome
>- Dispositivos interagem automaticamente sem intervenção humana.
## 21 - Defina o que é um sistema distribuido e cite sua principal caracteristica
>- Sistema composto por múltiplos nós autônomos interconectados via rede.
## 22 - Qual é o objetivo da transparencia em sistema distribuidos? de um exemplo.
> Esconder a complexidade da distribuição dos recursos.
## 23 - Explique a diferença entre sistemas paralelos e distribuidos
>- Paralelos: Compartilham memória e executam em múltiplos núcleos/máquinas próximas.
>- Distribuídos: Computadores autônomos e geograficamente dispersos.
## 24 - descreva o modelo cliente-Servidor e compare-o com modelo P2P
>- Cliente-Servidor: Um servidor fornece serviço a vários clientes.
>- P2P: Todos os nós podem atuar como cliente e servidor. Centralização vs descentralização.

## 25- quais são os tres tipos de modelos fisicos de sistemas distruibuidos? cite um exemplo de cada
>- Computação em Cluster: Cluster de servidores web em uma universidade que distribui a carga de acessos simultâneos ao portal acadêmico.
>- Grade Computacional: Hardwares distintos e dispersos entre elas
>- Sistemas formados por sites geograficamente distribuídos, interligados pela internet.
>- Funcionam como um único sistema virtual, integrando recursos de diferentes locais.
>- Nuvem: Microsoft Azure.
## 26 - o que é middleware e qual seu papel em sistemas distruibods heterogenos
>- Middleware é uma camada de software que facilita a comunicação entre diferentes sistemas, ocultando a heterogeneidade.
## 27 - liste dois desafios em um sistema distribuidos relacionados a falha e explique um deles
> Ataque de Negação de Serviço (DoS): Ocorre quando um serviço é sobrecarregado com pedidos falsos, tornando-o inacessível a usuários reais. Afeta a disponibilidade do sistema e exige medidas como filtros e gerenciamento de tráfego para mitigação.
>- Segurança de Código Móvel: Códigos recebidos e executados remotamente podem ser maliciosos, acessando dados indevidos ou afetando o sistema. Exige autenticação da origem, execução segura e verificação de integridade.
## 28 - Como arquiteturas centradas em dados funcionam? de um exemplo pratico
>- Dados são o centro das operações, e os serviços interagem indiretamente por meio desses dados. Ex. Sistemas baseados em eventos (event sourcing)
## 29 - Explique o modelo publish-subscribe e suas vantagens
> - Modelo onde emissores (publishers) enviam mensagens para tópicos e receptores (subscribers) recebem apenas o que assinam.
>- Desacoplamento.
>- Escalabilidade.
>- Flexibilidade.
## 30 - Qual a diferença entre arquiteturas em camadas e arquiteturas baseadas em objetos
>- Em camadas: Separação funcional (ex: apresentação, lógica, dados).
>- Baseadas em objetos: Foco em reusabilidade e encapsulamento de objetos com estado e comportamento.