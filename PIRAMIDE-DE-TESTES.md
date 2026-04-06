# 🏥 Estudo de Caso: Pirâmide de Testes no Setor Hospitalar

Neste estudo, aplico os conceitos da **Pirâmide de Testes** em um cenário real de alta complexidade: a jornada de um paciente em um sistema de gestão hospitalar (ERP).

O objetivo deste modelo é garantir a qualidade desde a base, reduzindo custos de retrabalho e garantindo a segurança do usuário final.

---

## 🔼 A Pirâmide na Prática

### 1. Base: Testes Unitários (Unit Tests) 🌱
**Foco:** Validar a menor unidade de código de forma isolada.
* **Exemplo:** Validação do campo de CPF no cadastro do paciente.
* **O que é testado:** Se o sistema aceita apenas números, possui a quantidade correta de dígitos e se a lógica do dígito verificador funciona.
* **Por que é a base:** É o teste mais rápido e barato. Se o dado nasce errado aqui, ele quebra o faturamento e o prontuário lá na frente.

### 2. Meio: Testes de Integração (Integration Tests) 🌸
**Foco:** Validar a "conversa" entre diferentes módulos do sistema.
* **Exemplo:** O fluxo de **Alta Hospitalar**.
* **O que é testado:** Quando o médico registra a alta, o sistema deve integrar a informação com:
    * **Faturamento:** Para fechamento da conta.
    * **Hotelaria:** Para limpeza e liberação do leito.
* **Objetivo:** Garantir que a informação não se perca entre as "paredes" do sistema.

### 3. Topo: Testes de Sistema / E2E (End-to-End) ☀️
**Foco:** Validar a jornada completa do usuário através da interface (UI).
* **Exemplo:** Fluxo completo da Emergência.
* **O que é testado:** O caminho feliz: Recepção -> Triagem -> Atendimento Médico -> Emissão de Documentos.
* **Objetivo:** Simular o uso real do sistema e garantir que o fluxo principal está fluido e sem travamentos.

---

## 🧠 Insights de Aprendizado

> "Trazer minha bagagem do suporte para o QA me permite entender que um 'bug' no topo da pirâmide muitas vezes é o sintoma de um teste que faltou na base. O foco no negócio é o que diferencia um teste comum de uma estratégia de qualidade real."

--
--
![Pirâmide de Testes Hospitalar](piramide.png)


---
[⬅️ Voltar para o Início](./README.md)
