# Cartilha de Segurança: Vulnerabilidades Humanas e IA no Ambiente Corporativo

> **Projeto de Graduação - Segurança da Informação**  
> Fatec Ourinhos | Centro Paula Souza  
> **Autores:** Adriano Bernardes Lemes e Gustavo Borges de Jesus Machado  
> **Orientador:** Prof. Me. Carlos Alexandre Carvalho Tojeiro  

## Objetivo
Esta cartilha foi desenvolvida para ajudar colaboradores e empresas a identificarem e mitigarem ataques de Engenharia Social, que hoje representam a maior vulnerabilidade na Segurança da Informação. Com o avanço da Inteligência Artificial (IA), os ataques tornaram-se mais convincentes, explorando nossas emoções e falhas cognitivas.

---

## 1. O Fator Humano: Por que caímos em golpes?
Os cibercriminosos não precisam "hackear" sistemas complexos se puderem convencer um humano a abrir a porta. Eles exploram **falhas cognitivas** (dificuldade momentânea de processar informações de forma lógica) utilizando gatilhos emocionais:

* **Urgência e Medo:** *"Sua conta será bloqueada em 2h se você não clicar aqui."* (Desliga o pensamento crítico).
* **Autoridade:** E-mails falsos se passando por diretores (CEO Fraud) ou suporte de TI.
* **Curiosidade e Ganância:** Ofertas imperdíveis ou prêmios falsos (Baiting).

---

## 2. A Evolução dos Ataques com Inteligência Artificial
A IA elevou a Engenharia Social a um novo patamar, eliminando erros de português e permitindo ataques em massa altamente personalizados.

### Phishing (E-mail e Mensagens)
Textos gerados por IA são usados para criar e-mails falsos perfeitos, simulando o tom de voz da liderança da empresa ou de fornecedores conhecidos.

### Vishing (Golpes de Voz)
* **Clonagem de Voz:** Com poucos segundos de áudio (extraídos de redes sociais), cibercriminosos clonam a voz de familiares ou chefes.
* **Golpe do PIX:** Ligações simulando pedidos de transferência urgente de dinheiro utilizando vozes sintéticas quase impossíveis de distinguir de vozes reais.

### Deepfakes (Vídeo)
Falsificação de rostos em chamadas de vídeo corporativas para autorizar transferências financeiras fraudulentas.

---

## 3. Boas Práticas e Mitigação: Como se proteger?

### Para o Colaborador (O que fazer na prática)
1. **Desconfie do senso de urgência:** Pare, respire e analise. Bancos e equipes de TI não exigem ações imediatas sob ameaça de bloqueio.
2. **Validação em Dois Canais:** Recebeu um pedido de PIX urgente pelo WhatsApp? Ligue para a pessoa num número oficial para confirmar.
3. **Verifique o remetente:** Clique sobre o nome de quem enviou o e-mail para ver o endereço real (ex: o nome diz "Suporte RH", mas o e-mail é `rh-empresa@gmail.com`).
4. **Cuidado com a exposição nas redes (OSINT):** Reduza postagens excessivas sobre rotina de trabalho; essas informações alimentam a IA dos criminosos.

### Para a Empresa (Políticas Corporativas)
* Implementar **Múltiplos Fatores de Autenticação (MFA)** em todos os sistemas.
* Adotar o princípio do **Privilégio Mínimo (Zero Trust)**.
* Realizar **treinamentos contínuos** e testes simulados de phishing com os colaboradores.

---

## 4. Teste seus Conhecimentos!
Você consegue identificar um ataque de Engenharia Social gerado por IA? Participe da nossa simulação interativa e ajude na nossa pesquisa!  
👉 **[Acessar o Simulado de Phishing (Google Forms)](https://docs.google.com/forms/d/e/1FAIpQLSdfIIg2xh5GQxBJdcCAbOcPIu-ns7g_zCjogYTsLSvxYVv7aQ/viewform)**

---

## Referências e Ferramentas Úteis
* [Teste de Phishing do Google Jigsaw](https://phishingquiz.withgoogle.com/)
* Base de Vulnerabilidades: [CVE.org](https://www.cve.org/)
* Cartilha CERT.br: [Cartilha de Segurança para Internet](https://cartilha.cert.br/)

*Este material é parte integrante do Trabalho de Conclusão de Curso da Fatec Ourinhos (2026).*

---

---

---

> ## 🚨 5. Protocolo de Resposta a Incidentes: Guia Prático Pós-Clique (Contenção Imediata)
> 
> Caso o colaborador identifique ou suspeite de uma interação maliciosa (clique em *phishing*, execução de carga maliciosa ou fornecimento de credenciais corporativas), o plano de ação imediata segue as diretrizes de contenção rápida:
> 
> 1. **Isolamento Físico e Lógico do Endpoint (Contenção Inicial):**
>    * **Ação:** Desative imediatamente o Wi-Fi, retire o cabo de rede Ethernet e desative conexões Bluetooth do computador ou dispositivo móvel afetado.
>    * **Fundamentação Técnica:** Interrompe instantaneamente o tráfego de rede e bloqueia o contato do *payload* com servidores de Comando e Controle (C2), prevenindo o *Lateral Movement* (movimento lateral na rede interna) e a exfiltração em massa de dados confidenciais.
> 
> 2. **Higienização de Credenciais e Revogação de Sessões (Mitigação de Impacto):**
>    * **Ação:** Utilizando um **dispositivo limpo e seguro** (como um smartphone pessoal conectado exclusivamente à rede móvel 4G/5G), acesse os painéis de controle das contas comprometidas (e-mail corporativo, VPN, sistemas internos).
>    * **Fundamentação Técnica:** Altere as senhas de acesso, force o encerramento remoto de todas as sessões ativas (*Token Revocation*) e certifique-se de que o **Múltiplo Fator de Autenticação (MFA)** com chaves de segurança ou aplicativo autenticador esteja rigorosamente ativo.
> 
> 3. **Notificação Forense e Acionamento do SOC / Equipe de TI:**
>    * **Ação:** Comunique formalmente o Centro de Operações de Segurança (SOC) ou o suporte técnico da organização, fornecendo o link exato (URL) ou o anexo suspeito **sem reabri-los**, além de detalhar se houve digitação de credenciais.
>    * **Fundamentação Técnica:** Permite que a equipe de resposta a incidentes isole logs de rede, realize a análise forense do host e inicie rapidamente os procedimentos de erradicação e recuperação do perímetro corporativo.
