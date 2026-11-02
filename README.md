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

## 6. Calculadora de Risco Pós-Clique (Simulador de Avaliação Interativo)
*Marque o que ocorreu após o clique para calcular o nível de ameaça em tempo real:*

<div style="background-color: #1e293b; color: white; padding: 20px; border-radius: 8px; font-family: sans-serif; max-width: 650px;">
  <form id="calcRiscoForm" style="margin-bottom: 15px;">
    <label style="display: block; margin-bottom: 10px; cursor: pointer;">
      <input type="checkbox" id="chkDownload" onchange="atualizarCalculoRisco()" style="transform: scale(1.2); margin-right: 8px;">
      Baixou ou executou algum arquivo desconhecido
    </label>
    <label style="display: block; margin-bottom: 10px; cursor: pointer;">
      <input type="checkbox" id="chkSenha" onchange="atualizarCalculoRisco()" style="transform: scale(1.2); margin-right: 8px;">
      Inseriu senhas ou dados corporativos na página falsa
    </label>
    <label style="display: block; margin-bottom: 10px; cursor: pointer;">
      <input type="checkbox" id="chkRede" onchange="atualizarCalculoRisco()" style="transform: scale(1.2); margin-right: 8px;">
      O dispositivo continua conectado à rede interna da empresa
    </label>
  </form>

  <div style="background-color: #0f172a; padding: 15px; border-radius: 6px; display: flex; align-items: center; justify-content: space-between; border: 1px solid #334155;">
    <div>
      <span style="font-size: 0.85em; color: #94a3b8; text-transform: uppercase; letter-spacing: 0.5px;">Nível de Ameaça Estimado:</span>
      <h2 id="pctRiscoTexto" style="margin: 5px 0 0 0; color: #22c55e; font-size: 1.8em;">15% (Baixo)</h2>
    </div>
    <div id="statusBadgeRisco" style="background-color: #22c55e; color: #000; padding: 8px 14px; border-radius: 20px; font-weight: bold; font-size: 0.8em; text-align: center;">
      RISCO CONTROLADO
    </div>
  </div>
</div>

<script>
function atualizarCalculoRisco() {
  let risco = 15;
  const download = document.getElementById('chkDownload').checked;
  const senha = document.getElementById('chkSenha').checked;
  const rede = document.getElementById('chkRede').checked;

  if (download) risco += 40;
  if (senha) risco += 35;
  if (rede && (download || senha)) risco += 10;

  const pctElem = document.getElementById('pctRiscoTexto');
  const badgeElem = document.getElementById('statusBadgeRisco');

  if (risco >= 70) {
    pctElem.innerText = risco + "% (Crítico)";
    pctElem.style.color = "#ef4444";
    badgeElem.innerText = "ALTO RISCO - ISOLAR REDE";
    badgeElem.style.backgroundColor = "#ef4444";
    badgeElem.style.color = "#ffffff";
  } else if (risco >= 40) {
    pctElem.innerText = risco + "% (Moderado)";
    pctElem.style.color = "#f59e0b";
    badgeElem.innerText = "ATENÇÃO NECESSÁRIA";
    badgeElem.style.backgroundColor = "#f59e0b";
    badgeElem.style.color = "#000000";
  } else {
    pctElem.innerText = risco + "% (Baixo)";
    pctElem.style.color = "#22c55e";
    badgeElem.innerText = "RISCO CONTROLADO";
    badgeElem.style.backgroundColor = "#22c55e";
    badgeElem.style.color = "#000000";
  }
}
</script>
