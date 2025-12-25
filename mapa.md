graph LR
    classDef js fill:#f9f,stroke:#333,stroke-width:2px,color:black;
    classDef html fill:#bbf,stroke:#333,stroke-width:2px,color:black;
    classDef action fill:#ffd700,stroke:#333,stroke-width:1px,color:black;

    subgraph JAVASCRIPT ["JAVASCRIPT (O Quartel General)"]
        direction TB
        V_Campo[var campoPalpite]:::js
        V_Botao[var envioPalpite]:::js
        V_Result[var ultimoResultado]:::js
        V_Palpites[var palpites]:::js
        V_Tentativas[var tentativasRestantes]:::js
    end

    subgraph ACOES ["O CANAL (Métodos de Seleção)"]
        Q_Sel[".querySelector()"]:::action
        Get_ID["getElementById()"]:::action
    end

    subgraph HTML_DOC ["HTML (O Campo de Batalha)"]
        direction TB
        H_Input["< input class='campoPalpite' >"]:::html
        H_Btn["< input type='submit' class='envioPalpite' >"]:::html
        H_P_Result["< p class='ultimoResultado' >"]:::html
        H_P_Palpite["< p class='palpites' >"]:::html
        H_Span_Tent["< span id='tentativasRestantes' >"]:::html
    end

    V_Campo -->|Busca pela Classe| Q_Sel
    V_Botao -->|Busca pela Classe| Q_Sel
    V_Result -->|Busca pela Classe| Q_Sel
    V_Palpites -->|Busca pela Classe| Q_Sel
    V_Tentativas -->|Busca pelo ID| Get_ID

    Q_Sel --> H_Input
    Q_Sel --> H_Btn
    Q_Sel --> H_P_Result
    Q_Sel --> H_P_Palpite
    Get_ID --> H_Span_Tent