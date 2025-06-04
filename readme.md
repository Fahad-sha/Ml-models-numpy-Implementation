graph TD
    A[Start] --> B[Input Data: Features X, Target y];
    B --> C[Initialize Parameters: weight w, bias b <br>(e.g., random values or zeros)];
    C --> D[Set Hyperparameters: <br>Learning Rate α, <br>Number of Iterations N_iter];
    D --> E[Set m = number of training examples];
    E --> F{FOR iteration = 1 TO N_iter};
    F -- Loop Start --> G[Calculate Predictions (Forward Pass)<br>ŷ = wX + b <br><i>(Equation 1)</i>];
    G --> H[Calculate Cost (e.g., MSE)<br>J(w,b) = (1/2m) Σ(ŷ - y)²<br><i>(Equation 3)</i>];
    H --> I[Calculate Gradients (Backward Pass)<br>∂J/∂w = (1/m) Σ((ŷ - y)X)<br>∂J/∂b = (1/m) Σ(ŷ - y)<br><i>(Equations 4 & 5)</i>];
    I --> J[Update Parameters<br>w = w - α * ∂J/∂w<br>b = b - α * ∂J/∂b<br><i>(Equations 6 & 7)</i>];
    J -- Loop End --> F;
    F -- Iterations Complete --> K[Output Final Optimized Parameters: w, b];
    K --> L[End];

    %% Styling (optional, for better visualization in some renderers)
    classDef default fill:#f9f,stroke:#333,stroke-width:2px;
    classDef process fill:#ccf,stroke:#333,stroke-width:2px;
    classDef decision fill:#ff9,stroke:#333,stroke-width:2px; %% decision is for diamond shape
    classDef io fill:#9cf,stroke:#333,stroke-width:2px; %% Using 'io' for general process for now

    class A,L default;
    class B,C,D,E,G,H,I,J,K io; %% Changed these to 'io' or can be 'process'
    class F decision; %% F is a decision/condition node
    