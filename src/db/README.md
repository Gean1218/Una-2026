## Arquivo .sql

CREATE TABLE Empreendedor (
    EmpId INTEGER PRIMARY KEY,
    EmpNome VARCHAR(100),
    EmpEmail VARCHAR(100),
    EmpSenha VARCHAR(100)
);

CREATE TABLE Fornecedor (
    ForId INTEGER PRIMARY KEY,
    ForNome VARCHAR(100),
    ForTelefone VARCHAR(20)
);

CREATE TABLE Produto (
    ProId INTEGER PRIMARY KEY,
    ProNome VARCHAR(100),
    ProCategoria VARCHAR(50),
    ProPrecoCusto DECIMAL(10,2),
    ProPrecoVenda DECIMAL(10,2),
    ProQuantidade INTEGER,
    ProEstoqueMinimo INTEGER,
    ForId INTEGER,
    FOREIGN KEY (ForId) REFERENCES Fornecedor(ForId)
);

CREATE TABLE Venda (
    VenId INTEGER PRIMARY KEY,
    VenData DATE,
    VenValor DECIMAL(10,2)
);
 
CREATE TABLE Compra (
    ComId INTEGER PRIMARY KEY,
    ComData DATE,
    ComValor DECIMAL(10,2),
    ForId INTEGER,
    FOREIGN KEY (ForId) REFERENCES Fornecedor(ForId)
);

CREATE TABLE MovimentacaoEstoque (
    MovId INTEGER PRIMARY KEY,
    MovTipo VARCHAR(30),
    MovQuantidade INTEGER,
    MovData DATE,
    ProId INTEGER,
    FOREIGN KEY (ProId) REFERENCES Produto(ProId)
);

CREATE TABLE Relatorio (
    RelId INTEGER PRIMARY KEY,
    RelTipo VARCHAR(50),
    RelData DATE
);
