# projeto-2-cibersecurity
# Hardening, Firewall, WAF (ModSecurity) e Resposta a Incidentes

## 📌 Visão Geral

Este projeto consiste em um ambiente prático (hands-on) para configuração de hardening, firewall, implementação de WAF com ModSecurity (OWASP Core Rule Set) e simulação de ataques cibernéticos com o objetivo de coletar logs e executar um fluxo de resposta a incidentes seguindo o modelo **NIST Incident Response (IR)**.

O ambiente foi composto por:

* **Container atacante**: Kali Linux
* **WAF**: ModSecurity + OWASP CRS
* **Aplicação alvo**: DVWA (Damn Vulnerable Web Application)
* **Monitoramento de logs**: Dozzle

A entrega inclui relatório, prints/logs e diagrama da arquitetura.

---

## 🎯 Objetivos do Projeto

* Aplicar hardening e firewall em ambiente controlado.
* Configurar o ModSecurity com OWASP Core Rule Set.
* Simular ataques SQL Injection (SQLi) e Cross-Site Scripting (XSS) contra a DVWA.
* Coletar evidências via logs (ModSecurity e Dozzle).
* Analisar e responder ao incidente com base no fluxo do **NIST IR**:

  * *Preparation*
  * *Detection & Analysis*
  * *Containment, Eradication & Recovery*
  * *Post-Incident Activity*

---

## 🔧 Configuração do Ambiente

### Componentes principais

* **DVWA**: Aplicação vulnerável utilizada como alvo dos testes.
* **ModSecurity + OWASP CRS**: WAF configurado em modo *blocking*, inspecionando tráfego HTTP.
* **Kali Linux**: Ambiente atacante usado para executar vetores de ataque.
* **Dozzle**: Ferramenta para visualizar logs dos containers em tempo real.

### ModSecurity

* Configurado em modo **"Detection + Blocking"**.
* OWASP CRS habilitado.
* Logs armazenados e monitorados durante toda a simulação.

---

## 🛡️ Ataques Simulados

Foram executados dois tipos de ataques:

### 1. **SQL Injection (SQLi)**

* Vetores de SQLi foram enviados para campos vulneráveis da DVWA.
* O ModSecurity identificou o ataque e bloqueou a requisição.
* **ID da regra acionada:** `942100`
* **Resposta:** `403 Forbidden`

### 2. **Cross-Site Scripting (XSS)**

* Scripts maliciosos foram inseridos nos campos vulneráveis.
* O ModSecurity detectou e bloqueou a tentativa.
* **ID da regra acionada:** `941100`
* **Resposta:** `403 Forbidden`


---

## 📝 Conclusão

O ambiente foi configurado com sucesso e o WAF ModSecurity, utilizando o OWASP CRS, demonstrou efetividade ao identificar e bloquear ataques SQLi e XSS. O processo de coleta de logs e análise possibilitou simular um fluxo de resposta a incidentes seguindo o modelo NIST IR.

As evidências demonstram que o sistema reagiu conforme esperado, reforçando a importância da camada WAF em ambientes expostos.

---

## 📎 Anexos

* Logs do ModSecurity
* Prints da execução dos ataques
* Diagrama da arquitetura
