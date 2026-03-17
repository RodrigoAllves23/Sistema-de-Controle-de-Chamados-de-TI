# 📌 Sistema de Controle de Chamados de TI

## 👥 Grupo
- Beatriz Moscareli 
- Bruno Rodrigues 
- Cayky Victor Hermann 
- Henrique de Souza
- João Vitor Martins dos Santos
- Marcos Munir Moreira Melo da Silva
- Rodrigo Alves dos Santos

## 📅 Versão
**2.0 – 25/02/2026**

---

## 🏢 Visão Geral da Empresa

A empresa é uma rede de supermercados de pequeno porte com cinco lojas, que precisa registrar e gerenciar problemas técnicos internos, como falhas em:

- Computadores  
- Impressoras  
- Sistemas internos  
- Equipamentos de rede  

Atualmente, os registros são feitos em planilhas e anotações manuais, sem controle estruturado ou histórico confiável.

---

## ⚠️ Problema Atual

### ❌ Situação Atual
- Não existe controle de login  
- Falta rastreabilidade de ações  
- Não há histórico de movimentações  
- Status não são controlados corretamente  

### 🚨 Consequências
- Perda de informações  
- Dificuldade de priorização  
- Falta de auditoria  
- Retrabalho  

---

## 🎯 Objetivo da Solução

### 🧩 Objetivo Principal
Desenvolver um sistema simples, estruturado e seguro para:

- Registrar chamados  
- Controlar acesso via login  
- Acompanhar andamento  
- Registrar histórico completo  
- Finalizar chamados com regras definidas  

### ✅ Benefícios Esperados
- Organização centralizada  
- Controle de acesso  
- Histórico detalhado  
- Auditoria de alterações  
- Maior agilidade no suporte  

---

## 👤 Perfis de Usuário

### 🛠️ Operador

**Permissões:**
- Realizar login  
- Cadastrar categorias  
- Abrir chamados  
- Alterar status  
- Registrar observações  
- Visualizar histórico  
- Listar e filtrar chamados  

---

## 📦 Escopo do Sistema

### ✅ Dentro do Escopo (IN)
- Login de usuário  
- Cadastro de categorias  
- Cadastro de níveis de prioridade (Estágio 1, 2 e 3)  
- Abertura de chamados  
- Alteração de status  
- Registro de histórico  
- Inserção de observações  
- Finalização de chamados  
- Listagem de chamados  
- Filtro por status  
- Visualização de histórico completo  

### ❌ Fora do Escopo (OUT)
- Múltiplos perfis de usuário  
- Envio de e-mails  
- Sistema web/mobile  
- Dashboard com gráficos  
- Integrações externas  

---

## 🔄 Fluxo do Sistema

### 🔐 1. Login
1. Usuário acessa o sistema  
2. Realiza cadastro (usuário e senha)  
3. Sistema solicita credenciais  
4. Validação  
   - ✔️ Válido → acesso liberado  
   - ❌ Inválido → mensagem de erro  

---

### 📝 2. Abertura de Chamado
1. Selecionar “Novo Chamado”  
2. Informar:
   - Descrição (obrigatória)  
   - Categoria  
   - Prioridade  
3. Sistema:
   - Valida dados  
   - Gera ID automático  
   - Registra data/hora  
   - Define status como **Aberto**  
4. Cria histórico inicial  

---

### 🔧 3. Andamento

**Status disponíveis:**
- Aberto  
- Em Atendimento  
- Aguardando Peça  
- Aguardando Usuário  
- Em Observação  
- Concluído  

**A cada alteração:**
- Registro de data/hora  
- Usuário responsável  
- Status anterior e novo  
- Observação (se houver)  

---

### ✅ 4. Finalização

**Regras:**
- Só pode finalizar se estiver **Em Atendimento**  
- Após finalizado:
  - Status = Concluído  
  - Não pode mais ser alterado  
  - Histórico é encerrado  

---

## 📋 Requisitos Funcionais (RF)

- RF01 – Login de usuário  
- RF02 – Cadastro de categoria  
- RF03 – Registrar chamado  
- RF04 – Data/hora automática  
- RF05 – Status inicial = Aberto  
- RF06 – Alterar status  
- RF07 – Registrar histórico  
- RF08 – Inserir observações  
- RF09 – Finalizar chamado  
- RF10 – Listar chamados  
- RF11 – Filtrar por status  
- RF12 – Visualizar histórico  

---

## 📏 Regras de Negócio (RN)

- RN01 – Descrição obrigatória  
- RN02 – Status inicial: Aberto  
- RN03 – Finalização apenas em “Em Atendimento”  
- RN04 – Chamado finalizado não pode ser alterado  
- RN05 – Toda alteração gera histórico  
- RN06 – Data de abertura imutável  
- RN07 – Login obrigatório  
- RN08 – Histórico não pode ser editado/excluído  

---

## ⚙️ Requisitos Não Funcionais (RNF)

- RNF01 – Desenvolvido em Java  
- RNF02 – Persistência local (JSON ou CSV)  
- RNF03 – Funcionamento offline  
- RNF04 – Interface simples e intuitiva  
- RNF05 – Suporte até 500 chamados  
- RNF06 – Validação de login obrigatória  

---

## 🗂️ Entidades do Sistema

### 👤 Usuario
- id  
- nome  
- login  
- senha  

### 📁 Categoria
- id  
- nome  
- descrição  

### 📌 Chamado
- id  
- descrição  
- dataAbertura  
- statusAtual  
- prioridade  
- categoria  
- usuarioAbertura  

### 🕓 HistoricoChamado
- id  
- chamado  
- dataHora  
- usuario  
- statusAnterior  
- statusNovo  
- observacao  

### 🔄 StatusChamado
- Aberto  
- Em Atendimento  
- Aguardando Peça  
- Aguardando Usuário  
- Em Observação  
- Concluído  

---

## 🎯 Casos de Uso

1. Realizar Login  
2. Cadastrar Categoria  
3. Abrir Chamado  
4. Alterar Status  
5. Registrar Observação  
6. Finalizar Chamado  
7. Listar Chamados  
8. Filtrar Chamados  
9. Visualizar Histórico  

---

## 🧪 Cenários de Uso

### ✅ Cenário 1 – Fluxo Ideal
1. Usuário faz login  
2. Abre chamado  
3. Status = Aberto  
4. Alterado para Em Atendimento  
5. Alterado para Concluído  
6. Histórico registrado  
7. Chamado encerrado  

---

### ❌ Cenário 2 – Erro de Finalização
1. Usuário tenta finalizar chamado em “Aberto”  
2. Sistema valida regra RN03  
3. Exibe mensagem:

> ⚠️ “Chamado precisa estar em Atendimento antes de ser finalizado.”

4. Operação cancelada  
