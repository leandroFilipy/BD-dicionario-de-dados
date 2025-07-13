# 📦 Sistema de Gestão de Produção e Vendas

Este repositório contém o **dicionário de dados** de um sistema de gerenciamento de produtos, matérias-primas, funcionários, fornecedores, vendas e pedidos. O objetivo é organizar e manter uma base de dados eficiente para controle de processos industriais.

---

## 🗂️ Estrutura do Banco de Dados

### 🛍️ Tabela: `PRODUCTS`
| Coluna             | Tipo         | Restrição           |
|--------------------|--------------|---------------------|
| ID_PRODUCTS        | INT          | PK, AUTO_INCREMENT  |
| NAME_PRODUCTS      | VARCHAR(50)  | NOT NULL            |
| DESCRIPTION_PRODUCT| TEXT         | NULL                |
| PRICE              | DECIMAL(6,2) | NOT NULL            |
| AVAILABLE_IN_STOCK | INT          | NOT NULL            |
| SIZE               | VARCHAR(50)  | NULL                |
| VERSIONS           | VARCHAR(50)  | NULL                |
| SUPPLIERS_ID       | INT          | FK                  |

---

### 👨‍🏭 Tabela: `FUNCIONARIOS`
| Coluna             | Tipo         | Restrição           |
|--------------------|--------------|---------------------|
| ID_FUNCIONARIO     | INT          | PK, AUTO_INCREMENT  |
| NOME_FUNCIONARIO   | VARCHAR(50)  | NOT NULL            |
| CARGO              | VARCHAR(50)  | NOT NULL            |
| DATA_DE_CONTRATAÇÃO| DATE         | NOT NULL            |
| SALARIO            | DECIMAL(6,2) | NOT NULL            |
| FABRICA            | VARCHAR(50)  | NULL                |

---

### 🏭 Tabela: `SUPPLIERS`
| Coluna             | Tipo         | Restrição           |
|--------------------|--------------|---------------------|
| SUPPLIERS_ID       | INT          | PK, AUTO_INCREMENT  |
| NAMEE              | VARCHAR(50)  | NOT NULL            |
| TELEPHONE          | CHAR(14)     | NOT NULL            |
| ADDRESS            | VARCHAR(50)  | NOT NULL            |
| TYPE_OF_MATERIALS  | VARCHAR(50)  | NOT NULL            |

---

### 🧱 Tabela: `RAW_MATERIALS`
| Coluna             | Tipo           | Restrição           |
|--------------------|----------------|---------------------|
| RAW_MATERIAL_ID    | INT            | PK, AUTO_INCREMENT  |
| NAME               | CHAR(50)       | NOT NULL            |
| AVAILABLE_QUANTITY | INT            | NOT NULL            |
| ACQUISITION_COST   | DECIMAL(10,2)  | NOT NULL            |

---

### 🛠️ Tabela: `PRODUCTIONS`
| Coluna             | Tipo         | Restrição           |
|--------------------|--------------|---------------------|
| ID_PRODUCTS        | INT          | PK, AUTO_INCREMENT  |
| CREATION_DATE      | DATE         | NOT NULL            |
| CONCLUSION_DATE    | DATE         | NULL                |
| STATUS_OF_PRODUCTIONS | CHAR(50)  | NULL                |
| PRODUCTS_ID        | INT          | FK                  |

---

### 📦 Tabela: `ORDERS`
| Coluna             | Tipo      | Restrição           |
|--------------------|-----------|---------------------|
| ORDER_ID           | INT       | PK, AUTO_INCREMENT  |
| RAW_MATERIAL_ID    | INT       | FK                  |
| DATE_ORDER         | DATETIME  | -                   |

---

### 💰 Tabela: `SALES`
| Coluna             | Tipo           | Restrição           |
|--------------------|----------------|---------------------|
| SALE_ID            | INT            | PK, AUTO_INCREMENT  |
| SALES_DATE         | DATE           | -                   |
| WHO_BOUGHT         | VARCHAR(50)    | -                   |
| SALES_TOTAL        | DECIMAL(10,2)  | -                   |
| WORKER_ID          | INT            | FK (FUNCIONARIOS)   |
| ID_DEPARTAMENTO    | INT            | FK (DEPARTAMENTOS)  |

---

### 🔗 Tabela: `SALES_PRODUCTS`
| Coluna      | Tipo | Restrição                             |
|-------------|------|----------------------------------------|
| SALE_ID     | INT  | FK (referência SALES.SALE_ID)         |
| PRODUCT_ID  | INT  | FK (referência PRODUCTS.ID_PRODUCTS)  |

---

## 🧠 Observações

- As tabelas foram normalizadas para facilitar integridade referencial.
- Uso de `AUTO_INCREMENT` para IDs únicos.
- Relações bem definidas com `FOREIGN KEY` entre tabelas dependentes.

---

## 📄 Licença

Este projeto é de livre uso acadêmico e educacional. Licenciado sob a [MIT License](LICENSE).

---

## 🚀 Contribua!

Pull requests são bem-vindos! Para mudanças maiores, abra uma issue antes para discutir o que você gostaria de modificar.

---

