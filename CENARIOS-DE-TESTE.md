# 📝 Escrita de Cenários de Teste e Análise de Requisitos

Neste documento, registro como transformo requisitos de negócio (muitas vezes ambíguos) em cenários de teste sólidos, aplicando a mentalidade de **Shift Left** e foco na experiência do usuário (UX).

---

## 🚨 Caso de Estudo: O Botão de Emergência (App Hospitalar)

Um requisito simples como *"O app deve ter um botão de emergência"* esconde diversos "fios soltos" que o QA deve identificar no início do ciclo (SDLC).

### 1. Análise de Ambiguidade
Ao analisar o requisito, levantei os seguintes questionamentos:
* **Ação:** O que acontece no clique? (Chamada de voz, SMS ou alerta no painel do hospital?)
* **Feedback:** O usuário recebe uma confirmação de que o socorro está a caminho?
* **Localização:** O sistema precisa capturar o GPS automaticamente?

### 2. Cenários de Teste (Positivos e de Exceção)

#### **Cenário 01: Acionamento Padrão (Caminho Feliz)**
* **Objetivo:** Validar o acionamento com conexão estável.
* **Comportamento Esperado:** Ao clicar no botão e confirmar, o sistema envia as coordenadas GPS para a central e exibe a mensagem: "Socorro acionado. Aguarde no local."

#### **Cenário 02: Acionamento Offline (Resiliência)**
* **Objetivo:** Garantir que o paciente não fique desamparado sem internet.
* **Comportamento Esperado:** O sistema detecta a falta de conexão e abre automaticamente o discador do celular com o número da emergência (Ex: 192) preenchido.

---

## 📅 Caso de Estudo: Agendamento de Consultas

**Regra de Negócio:** Prevenir conflitos e garantir o preparo do paciente.

| Cenário | O que o QA valida | Valor para o Negócio |
| :--- | :--- | :--- |
| **Concorrência** | Dois usuários tentando o mesmo horário. | Evita agendamentos duplicados. |
| **Preparo de Exame** | Alerta de jejum ou exames prévios. | Evita que o paciente perca a viagem/horário. |
| **Cancelamento** | Médico desmarca o dia. | Garante que o paciente seja avisado via push/SMS. |

---

> "Testar não é apenas verificar se o botão funciona, é garantir que o sistema se comporte de forma inteligente quando as condições não são ideais."
