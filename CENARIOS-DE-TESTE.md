# 📝 Meus Cenários de Teste e Refinamento

Neste documento, registro como transformo requisitos de negócio (muitas vezes ambíguos) em cenários de teste sólidos, aplicando a mentalidade de **Shift Left** e foco na experiência do usuário (UX).

---

## 🚨 Caso 01: O Botão de Emergência (App Hospitalar)

Um requisito simples como *"O app deve ter um botão de emergência"* esconde diversos "fios soltos" que o QA deve identificar no início do ciclo (SDLC).

### 1. Análise de Ambiguidade
Ao analisar o requisito, levantei os seguintes questionamentos:
* **Ação:** O que acontece no clique? (Chamada de voz, SMS ou alerta no painel do hospital?)
* **Feedback:** O usuário recebe uma confirmação de que o socorro está a caminho?
* **Localização:** O sistema precisa capturar o GPS automaticamente?

### 2. Refinamento de UX (Prevenção de Erro)
Durante a análise de riscos, identifiquei a possibilidade de acionamentos indevidos por cliques acidentais. Propus a inclusão de uma etapa de confirmação rápida (pop-up) para validar a real intenção do usuário antes de mobilizar recursos de emergência, evitando custos operacionais desnecessários.

### 3. Matriz de Cenários de Teste

| ID | Cenário | Tipo | Resultado Esperado (Critério de Aceitação) |
| :--- | :--- | :--- | :--- |
| **CT-01** | Acionamento com Internet (4G/Wi-Fi) | Positivo | Sistema solicita confirmação ("Deseja acionar?"). Após o "Sim", envia GPS + Mensagem de confirmação. |
| **CT-02** | Prevenção de Clique Acidental | Negativo | Ao clicar, o sistema **não** aciona direto; exibe pop-up de confirmação. Se clicar em "Cancelar", o fluxo é interrompido. |
| **CT-03** | Acionamento Sem Internet (Offline) | Exceção | Sistema detecta falta de rede e sugere/abre o discador nativo (ex: 192) após a confirmação. |
| **CT-04** | GPS Desativado no Aparelho | Exceção | Sistema solicita permissão de localização ou orienta busca manual para garantir a precisão do socorro. |

> **Nota de Estratégia:** Os cenários acima foram selecionados com base na criticidade e impacto para o negócio, priorizando a segurança do paciente em situações de falha tecnológica.

---
[⬅️ Voltar para o Início](./README.md)
