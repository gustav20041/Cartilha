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

<!-- PARTE 5: PROTOCOLO DE RESPOSTA A INCIDENTES -->
    <div class="alert-box">
        <h3 style="color: #dc3545; margin-top: 0; display: flex; align-items: center; gap: 8px;">
            🚨 5. Protocolo de Resposta a Incidentes (Contenção Pós-Clique)
        </h3>
        <p>Caso o colaborador perceba que interagiu com um link malicioso ou forneceu credenciais em uma página fraudulenta, deve executar imediatamente o seguinte fluxograma de contenção de danos:</p>
        
        <ol style="line-height: 1.8; margin-bottom: 0;">
            <li><strong>Isolamento Imediato do Dispositivo:</strong> Desative a conexão Wi-Fi e remova o cabo de rede Ethernet do computador ou celular atingido. <em>Objetivo:</em> Interromper a comunicação de eventuais malwares com servidores de Comando e Controle (C2) e bloquear a exfiltração de dados em tempo real.</li>
            <li><strong>Alteração de Credenciais em Dispositivo Limpo:</strong> Acesse contas corporativas, bancárias e pessoais utilizando um dispositivo comprovadamente seguro (ex.: smartphone através de dados móveis) e altere todas as senhas comprometidas. Ative obrigatoriamente o Múltiplo Fator de Autenticação (MFA) e encerre as sessões ativas remotamente.</li>
            <li><strong>Notificação Imediata à Equipe de TI ou SOC:</strong> Informe o setor de segurança da informação da empresa sem demora. Forneça o endereço exato da URL maliciosa (sem reabri-la) e especifique se houve inserção de credenciais ou download de arquivos para auditoria forense rápida.</li>
        </ol>
    </div>
