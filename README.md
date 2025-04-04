# Sistema de Gestão de Ordens de Serviço 🚗🔧

Este projeto contém o modelo lógico de banco de dados para um sistema de gestão de ordens de serviço de uma oficina mecânica.

## 📌 Modelo Entidade-Relacionamento (MER)
Abaixo está a representação do modelo lógico do banco de dados.


## 📋 Tabelas e Relacionamentos

### **Cliente**
- `idCliente` (INT, PK)
- `Nome` (VARCHAR 100)
- `Telefone` (VARCHAR 15)
- `Email` (VARCHAR 100)
- `Endereço` (VARCHAR 255)

### **Veículo**
- `idVeículo` (INT, PK)
- `Placa` (VARCHAR 10)
- `Modelo` (VARCHAR 50)
- `Ano` (INT)
- `Cliente_idCliente` (INT, FK)

### **OS (Ordem de Serviço)**
- `idOS` (INT, PK)
- `data_emissao` (DATE)
- `valor` (DECIMAL 10,2)
- `data_conclusao` (DATE)
- `Equipe_idEquipe` (INT, FK)
- `Status_idStatus` (INT, FK)
- `autorização` (TINYINT)

### **Mecânico**
- `idMecânico` (INT, PK)
- `Nome` (VARCHAR 100)
- `Endereço` (VARCHAR 255)
- `Especialidade` (VARCHAR 100)
- `Equipe_idEquipe` (INT, FK)

### **Equipe**
- `idEquipe` (INT, PK)
- `Nome` (VARCHAR 100)

### **Peça**
- `idPeça` (INT, PK)
- `Descrição` (VARCHAR 255)
- `Valor` (DECIMAL 10,2)

### **Serviço**
- `idServiço` (INT, PK)
- `Descrição` (VARCHAR 255)
- `Valor` (DECIMAL 10,2)

## 🔗 Relacionamentos
- **1 Cliente** → **N Veículos**
- **1 Veículo** → **N Ordens de Serviço**
- **1 Ordem de Serviço** → **N Peças** (via `OS_Peça`)
- **1 Ordem de Serviço** → **N Serviços** (via `OS_Serviço`)
- **1 Equipe** → **N Mecânicos**
- **N Mecânicos** → **N Ordens de Serviço** (via `Mecânico_has_OS`)

---

