# 🛠️ Painel Interativo & Documentação de Governança — Atendimento de TI

![Modelo ITSM/ITIL v4](https://img.shields.io/badge/Modelo-ITSM%20%2F%20ITIL%20v4-blue)
![Padrão BPMN](https://img.shields.io/badge/Padr%C3%A3o-BPMN%202.0-emerald)
![Status](https://img.shields.io/badge/Status-Homologado-success)

Este repositório contém a solução completa para a **padronização, governança e visualização interativa do processo de suporte e atendimento de TI**. O projeto resolve diretamente a indefinição de papéis e o problema do *"ping-pong"* de chamados através de uma plataforma integrada e documentação de governança operacional.

---

## 📌 Visão Geral do Projeto

A solução foi desenvolvida com base nas melhores práticas do **ITSM** (*IT Service Management*) e do **ITIL v4**. Ela fornece uma visão clara do ciclo de vida dos incidentes e solicitações de serviço, delineando objetivamente a pergunta fundamental de qualquer operação técnica: **"Quem faz o que?"**

### Principais Objetivos Alcançados:
* 🎯 **Eliminação de Ambiguidade:** Mapeamento detalhado das responsabilidades de 9 níveis operacionais.
* ⚡ **Redução do MTTR (*Mean Time to Resolve*):** Direcionamento assertivo na triagem inicial, evitando repasses desnecessários.
* 🎓 **Aceleração do Onboarding:** Material didático e dinâmico para treinamento rápido de novos analistas de TI.
* 📊 **Padronização de SLAs:** Tabela consolidada de tempos de resposta e resolução alinhados ao negócio.

---

## 📂 Estrutura de Arquivos do Repositório

| Arquivo | Descrição | Tecnologia |
| :--- | :--- | :--- |
| `fluxo_atendimento_ti.html` | **Aplicação Web Interativa (SPA):** Visualizador de diagrama BPMN 2.0 com suporte a zoom, inspeção de tarefas, catálogo de papéis e matriz de SLA. | HTML5, Tailwind CSS, BPMN.js, JS |
| `documentacao_atendimento_ti.html` | **Manual de Governança (Versão PDF-Ready):** Documento formatado para impressão direta ou geração de PDF A4 via navegador. | HTML5, Tailwind CSS, FontAwesome |
| `documentacao_atendimento_ti.tex` | **Manual de Governança em LaTeX:** Código-fonte LaTeX de alta qualidade tipográfica para compilação formal. | LaTeX (LuaLaTeX / XeLaTeX) |
| `post_linkedin_atendimento_ti.md` | **Texto de Divulgação Interna/Social:** Copy pronto para divulgação no LinkedIn ou portal corporativo. | Markdown |
| `README.md` | **Documentação Principal do Repositório:** Guia geral de utilização e arquitetura da solução. | Markdown |

---

## 🧩 Os 9 Níveis Operacionais ("Quem Faz o Que")

A governança do processo divide a operação em 9 raias (*lanes*) funcionais bem delimitadas:

```
[ Usuário Final ] ➔ [ Service Desk (SPOC) ] ➔ [ Help Desk ]
                                                  │
                                           [ Suporte N1 ]
                                                  │
                                           [ Suporte N2 ] ─── (Nó de Decisão)
                                                  │
      ┌───────────────────┬───────────────────────┼──────────────────────┐
      ▼                   ▼                       ▼                      ▼
[ Suporte N3 ]   [ Analista Redes ]   [ Analista Infraestrutura ]   [ Field Services ]
 (Vendors/Bugs)   (VPN/Wi-Fi/LAN)       (AD/Cloud/Servidores)      (Hardware/Local)
```

1. **Usuário Final (Solicitante):** Abertura do ticket com evidências e validação da solução.
2. **Service Desk (SPOC):** Central de governança, acompanhamento de SLAs globais e comunicação.
3. **Help Desk:** Suporte inicial de primeiro contato (FCR) para dúvidas rápidas e orientações.
4. **Suporte N1:** Atendimento técnico via Procedimentos Operacionais Padrão (SOP), reset de senhas e acessos.
5. **Suporte N2:** Diagnóstico técnico aprofundado, análise de causa e decisões de escalamento.
6. **Suporte N3:** Interface com fabricantes/fornecedores e Gestão de Problemas (causa raiz).
7. **Analista de Redes:** Conectividade, VPN, Wi-Fi corporativo e segurança de perímetro (Firewall).
8. **Analista de Infraestrutura:** Administração de servidores, Active Directory, ambientes Cloud (Azure/AWS) e backups.
9. **Field Services:** Suporte presencial *on-site*, manutenção física de hardware, cabeamento e salas de reunião.

---

## ⏱️ Matriz Operacional de SLA & Regras de Transição

| Nível / Equipe | SLA 1ª Resposta | SLA Resolução | Critério para Escalamento |
| :--- | :---: | :---: | :--- |
| **Service Desk** | 15 min | N/A | Chamado registrado e triado. |
| **Help Desk** | 15 min | 1 hora | Dúvida ou problema simples não solucionado. |
| **Suporte N1** | 30 min | 4 horas | Necessidade de análise técnica além dos roteiros SOP. |
| **Suporte N2** | 1 hora | 8 horas | Transição técnica após diagnóstico da causa. |
| **Suporte N3** | 2 horas | 24–48h | Bug comprovado no código/produto ou dependência de *vendor*. |
| **Analista de Redes** | 1 hora | 6 horas | Incidentes confirmados de conectividade/VPN/Firewall. |
| **Analista de Infra** | 1 hora | 6 horas | Indisponibilidade de servidores, AD, nuvem ou restore de backup. |
| **Field Services** | 2 horas | 8 horas | Defeito físico em hardware, cabeamento ou atendimento *in loco*. |

---

## 🚀 Como Executar e Utilizar

### 1. Painel Interativo (`fluxo_atendimento_ti.html`)
* Não requer instalação de servidor ou banco de dados.
* Basta dar um duplo clique no arquivo `fluxo_atendimento_ti.html` para abri-lo em qualquer navegador moderno (Chrome, Edge, Firefox, Safari).
* **Recursos do Painel:**
  * **Zoom & Pan:** Controles no canto superior esquerdo ou scroll do mouse.
  * **Inspeção de Elementos:** Clique em qualquer tarefa ou raia no diagrama para exibir os detalhes no painel lateral.
  * **Abas de Navegação:** Alternância rápida entre o Diagrama BPMN, Cartões de Papéis e Matriz de SLA.
  * **Exportação SVG:** Botão *"Baixar SVG"* para exportar o diagrama em alta resolução.

### 2. Gerar PDF do Manual de Governança (`documentacao_atendimento_ti.html`)
* Abra o arquivo `documentacao_atendimento_ti.html` no navegador.
* Clique no botão superior **"Salvar / Imprimir em PDF"** (ou pressione `Ctrl + P`).
* Defina o destino como **"Salvar como PDF"** e mantenha a opção de grafismo de segundo plano ativada para preservar a estilização.

### 3. Compilar a Documentação LaTeX (`documentacao_atendimento_ti.tex`)
Para gerar o PDF corporativo a partir do fonte LaTeX:
```bash
lualatex documentacao_atendimento_ti.tex
# ou
xelatex documentacao_atendimento_ti.tex
```

---

## 🛠️ Tecnologias Utilizadas

* **HTML5 / CSS3:** Estruturação semântica e estilização responsiva.
* **Tailwind CSS (via CDN):** Design moderno e utility-first.
* **BPMN.js (`v17.0.2`):** Motor de renderização e navegação vetorial do padrão BPMN 2.0.
* **FontAwesome (`v6.4.0`):** Iconografia técnica e de interface.
* **LaTeX (`XeLaTeX/LuaLaTeX`):** Formatação tipográfica profissional de documentos impressos.

---

## 🔄 Manutenção e Atualização do BPMN

Caso ocorram alterações no fluxo operacional da organização:
1. Edite o processo visual no software de sua preferência (ex: *Camunda Modeler*, *Bizagi* ou *draw.io*).
2. Exporte o arquivo XML BPMN 2.0 atualizado.
3. Abra a constante `bpmnXML` no arquivo `fluxo_atendimento_ti.html` e substitua a string XML pelo novo conteúdo.

---

## 📄 Licença e Uso

Este repositório é disponibilizado como modelo de governança operacional para equipes de Tecnologia da Informação. Sinta-se à vontade para adaptar os fluxos, regras e prazos às particularidades do seu ambiente corporativo.