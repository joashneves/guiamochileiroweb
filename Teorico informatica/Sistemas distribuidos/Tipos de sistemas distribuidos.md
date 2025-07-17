---
dg-publish: true
---
# Sistemas de informação dsitribuidos
- Sistemas que integram multiplos componentes em diferentes locais, acessados via navegador ou aplicativo.
- Dados e processamento ficam no lado do provedor, enquanto clientes enviam requisições e recebem repostas.
## Desafio principal : interoperabilidade
- Capacidade de sistemas diferentes se comunicarem de forma transparentes
- Necessaria em ambientes corporativos para integrar serviços heterogenos
# Modelo cliente-servidor
- **Cliente :** Envia requisições (Ex: navegador, app mobile)
- **Servidor/Provedor:** Processa e retorna respostas
- **Transparencia para o usuario:** Operações ocorrem sem que o cliente perceba a complexidade.
# Transações em sistemas distribuios
## Originalmente baseadas em modelos ACID:
- Atomicas (Indivisivel para o mundo exterior, tudo ou nada)
- Consistentes (não viola as invariantes do sistema, dados validos antes e depois)
- Isoladas (transações concorrentes não interferem umas com as outras - execução sem interferencia)
- Duraveis (uma vez comprometida uma transação, as alterações são permanente - sobrevivem a falhas)
	- **Problema:** Modelo rigido demais para aplicações distribuidas
	- **Solução:** Desacoplar aplicações de transações tradicionais
# Middlewares de cominicação
## RPC (Remote procedure call) & RMI (Remote Method invocation):
- Permitem chamadas diretas entre processos remotos
- Limitação: Requer que ambos os lados estejam ativos simultaneamente
## MOM (MEssage-Oriented Middleware):
- Sistema assincrono baseado em troca de mensagens
- **Modelo publish/subscribe: (Repositorio ou caixa postal)
- Aplicações publicam mensagens em topicos
- Middleware distribui para assinantes interesssados.
- Ex: Facebook
- vantagem : tolerancia a falhas e desconexões temporarias
# Aplicações corporativas
- **Exemplos:** Sistemas de ERP, logistica, finanças
### Requisitos:
- Escalabilidade.
- Tolerancia a falhas
- Integração entre sistemas legados e modernos
# Sistemas distribuidos pervasivos.
- Sistemas compostos por dispostivos moveis e ebarcados (LoT, Smartphones, sensores)
- **Caracteristicas principais:**
- Pequenos, moveis, com bateria limitada.
- Conectividade sem fio (Wi-fi, bluetooth, 4|G/5G)
- Configurados diretamente pelo usuario (Não requerem administração especializada)
# Desafios principais 
- Instabilidade: Conexões intermintentes e mudanças de contexto frequentes.
- Autodescoberta: O Sistema deve identificar e adaptar-se ao ambiente automaticamente.
- Heterogeneidade: Diversidade de dispositivos, protocolos e redes.
- Eficiencia energetica: Dispositivos com recursos limitados (CPU, memoria, bateria)
# Requisito essencias
### Adaptação continua a mudanças de contexto:
- Ex: trocaar automaticamente de rede (Wi-fi para 4g) se a conexão falhar
### Configuração simplificada pelo usuario:
- Interfaces intuitivas ou configuração automatica (plug-and-play)
### Acesso facil a recursos:
- Armazenamento, compartilhamento e gerenciamento de dados simplificados.
### Sincronização tolerante a falhas:
- Lidar com desconexões frequentes sem perda de dados.
# Abstração vs. Transparencia
## Abstração tradicional (Sistemas classicos):
- Oculta detalhes complexos do usuario.
## Sistemas perversivos:
- Menos abstração é melhor: usuario deve entender aspectos basicos da distribuição (ex: quais dispositivos estão conectados)
- Justificativa : Facilita a adaptação a cenarios dinamicos (Ex: smarthomes)
## Caso de uso: Ambiente de smart home/office
### Cenario : 
- Usuario acessa serviços em redes diferentes (internet, intranet, rede domestica)
- Dispositivos envolvidos : Notebook (wi-fi), smartphone (4G + GPS), camera digital, impressora.
### Requisitos : 
- **Operação espontanea:** Associações dinamicas entre dispositivos (ex: camera -> projetor).
- **Descoberta automatica de serviços:**
- Ex : Smartphone detecta impressora na rede local sem configuração manual
# Middleware para sistemas pervasivos
- **Protocolos de descoberta:** UPnP (Universal Plug and Play), mDNS (multicast DNS)
- **Comunicação assincrona:** Para lidar com dispositivos intermitentes (Ex: MOTT Para LoT)
- **Otimização de energia:**
	- Redução de overhead de comunicação (ex CoAP para dispositivos restritos)