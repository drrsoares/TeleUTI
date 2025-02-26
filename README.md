<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Round Matinal - UTI</title>
    <link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
    <link href="https://cdn.jsdelivr.net/npm/flowbite@1.6.5/dist/flowbite.min.css" rel="stylesheet">
    <style>
      :root {
        --primary-color: #5D5CDE;
        --warning-color: #FFC107;
        --danger-color: #DC3545;
        --success-color: #28A745;
      }

      /* Dark mode variables */
      @media (prefers-color-scheme: dark) {
        :root {
          --bg-color: #181818;
          --text-color: #f0f0f0;
          --card-bg: #2a2a2a;
          --border-color: #444;
        }
      }

      /* Light mode variables */
      @media (prefers-color-scheme: light) {
        :root {
          --bg-color: #FFFFFF;
          --text-color: #333333;
          --card-bg: #FFFFFF;
          --border-color: #e0e0e0;
        }
      }

      body {
        font-family: 'Inter', sans-serif;
        background-color: var(--bg-color);
        color: var(--text-color);
        margin: 0;
        padding: 0;
        transition: background-color 0.3s, color 0.3s;
      }

      .container {
        max-width: 1000px;
        margin: 0 auto;
        padding: 1rem;
      }

      .card {
        background-color: var(--card-bg);
        border-radius: 0.5rem;
        box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        padding: 1.5rem;
        margin-bottom: 1.5rem;
        border: 1px solid var(--border-color);
        transition: box-shadow 0.3s ease;
      }

      .card:hover {
        box-shadow: 0 6px 12px rgba(0, 0, 0, 0.15);
      }

      h1, h2, h3 {
        color: var(--primary-color);
        margin-bottom: 1rem;
      }

      .btn {
        padding: 0.5rem 1rem;
        border-radius: 0.25rem;
        font-weight: 500;
        cursor: pointer;
        transition: all 0.2s ease;
        display: inline-flex;
        align-items: center;
        justify-content: center;
        border: none;
        min-height: 2.5rem;
      }

      .btn-primary {
        background-color: var(--primary-color);
        color: white;
      }

      .btn-primary:hover {
        background-color: #4a49b9;
      }

      .btn-danger {
        background-color: var(--danger-color);
        color: white;
      }

      .btn-danger:hover {
        background-color: #c82333;
      }

      .btn-group {
        display: flex;
        gap: 0.5rem;
        margin-top: 1rem;
        flex-wrap: wrap;
      }

      @media (max-width: 768px) {
        .btn-group {
          flex-direction: column;
        }
        
        .btn {
          width: 100%;
        }
      }

      .form-group {
        margin-bottom: 1rem;
      }

      .form-control {
        width: 100%;
        padding: 0.75rem;
        border: 1px solid var(--border-color);
        border-radius: 0.25rem;
        font-size: 1rem;
        transition: border-color 0.2s ease-in-out;
        background-color: var(--bg-color);
        color: var(--text-color);
      }

      .form-control:focus {
        border-color: var(--primary-color);
        outline: none;
        box-shadow: 0 0 0 2px rgba(93, 92, 222, 0.25);
      }

      .form-label {
        display: block;
        margin-bottom: 0.5rem;
        font-weight: 500;
      }

      .invalid {
        border-color: var(--danger-color) !important;
      }

      .validation-message {
        color: var(--danger-color);
        font-size: 0.875rem;
        margin-top: 0.25rem;
      }

      .alert {
        padding: 1rem;
        border-radius: 0.25rem;
        margin-bottom: 1rem;
      }

      .alert-warning {
        background-color: rgba(255, 193, 7, 0.2);
        border: 1px solid var(--warning-color);
        color: #856404;
      }

      .alert-danger {
        background-color: rgba(220, 53, 69, 0.2);
        border: 1px solid var(--danger-color);
        color: #721c24;
      }

      .hidden {
        display: none !important;
      }

      .flex-container {
        display: flex;
        gap: 1rem;
        margin-bottom: 1rem;
      }

      .flex-container > div {
        flex: 1;
      }

      .medication-entry {
        border: 1px solid var(--border-color);
        border-radius: 0.25rem;
        padding: 1rem;
        margin-bottom: 1rem;
        background-color: rgba(0, 0, 0, 0.02);
      }

      .status-indicator {
        display: inline-block;
        width: 12px;
        height: 12px;
        border-radius: 50%;
        margin-left: 0.5rem;
      }

      .status-ok {
        background-color: var(--success-color);
      }

      .status-warning {
        background-color: var(--warning-color);
      }

      .status-danger {
        background-color: var(--danger-color);
      }

      .status-container {
        display: flex;
        align-items: center;
      }

      /* Tabs */
      .tabs {
        display: flex;
        flex-wrap: wrap;
        border-bottom: 1px solid var(--border-color);
        margin-bottom: 1.5rem;
      }

      .tab {
        padding: 0.75rem 1.25rem;
        cursor: pointer;
        transition: all 0.2s ease;
        border-bottom: 2px solid transparent;
        font-weight: 500;
      }

      .tab.active {
        color: var(--primary-color);
        border-bottom: 2px solid var(--primary-color);
      }

      .tab-content {
        display: none;
      }

      .tab-content.active {
        display: block;
      }

      .checkbox-container {
        display: flex;
        align-items: center;
        margin-bottom: 1rem;
      }

      .checkbox-container input[type="checkbox"] {
        width: auto;
        margin-right: 0.5rem;
      }

      .checkbox-container label {
        display: inline;
        font-weight: normal;
      }

      /* Loading Spinner */
      .spinner {
        width: 40px;
        height: 40px;
        border: 4px solid rgba(93, 92, 222, 0.1);
        border-left-color: var(--primary-color);
        border-radius: 50%;
        animation: spin 1s linear infinite;
        margin: 2rem auto;
      }

      @keyframes spin {
        to { transform: rotate(360deg); }
      }

      /* Toast Notification */
      .toast {
        position: fixed;
        top: 1rem;
        right: 1rem;
        padding: 1rem;
        background-color: var(--primary-color);
        color: white;
        border-radius: 0.25rem;
        box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        opacity: 0;
        transition: opacity 0.3s ease;
        z-index: 1000;
      }

      .toast.show {
        opacity: 1;
      }

      @media (max-width: 768px) {
        .flex-container {
          flex-direction: column;
        }
        
        .flex-container > div {
          width: 100%;
        }
      }

      /* Estilos para tabela de resumo */
      .table-container {
        overflow-x: auto;
      }

      table {
        width: 100%;
        border-collapse: collapse;
      }

      th, td {
        padding: 0.75rem;
        text-align: left;
        border-bottom: 1px solid var(--border-color);
      }

      th {
        background-color: rgba(93, 92, 222, 0.1);
        font-weight: 600;
      }

      tr:hover {
        background-color: rgba(0, 0, 0, 0.02);
      }

      /* Fixar sticky tab bar no mobile */
      @media (max-width: 768px) {
        .sticky-tabs {
          position: sticky;
          top: 0;
          background-color: var(--bg-color);
          z-index: 10;
          padding-top: 0.5rem;
        }
      }

      /* Animações */
      @keyframes fadeIn {
        from { opacity: 0; }
        to { opacity: 1; }
      }

      .fade-in {
        animation: fadeIn 0.3s ease forwards;
      }
    </style>
</head>
<body>
  <div class="container">
    <header class="text-center my-6">
      <h1 class="text-2xl font-bold">Round Matinal - UTI</h1>
      <p class="text-sm text-gray-600 dark:text-gray-400">Sistema de avaliação e coleta de dados</p>
    </header>

    <div class="tabs sticky-tabs">
      <div class="tab active" data-tab="identificacao">Identificação</div>
      <div class="tab" data-tab="dispositivos">Dispositivos</div>
      <div class="tab" data-tab="ventilacao">Ventilação</div>
      <div class="tab" data-tab="medicacoes">Medicações</div>
      <div class="tab" data-tab="outros">Outros Parâmetros</div>
      <div class="tab" data-tab="resumo">Resumo</div>
    </div>

    <form id="roundMatinalForm">
      <!-- Identificação do Paciente -->
      <div id="identificacao" class="tab-content active">
        <div class="card">
          <h2 class="text-xl font-semibold">Identificação do Paciente</h2>
          
          <div class="form-group">
            <label for="nomePaciente" class="form-label">Nome:</label>
            <input type="text" id="nomePaciente" name="nomePaciente" class="form-control" placeholder="Digite o nome do paciente" required>
          </div>

          <div class="flex-container">
            <div class="form-group">
              <label for="registroHospitalar" class="form-label">Registro Hospitalar:</label>
              <input type="text" id="registroHospitalar" name="registroHospitalar" class="form-control" placeholder="Digite o registro hospitalar" required>
            </div>
            <div class="form-group">
              <label for="leito" class="form-label">Leito:</label>
              <select id="leito" name="leito" class="form-control" required>
                <option value="" disabled selected>Selecione o leito</option>
                <option value="1">1</option>
                <option value="2">2</option>
                <option value="3">3</option>
                <option value="4">4</option>
                <option value="5">5</option>
                <option value="6">6</option>
                <option value="7">7</option>
                <option value="8">8</option>
                <option value="9">9</option>
                <option value="10">10</option>
              </select>
            </div>
          </div>

          <div class="flex-container">
            <div class="form-group">
              <label for="dataInternacao" class="form-label">Data de Internação:</label>
              <input type="date" id="dataInternacao" name="dataInternacao" class="form-control" required>
            </div>
            <div class="form-group">
              <label for="dataPreenchimento" class="form-label">Data do Preenchimento:</label>
              <input type="date" id="dataPreenchimento" name="dataPreenchimento" class="form-control" required>
            </div>
            <div class="form-group">
              <label for="tempoInternacao" class="form-label">Tempo de Internação:</label>
              <input type="text" id="tempoInternacao" name="tempoInternacao" class="form-control" readonly placeholder="Calculado automaticamente">
            </div>
          </div>

          <div class="btn-group justify-end">
            <button type="button" class="btn btn-primary" id="nextToDispositivos">Próximo</button>
          </div>
        </div>
      </div>

      <!-- Dispositivos (Cateteres e Sondas) -->
      <div id="dispositivos" class="tab-content">
        <div class="card">
          <h2 class="text-xl font-semibold">Uso de Cateteres</h2>
          <div id="cateteresContainer">
            <!-- Entradas de cateteres serão adicionadas dinamicamente -->
          </div>
          <button type="button" id="addCateter" class="btn btn-primary">Adicionar Cateter</button>
        </div>

        <div class="card">
          <h2 class="text-xl font-semibold">Uso de Sondas</h2>
          <div id="sondasContainer">
            <!-- As sondas serão adicionadas dinamicamente -->
          </div>
          <button type="button" id="addSonda" class="btn btn-primary">Adicionar Sonda</button>
        </div>

        <div class="card">
          <h2 class="text-xl font-semibold">Uso de Drogas Vasoativas</h2>
          <div id="drogasContainer">
            <!-- Entradas de drogas serão adicionadas dinamicamente -->
          </div>
          <button type="button" id="addDroga" class="btn btn-primary">Adicionar Droga</button>
        </div>

        <div class="btn-group justify-between">
          <button type="button" class="btn btn-primary" id="backToIdentificacao">Anterior</button>
          <button type="button" class="btn btn-primary" id="nextToVentilacao">Próximo</button>
        </div>
      </div>

      <!-- Ventilação Mecânica -->
      <div id="ventilacao" class="tab-content">
        <div class="card">
          <h2 class="text-xl font-semibold">Ventilação Mecânica</h2>

          <div class="form-group">
            <label for="pacienteIntubado" class="form-label">Paciente Intubado?</label>
            <select id="pacienteIntubado" name="pacienteIntubado" class="form-control" required>
              <option value="" disabled selected>Selecione uma opção</option>
              <option value="Sim">Sim</option>
              <option value="Não">Não</option>
            </select>
          </div>

          <div id="intubacaoDetails" class="hidden">
            <div class="flex-container">
              <div class="form-group">
                <label for="dataIntubacao" class="form-label">Data de Intubação:</label>
                <input type="datetime-local" id="dataIntubacao" name="dataIntubacao" class="form-control">
              </div>
              <div class="form-group">
                <label for="tempoIntubacao" class="form-label">Tempo de Intubação:</label>
                <div class="status-container">
                  <input type="text" id="tempoIntubacao" name="tempoIntubacao" class="form-control" readonly placeholder="Será calculado automaticamente">
                  <span id="statusIntubacao" class="status-indicator"></span>
                </div>
              </div>
            </div>

            <div class="form-group">
              <label for="modoVentilacao" class="form-label">Modo de Ventilação:</label>
              <select id="modoVentilacao" name="modoVentilacao" class="form-control">
                <option value="" disabled selected>Selecione um modo</option>
                <option value="PCV">PCV</option>
                <option value="VCV">VCV</option>
                <option value="PSV">PSV</option>
                <option value="Outros">Outros</option>
              </select>
            </div>

            <div id="psvDetails" class="hidden">
              <div class="form-group">
                <label for="podeExtubar" class="form-label">Paciente Pode Extubar?</label>
                <select id="podeExtubar" name="podeExtubar" class="form-control">
                  <option value="" disabled selected>Selecione uma opção</option>
                  <option value="Sim">Sim</option>
                  <option value="Não">Não</option>
                </select>
              </div>
            </div>

            <div id="traqueostomiaContainer" class="hidden">
              <div class="alert alert-warning">
                <p>Paciente com mais de 5 dias de intubação. Considerar traqueostomia.</p>
              </div>
              <div class="checkbox-container">
                <input type="checkbox" id="realizouTraqueostomia" name="realizouTraqueostomia">
                <label for="realizouTraqueostomia">Realizou Traqueostomia?</label>
              </div>
              <div id="dataTraqueostomiaContainer" class="hidden">
                <div class="form-group">
                  <label for="dataTraqueostomia" class="form-label">Data da Traqueostomia:</label>
                  <input type="datetime-local" id="dataTraqueostomia" name="dataTraqueostomia" class="form-control">
                </div>
              </div>
            </div>
          </div>
        </div>

        <div class="btn-group justify-between">
          <button type="button" class="btn btn-primary" id="backToDispositivos">Anterior</button>
          <button type="button" class="btn btn-primary" id="nextToMedicacoes">Próximo</button>
        </div>
      </div>

      <!-- Medicações -->
      <div id="medicacoes" class="tab-content">
        <div class="card">
          <h2 class="text-xl font-semibold">Sedação</h2>
          <div id="sedacaoContainer">
            <!-- Entradas de sedação serão adicionadas dinamicamente -->
          </div>
          <button type="button" id="addSedacao" class="btn btn-primary">Adicionar Sedação</button>
        </div>

        <div class="card">
          <h2 class="text-xl font-semibold">Analgesia</h2>
          <div id="analgesiaContainer">
            <!-- Entradas de analgesia serão adicionadas dinamicamente -->
          </div>
          <button type="button" id="addAnalgesia" class="btn btn-primary">Adicionar Analgesia</button>
        </div>

        <div class="card">
          <h2 class="text-xl font-semibold">Uso de Antibióticos</h2>
          <div id="antibioticosContainer">
            <!-- Entradas de antibióticos serão adicionadas dinamicamente -->
          </div>
          <button type="button" id="addAntibiotico" class="btn btn-primary">Adicionar Antibiótico</button>
        </div>

        <div class="btn-group justify-between">
          <button type="button" class="btn btn-primary" id="backToVentilacao">Anterior</button>
          <button type="button" class="btn btn-primary" id="nextToOutros">Próximo</button>
        </div>
      </div>

      <!-- Outros Parâmetros -->
      <div id="outros" class="tab-content">
        <div class="card">
          <h2 class="text-xl font-semibold">Alimentação</h2>
          <div class="form-group">
            <label for="viaAlimentacao" class="form-label">Via de Alimentação:</label>
            <select id="viaAlimentacao" name="viaAlimentacao" class="form-control" required>
              <option value="" disabled selected>Selecione uma opção</option>
              <option value="VO">VO</option>
              <option value="SNG">SNG</option>
              <option value="SNE">SNE</option>
              <option value="Gastrostomia">Gastrostomia</option>
              <option value="Jejunostomia">Jejunostomia</option>
              <option value="Jejum">Jejum</option>
            </select>
          </div>

          <div id="quantidadeContainer" class="hidden">
            <div class="form-group">
              <label for="quantidadeDiaria" class="form-label">Quantidade Diária (ml):</label>
              <input type="number" id="quantidadeDiaria" name="quantidadeDiaria" class="form-control" placeholder="Informe a quantidade diária">
            </div>
          </div>
        </div>

        <div class="card">
          <h2 class="text-xl font-semibold">Trânsito Intestinal</h2>
          <div class="form-group">
            <label for="transitoIntestinal" class="form-label">Trânsito Intestinal:</label>
            <select id="transitoIntestinal" name="transitoIntestinal" class="form-control" required>
              <option value="" disabled selected>Selecione uma opção</option>
              <option value="Normal">Normal</option>
              <option value="Constipado">Constipado</option>
              <option value="Diarreia">Diarreia</option>
            </select>
          </div>

          <div class="flex-container">
            <div class="form-group">
              <label for="dataUltimaEvacuacao" class="form-label">Data da Última Evacuação:</label>
              <input type="datetime-local" id="dataUltimaEvacuacao" name="dataUltimaEvacuacao" class="form-control">
            </div>
            <div class="form-group">
              <label for="tempoDesdeEvacuacao" class="form-label">Tempo desde Última Evacuação:</label>
              <input type="text" id="tempoDesdeEvacuacao" name="tempoDesdeEvacuacao" class="form-control" readonly placeholder="Será calculado automaticamente">
            </div>
          </div>
        </div>

        <div class="flex-container">
          <div class="card">
            <h2 class="text-xl font-semibold">Trombofilaxia</h2>
            <div class="form-group">
              <label for="usoTrombofilaxia" class="form-label">Uso de Trombofilaxia:</label>
              <select id="usoTrombofilaxia" name="usoTrombofilaxia" class="form-control" required>
                <option value="" disabled selected>Selecione uma opção</option>
                <option value="Sim">Sim</option>
                <option value="Não">Não</option>
              </select>
            </div>

            <div id="trombofilaxiaDetails" class="hidden">
              <div class="form-group">
                <label for="tipoTrombofilaxia" class="form-label">Tipo de Trombofilaxia:</label>
                <select id="tipoTrombofilaxia" name="tipoTrombofilaxia" class="form-control">
                  <option value="" disabled selected>Selecione um tipo</option>
                  <option value="Heparina">Heparina</option>
                  <option value="Enoxaparina">Enoxaparina</option>
                  <option value="Outros">Outros</option>
                </select>
              </div>
            </div>
          </div>

          <div class="card">
            <h2 class="text-xl font-semibold">Proteção Gástrica</h2>
            <div class="form-group">
              <label for="usoProtecaoGastrica" class="form-label">Uso de Proteção Gástrica:</label>
              <select id="usoProtecaoGastrica" name="usoProtecaoGastrica" class="form-control" required>
                <option value="" disabled selected>Selecione uma opção</option>
                <option value="Sim">Sim</option>
                <option value="Não">Não</option>
              </select>
            </div>

            <div id="protecaoGastricaDetails" class="hidden">
              <div class="form-group">
                <label for="tipoProtecaoGastrica" class="form-label">Tipo de Proteção Gástrica:</label>
                <select id="tipoProtecaoGastrica" name="tipoProtecaoGastrica" class="form-control">
                  <option value="" disabled selected>Selecione uma opção</option>
                  <option value="Omeprazol">Omeprazol</option>
                  <option value="Pantoprazol">Pantoprazol</option>
                  <option value="Ranitidina">Ranitidina</option>
                  <option value="Outros">Outros</option>
                </select>
              </div>
            </div>
          </div>
        </div>

        <div class="flex-container">
          <div class="card">
            <h2 class="text-xl font-semibold">Controle Glicêmico</h2>
            <div class="form-group">
              <label for="glicemiaAtual" class="form-label">Glicemia Atual (mg/dL):</label>
              <input type="number" id="glicemiaAtual" name="glicemiaAtual" class="form-control" placeholder="Informe a glicemia atual">
            </div>

            <div class="form-group">
              <label for="controleGlicemico" class="form-label">Controle Glicêmico:</label>
              <select id="controleGlicemico" name="controleGlicemico" class="form-control" required>
                <option value="" disabled selected>Selecione uma opção</option>
                <option value="Insulina NPH">Insulina NPH</option>
                <option value="Insulina Regular">Insulina Regular</option>
                <option value="Nenhum">Nenhum</option>
              </select>
            </div>
          </div>

          <div class="card">
            <h2 class="text-xl font-semibold">Cabeceira e Conforto</h2>
            <div class="form-group">
              <label for="elevacaoCabeceira" class="form-label">Elevação da Cabeceira:</label>
              <select id="elevacaoCabeceira" name="elevacaoCabeceira" class="form-control" required>
                <option value="" disabled selected>Selecione uma opção</option>
                <option value="0 graus">0 graus</option>
                <option value="30 graus">30 graus</option>
                <option value="45 graus">45 graus</option>
                <option value="Acima de 45 graus">Acima de 45 graus</option>
              </select>
            </div>

            <div class="form-group">
              <label for="nivelConforto" class="form-label">Nível de Conforto do Paciente:</label>
              <select id="nivelConforto" name="nivelConforto" class="form-control" required>
                <option value="" disabled selected>Selecione uma opção</option>
                <option value="Confortável">Confortável</option>
                <option value="Moderadamente desconfortável">Moderadamente desconfortável</option>
                <option value="Muito desconfortável">Muito desconfortável</option>
              </select>
            </div>
          </div>
        </div>

        <div class="card">
          <h2 class="text-xl font-semibold">Pendências / Condutas</h2>
          <div class="form-group">
            <label for="pendenciasCondutas" class="form-label">Observações:</label>
            <textarea id="pendenciasCondutas" name="pendenciasCondutas" class="form-control" rows="5" placeholder="Insira aqui as pendências ou condutas do paciente"></textarea>
          </div>
        </div>

        <div class="btn-group justify-between">
          <button type="button" class="btn btn-primary" id="backToMedicacoes">Anterior</button>
          <button type="button" class="btn btn-primary" id="nextToResumo">Gerar Resumo</button>
        </div>
      </div>

      <!-- Resumo -->
      <div id="resumo" class="tab-content">
        <div class="card">
          <h2 class="text-xl font-semibold">Resumo da Avaliação</h2>
          <div id="resumoContent" class="mt-4">
            <!-- O conteúdo do resumo será gerado dinamicamente -->
            <div id="loadingResumo" class="spinner"></div>
          </div>
        </div>

        <div class="btn-group justify-between">
          <button type="button" class="btn btn-primary" id="backToOutros">Voltar</button>
          <button type="button" class="btn btn-primary" id="saveData">Salvar Dados</button>
          <button type="button" class="btn btn-primary" id="exportarCSV">Exportar para CSV</button>
          <button type="button" class="btn btn-primary" id="exportarPDF">Exportar em PDF</button>
          <button type="button" class="btn btn-danger" id="clearForm">Limpar Formulário</button>
        </div>
      </div>
    </form>
  </div>

  <div id="toast" class="toast">Mensagem de notificação</div>

  <script src="https://cdn.jsdelivr.net/npm/flowbite@1.6.5/dist/flowbite.min.js"></script>
  <script>
    document.addEventListener('DOMContentLoaded', function() {
      // Estado do formulário
      let formState = {
        lastSaved: null,
        patientData: {}
      };

      // Elementos DOM para as abas
      const tabs = document.querySelectorAll('.tab');
      const tabContents = document.querySelectorAll('.tab-content');

      // Função para mostrar uma aba específica
      function showTab(tabId) {
        tabContents.forEach(content => {
          content.classList.remove('active');
        });
        
        tabs.forEach(tab => {
          tab.classList.remove('active');
        });
        
        document.getElementById(tabId).classList.add('active');
        document.querySelector(`.tab[data-tab="${tabId}"]`).classList.add('active');
        
        // Scroll para o topo quando trocar de aba
        window.scrollTo(0, 0);
      }

      // Configurar navegação entre abas
      tabs.forEach(tab => {
        tab.addEventListener('click', () => {
          const tabId = tab.getAttribute('data-tab');
          showTab(tabId);
        });
      });

      // Botões de navegação entre abas
      document.getElementById('nextToDispositivos').addEventListener('click', () => showTab('dispositivos'));
      document.getElementById('backToIdentificacao').addEventListener('click', () => showTab('identificacao'));
      document.getElementById('nextToVentilacao').addEventListener('click', () => showTab('ventilacao'));
      document.getElementById('backToDispositivos').addEventListener('click', () => showTab('dispositivos'));
      document.getElementById('nextToMedicacoes').addEventListener('click', () => showTab('medicacoes'));
      document.getElementById('backToVentilacao').addEventListener('click', () => showTab('ventilacao'));
      document.getElementById('nextToOutros').addEventListener('click', () => showTab('outros'));
      document.getElementById('backToMedicacoes').addEventListener('click', () => showTab('medicacoes'));
      document.getElementById('nextToResumo').addEventListener('click', () => {
        showTab('resumo');
        generateSummary();
      });
      document.getElementById('backToOutros').addEventListener('click', () => showTab('outros'));

      // Elementos DOM para os campos do formulário
      const elements = {
        // Identificação do Paciente
        nomePaciente: document.getElementById('nomePaciente'),
        registroHospitalar: document.getElementById('registroHospitalar'),
        leito: document.getElementById('leito'),
        dataInternacao: document.getElementById('dataInternacao'),
        dataPreenchimento: document.getElementById('dataPreenchimento'),
        tempoInternacao: document.getElementById('tempoInternacao'),

        // Ventilação Mecânica
        pacienteIntubado: document.getElementById('pacienteIntubado'),
        intubacaoDetails: document.getElementById('intubacaoDetails'),
        dataIntubacao: document.getElementById('dataIntubacao'),
        tempoIntubacao: document.getElementById('tempoIntubacao'),
        statusIntubacao: document.getElementById('statusIntubacao'),
        modoVentilacao: document.getElementById('modoVentilacao'),
        psvDetails: document.getElementById('psvDetails'),
        traqueostomiaContainer: document.getElementById('traqueostomiaContainer'),
        realizouTraqueostomia: document.getElementById('realizouTraqueostomia'),
        dataTraqueostomiaContainer: document.getElementById('dataTraqueostomiaContainer'),
        dataTraqueostomia: document.getElementById('dataTraqueostomia'),

        // Alimentação
        viaAlimentacao: document.getElementById('viaAlimentacao'),
        quantidadeContainer: document.getElementById('quantidadeContainer'),
        quantidadeDiaria: document.getElementById('quantidadeDiaria'),

        // Trânsito Intestinal
        transitoIntestinal: document.getElementById('transitoIntestinal'),
        dataUltimaEvacuacao: document.getElementById('dataUltimaEvacuacao'),
        tempoDesdeEvacuacao: document.getElementById('tempoDesdeEvacuacao'),

        // Containers
        cateteresContainer: document.getElementById('cateteresContainer'),
        sondasContainer: document.getElementById('sondasContainer'),
        drogasContainer: document.getElementById('drogasContainer'),
        sedacaoContainer: document.getElementById('sedacaoContainer'),
        analgesiaContainer: document.getElementById('analgesiaContainer'),
        antibioticosContainer: document.getElementById('antibioticosContainer'),

        // Proteção Gástrica e Trombofilaxia
        usoProtecaoGastrica: document.getElementById('usoProtecaoGastrica'),
        tipoProtecaoGastrica: document.getElementById('tipoProtecaoGastrica'),
        protecaoGastricaDetails: document.getElementById('protecaoGastricaDetails'),
        usoTrombofilaxia: document.getElementById('usoTrombofilaxia'),
        tipoTrombofilaxia: document.getElementById('tipoTrombofilaxia'),
        trombofilaxiaDetails: document.getElementById('trombofilaxiaDetails'),

        // Controle Glicêmico
        glicemiaAtual: document.getElementById('glicemiaAtual'),
        controleGlicemico: document.getElementById('controleGlicemico'),

        // Cabeceira e Conforto
        elevacaoCabeceira: document.getElementById('elevacaoCabeceira'),
        nivelConforto: document.getElementById('nivelConforto'),
        
        // Pendências/Condutas
        pendenciasCondutas: document.getElementById('pendenciasCondutas'),
        
        // Botões
        saveData: document.getElementById('saveData'),
        exportarCSV: document.getElementById('exportarCSV'),
        exportarPDF: document.getElementById('exportarPDF'),
        clearForm: document.getElementById('clearForm')
      };

      // Configurações iniciais
      const hoje = new Date();
      elements.dataPreenchimento.valueAsDate = hoje;
      
      // Função para mostrar toast de notificação
      function showToast(message, duration = 3000) {
        const toast = document.getElementById('toast');
        toast.textContent = message;
        toast.classList.add('show');
        
        setTimeout(() => {
          toast.classList.remove('show');
        }, duration);
      }

      // Funções de cálculo
      function calculateDays(startDate, endDate) {
        const start = new Date(startDate);
        const end = new Date(endDate);
        const diffTime = Math.abs(end - start);
        return Math.ceil(diffTime / (1000 * 60 * 60 * 24));
      }

      // Função para atualizar todas as datas máximas
      function atualizarDataMaxima() {
        const agora = new Date();
        const dataFormatada = agora.toISOString().slice(0, 16);
        
        if (elements.dataIntubacao) {
          elements.dataIntubacao.max = dataFormatada;
        }
        
        if (elements.dataTraqueostomia) {
          elements.dataTraqueostomia.max = dataFormatada;
        }
        
        if (elements.dataUltimaEvacuacao) {
          elements.dataUltimaEvacuacao.max = dataFormatada;
        }
      }

      // Funções de Ventilação Mecânica
      function limparCamposIntubacao() {
        elements.tempoIntubacao.value = '';
        elements.statusIntubacao.className = 'status-indicator';
        elements.traqueostomiaContainer.classList.add('hidden');
        if (elements.realizouTraqueostomia) {
          elements.realizouTraqueostomia.checked = false;
        }
        if (elements.dataTraqueostomia) {
          elements.dataTraqueostomia.value = '';
        }
      }

      function calcularTempoIntubacao() {
        if (!elements.dataIntubacao || !elements.dataIntubacao.value) {
          limparCamposIntubacao();
          return;
        }
        
        const dataInicio = new Date(elements.dataIntubacao.value);
        const agora = new Date();
        
        if (isNaN(dataInicio.getTime())) {
          limparCamposIntubacao();
          return;
        }

        if (dataInicio > agora) {
          showToast('A data de intubação não pode ser no futuro', 5000);
          elements.dataIntubacao.value = '';
          limparCamposIntubacao();
          return;
        }

        const diffMs = agora - dataInicio;
        const diffDias = Math.floor(diffMs / (1000 * 60 * 60 * 24));
        const diffHoras = Math.floor((diffMs % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));

        elements.tempoIntubacao.value = `${diffDias} dia(s) e ${diffHoras} hora(s)`;

        // Atualizar status visual
        elements.tempoIntubacao.style.color = '';
        elements.statusIntubacao.className = 'status-indicator';

        if (diffDias >= 11) {
          elements.tempoIntubacao.style.color = 'var(--danger-color)';
          elements.statusIntubacao.classList.add('status-danger');
        } else if (diffDias >= 6) {
          elements.tempoIntubacao.style.color = 'var(--warning-color)';
          elements.statusIntubacao.classList.add('status-warning');
        } else {
          elements.statusIntubacao.classList.add('status-ok');
        }

        // Verificar necessidade de traqueostomia
        if (diffDias > 5) {
          elements.traqueostomiaContainer.classList.remove('hidden');
        } else {
          elements.traqueostomiaContainer.classList.add('hidden');
          if (elements.realizouTraqueostomia) {
            elements.realizouTraqueostomia.checked = false;
          }
          if (elements.dataTraqueostomia) {
            elements.dataTraqueostomia.value = '';
          }
        }
      }
      
      // Função para cálculo do tempo desde última evacuação
      function calcularTempoDesdeEvacuacao() {
        if (!elements.dataUltimaEvacuacao || !elements.dataUltimaEvacuacao.value) {
          elements.tempoDesdeEvacuacao.value = '';
          return;
        }
        
        const dataEvacuacao = new Date(elements.dataUltimaEvacuacao.value);
        const agora = new Date();
        
        if (isNaN(dataEvacuacao.getTime())) {
          elements.tempoDesdeEvacuacao.value = '';
          return;
        }

        if (dataEvacuacao > agora) {
          showToast('A data da última evacuação não pode ser no futuro', 5000);
          elements.dataUltimaEvacuacao.value = '';
          return;
        }

        const diffMs = agora - dataEvacuacao;
        const diffHoras = Math.floor(diffMs / (1000 * 60 * 60));
        const diffDias = Math.floor(diffHoras / 24);
        const horasRestantes = diffHoras % 24;

        elements.tempoDesdeEvacuacao.value = `${diffDias} dia(s) e ${horasRestantes} hora(s)`;

        // Atualizar estilo baseado no tempo
        if (diffHoras >= 72) {
          elements.tempoDesdeEvacuacao.style.color = 'var(--danger-color)';
          elements.tempoDesdeEvacuacao.style.fontWeight = 'bold';
        } else if (diffHoras >= 48) {
          elements.tempoDesdeEvacuacao.style.color = 'var(--warning-color)';
          elements.tempoDesdeEvacuacao.style.fontWeight = 'bold';
        } else {
          elements.tempoDesdeEvacuacao.style.color = 'var(--success-color)';
          elements.tempoDesdeEvacuacao.style.fontWeight = 'normal';
        }
      }

      // Função para validação do formulário
      function validateForm() {
        let isValid = true;
        const requiredFields = document.querySelectorAll('[required]');
        
        requiredFields.forEach(field => {
          if (!field.value) {
            field.classList.add('invalid');
            isValid = false;
            
            if (!field.nextElementSibling?.classList.contains('validation-message')) {
              const message = document.createElement('div');
              message.className = 'validation-message';
              message.textContent = 'Este campo é obrigatório';
              field.parentNode.insertBefore(message, field.nextSibling);
            }
          } else {
            field.classList.remove('invalid');
            const message = field.nextElementSibling;
            if (message?.classList.contains('validation-message')) {
              message.remove();
            }
          }
        });

        return isValid;
      }

      // Funções para criar elementos dinâmicos
      function createCateterEntry() {
        const entry = document.createElement('div');
        entry.classList.add('medication-entry');
        entry.innerHTML = `
          <div class="flex-container">
            <div class="form-group">
              <label for="tipoCateter" class="form-label">Tipo de Cateter:</label>
              <select name="tipoCateter[]" class="form-control tipo-cateter" required>
                <option value="" disabled selected>Selecione uma opção</option>
                <option value="Cateter Central">Cateter Central</option>
                <option value="Cateter Periférico">Cateter Periférico</option>
                <option value="Outro">Outro</option>
              </select>
            </div>
            <div class="form-group">
              <label for="localizacaoCateter" class="form-label">Localização:</label>
              <select name="localizacaoCateter[]" class="form-control localizacao-cateter">
                <option value="" disabled selected>Selecione a localização</option>
                <option value="VJD">VJD</option>
                <option value="VJE">VJE</option>
                <option value="VSCD">VSCD</option>
                <option value="VSCE">VSCE</option>
                <option value="FD">FD</option>
                <option value="FE">FE</option>
                <option value="MSD">MSD</option>
                <option value="MSE">MSE</option>
                <option value="MID">MID</option>
                <option value="MIE">MIE</option>
                <option value="Outros">Outros</option>
              </select>
            </div>
          </div>
          <div class="flex-container">
            <div class="form-group">
              <label for="dataInsercaoCateter" class="form-label">Data de Inserção:</label>
              <input type="date" name="dataInsercaoCateter[]" class="form-control data-insercao-cateter">
            </div>
            <div class="form-group">
              <label for="tempoUsoCateter" class="form-label">Tempo de Uso:</label>
              <input type="text" name="tempoUsoCateter[]" class="form-control tempo-uso-cateter" readonly placeholder="Será calculado automaticamente">
            </div>
          </div>
          <button type="button" class="btn btn-danger remove-btn">Remover</button>
        `;

        const dataInsercaoInput = entry.querySelector('.data-insercao-cateter');
        const tempoUsoInput = entry.querySelector('.tempo-uso-cateter');
        
        // Adicionar evento para calcular tempo de uso quando a data mudar
        dataInsercaoInput.addEventListener('change', () => {
          calcularTempoUso(dataInsercaoInput, tempoUsoInput);
        });
        
        // Adicionar evento para remover a entrada quando o botão de remover for clicado
        entry.querySelector('.remove-btn').addEventListener('click', () => entry.remove());
        
        return entry;
      }

      function createSondaEntry() {
        const entry = document.createElement('div');
        entry.classList.add('medication-entry');
        entry.innerHTML = `
          <div class="flex-container">
            <div class="form-group">
              <label for="tipoSonda" class="form-label">Tipo de Sonda:</label>
              <select name="tipoSonda[]" class="form-control" required>
                <option value="" disabled selected>Selecione uma opção</option>
                <option value="SVD">SVD</option>
                <option value="SR">SR</option>
                <option value="Dreno de Tórax">Dreno de Tórax</option>
                <option value="Drenos Abdominais">Drenos Abdominais</option>
                <option value="Outros Drenos">Outros Drenos</option>
              </select>
            </div>
            <div class="form-group">
              <label for="valorDrenado" class="form-label">Valor Drenado (ml):</label>
              <input type="number" name="valorDrenado[]" class="form-control" placeholder="Insira o valor drenado">
            </div>
          </div>
          <button type="button" class="btn btn-danger remove-btn">Remover</button>
        `;
        
        // Adicionar evento para remover a entrada quando o botão de remover for clicado
        entry.querySelector('.remove-btn').addEventListener('click', () => entry.remove());
        
        return entry;
      }

      function createDrogaEntry() {
        const entry = document.createElement('div');
        entry.classList.add('medication-entry');
        entry.innerHTML = `
          <div class="flex-container">
            <div class="form-group">
              <label for="drogaVasoativa" class="form-label">Droga Vasoativa:</label>
              <select name="drogaVasoativa[]" class="form-control" required>
                <option value="" disabled selected>Selecione uma droga</option>
                <option value="Noradrenalina">Noradrenalina</option>
                <option value="Vasopressina">Vasopressina</option>
                <option value="Dobutamina">Dobutamina</option>
                <option value="Adrenalina">Adrenalina</option>
                <option value="Nitroprussiato">Nitroprussiato</option>
                <option value="Nitroglicerina">Nitroglicerina</option>
                <option value="Amiodarona">Amiodarona</option>
                <option value="Nenhuma">Nenhuma</option>
              </select>
            </div>
            <div class="form-group">
              <label for="vazaoDroga" class="form-label">Vazão (ml/h):</label>
              <input type="number" name="vazaoDroga[]" class="form-control" placeholder="Informe a vazão">
            </div>
          </div>
          <button type="button" class="btn btn-danger remove-btn">Remover</button>
        `;
        
        // Adicionar evento para remover a entrada quando o botão de remover for clicado
        entry.querySelector('.remove-btn').addEventListener('click', () => entry.remove());
        
        return entry;
      }

      function createMedicationEntry(type) {
        const entry = document.createElement('div');
        entry.classList.add('medication-entry');
        
        const selectOptions = type === 'sedacao' 
          ? `<option value="Midazolan">Midazolan</option>
              <option value="Propofol">Propofol</option>
              <option value="Cetamina">Cetamina</option>
              <option value="Dexmedetomidina">Dexmedetomidina</option>`
          : `<option value="Dipirona">Dipirona</option>
              <option value="Morfina">Morfina</option>
              <option value="Fentanil">Fentanil</option>
              <option value="Metadona">Metadona</option>`;

        entry.innerHTML = `
          <div class="flex-container">
            <div class="form-group">
              <label for="medicacao${type}" class="form-label">Medicação:</label>
              <select class="form-control medicacao-dropdown" name="medicacao${type}[]" required>
                <option value="" disabled selected>Selecione uma opção</option>
                ${selectOptions}
                <option value="Outros">Outros</option>
              </select>
            </div>
            <div class="form-group">
              <label for="dose${type}" class="form-label">Dose em uso (${type === 'sedacao' ? 'mg/h' : 'mg'}):</label>
              <input type="text" class="form-control dose-input" name="dose${type}[]" placeholder="Informe a dose">
            </div>
          </div>
          <button type="button" class="btn btn-danger remove-btn">Remover</button>
        `;

        entry.querySelector('.remove-btn').addEventListener('click', () => entry.remove());
        return entry;
      }

      function createAntibioticoEntry() {
        const entry = document.createElement('div');
        entry.classList.add('medication-entry');
        entry.innerHTML = `
          <div class="form-group">
            <label for="antibiotico" class="form-label">Antibiótico:</label>
            <select class="form-control antibiotico-dropdown" name="antibiotico[]" required>
              <option value="" disabled selected>Selecione um antibiótico</option>
              <option value="Vancomicina">Vancomicina</option>
              <option value="Ceftriaxone">Ceftriaxone</option>
              <option value="Meropenem">Meropenem</option>
              <option value="Tazo-Pipe">Tazo</option>
              <option value="Poli B">Poli B</option>
              <option value="Metronidazol">Metro</option>
              <option value="Fluconazol">Fluco</option>
              <option value="Cefalotina">Cefalo</option>
              <option value="Outro">Outro</option>
            </select>
          </div>
          
          <div class="outro-antibiotico hidden">
            <div class="form-group">
              <label for="outroAntibiotico" class="form-label">Nome do Antibiótico:</label>
              <input type="text" class="form-control" name="outroAntibiotico[]" placeholder="Digite o nome do antibiótico">
            </div>
          </div>

          <div class="flex-container">
            <div class="form-group">
              <label for="dataInicioAntibiotico" class="form-label">Data de Início:</label>
              <input type="date" class="form-control data-inicio-antibiotico" name="dataInicioAntibiotico[]" required>
            </div>
            <div class="form-group">
              <label for="tempoUsoAntibiotico" class="form-label">Tempo de Uso (dias):</label>
              <input type="text" class="form-control tempo-uso-antibiotico" name="tempoUsoAntibiotico[]" readonly placeholder="Calculado automaticamente">
            </div>
          </div>

          <button type="button" class="btn btn-danger remove-btn">Remover</button>
        `;

        const antibioticoDropdown = entry.querySelector('.antibiotico-dropdown');
        const outroAntibioticoContainer = entry.querySelector('.outro-antibiotico');
        
        antibioticoDropdown.addEventListener('change', function() {
          outroAntibioticoContainer.classList.toggle('hidden', this.value !== 'Outro');
        });

        entry.querySelector('.remove-btn').addEventListener('click', () => entry.remove());
        
        const dataInicioInput = entry.querySelector('.data-inicio-antibiotico');
        const tempoUsoInput = entry.querySelector('.tempo-uso-antibiotico');
        
        dataInicioInput.addEventListener('change', () => {
          calcularTempoUsoAntibiotico(dataInicioInput, tempoUsoInput);
        });

        return entry;
      }

      // Função para cálculo do tempo de uso
      function calcularTempoUso(dataInsercaoInput, tempoUsoInput) {
        const dataInsercao = new Date(dataInsercaoInput.value);
        const hoje = new Date();
        
        if (!dataInsercaoInput.value) {
          tempoUsoInput.value = '';
          return;
        }
        
        if (dataInsercao > hoje) {
          showToast('A data de inserção não pode ser no futuro', 5000);
          dataInsercaoInput.value = '';
          tempoUsoInput.value = '';
          return;
        }

        const diffMs = hoje - dataInsercao;
        const diffDias = Math.floor(diffMs / (1000 * 60 * 60 * 24));
        tempoUsoInput.value = `${diffDias} dia(s)`;
        
        // Aplicar destaque para cateter com uso prolongado
        if (diffDias > 7) {
          tempoUsoInput.style.color = 'var(--warning-color)';
          tempoUsoInput.style.fontWeight = 'bold';
        } else {
          tempoUsoInput.style.color = '';
          tempoUsoInput.style.fontWeight = 'normal';
        }
      }

      // Função para cálculo do tempo de uso de antibióticos
      function calcularTempoUsoAntibiotico(dataInicioInput, tempoUsoInput) {
        const dataInicio = new Date(dataInicioInput.value);
        const hoje = new Date();
        
        if (!dataInicioInput.value) {
          tempoUsoInput.value = '';
          return;
        }
        
        if (dataInicio > hoje) {
          showToast('A data de início não pode ser no futuro', 5000);
          dataInicioInput.value = '';
          tempoUsoInput.value = '';
          return;
        }

        const diffMs = hoje - dataInicio;
        const diffDias = Math.floor(diffMs / (1000 * 60 * 60 * 24));
        tempoUsoInput.value = `${diffDias} dia(s)`;
        
        // Aplicar destaque para antibióticos com uso prolongado
        if (diffDias > 10) {
          tempoUsoInput.style.color = 'var(--danger-color)';
          tempoUsoInput.style.fontWeight = 'bold';
        } else if (diffDias > 7) {
          tempoUsoInput.style.color = 'var(--warning-color)';
          tempoUsoInput.style.fontWeight = 'bold';
        } else {
          tempoUsoInput.style.color = '';
          tempoUsoInput.style.fontWeight = 'normal';
        }
      }

      // Função para gerar resumo
      function generateSummary() {
        const resumoContent = document.getElementById('resumoContent');
        const loadingResumo = document.getElementById('loadingResumo');
        
        // Mostrar loading e limpar conteúdo anterior
        loadingResumo.style.display = 'block';
        resumoContent.innerHTML = '<div id="loadingResumo" class="spinner"></div>';
        
        // Simular carregamento para experiência do usuário
        setTimeout(() => {
          const formData = new FormData(document.getElementById('roundMatinalForm'));
          const data = {};
          
          for (const [key, value] of formData.entries()) {
            if (key.endsWith('[]')) {
              const baseKey = key.slice(0, -2);
              if (!data[baseKey]) {
                data[baseKey] = [];
              }
              data[baseKey].push(value);
            } else {
              data[key] = value;
            }
          }
          
          // Criar conteúdo HTML do resumo
          let html = `
            <div class="card">
              <h3 class="text-lg font-semibold">Identificação do Paciente</h3>
              <div class="table-container">
                <table>
                  <tr>
                    <th>Nome</th>
                    <td>${data.nomePaciente || 'Não informado'}</td>
                  </tr>
                  <tr>
                    <th>Registro</th>
                    <td>${data.registroHospitalar || 'Não informado'}</td>
                  </tr>
                  <tr>
                    <th>Leito</th>
                    <td>${data.leito || 'Não informado'}</td>
                  </tr>
                  <tr>
                    <th>Internação</th>
                    <td>${formatarData(data.dataInternacao)} (${data.tempoInternacao || 'Não calculado'})</td>
                  </tr>
                </table>
              </div>
            </div>
          `;
          
          // Ventilação Mecânica
          html += `
            <div class="card mt-4">
              <h3 class="text-lg font-semibold">Status Ventilatório</h3>
              <div class="table-container">
                <table>
                  <tr>
                    <th>Intubado</th>
                    <td>${data.pacienteIntubado || 'Não informado'}</td>
                  </tr>
          `;
          
          if (data.pacienteIntubado === 'Sim') {
            html += `
                  <tr>
                    <th>Tempo de Intubação</th>
                    <td>${data.tempoIntubacao || 'Não calculado'}</td>
                  </tr>
                  <tr>
                    <th>Modo Ventilação</th>
                    <td>${data.modoVentilacao || 'Não informado'}</td>
                  </tr>
            `;
            
            if (data.modoVentilacao === 'PSV' && data.podeExtubar) {
              html += `
                  <tr>
                    <th>Pode Extubar</th>
                    <td>${data.podeExtubar}</td>
                  </tr>
              `;
            }
            
            if (data.realizouTraqueostomia) {
              html += `
                  <tr>
                    <th>Traqueostomia</th>
                    <td>Sim, em ${formatarData(data.dataTraqueostomia)}</td>
                  </tr>
              `;
            }
          }
          
          html += `
                </table>
              </div>
            </div>
          `;
          
          // Dispositivos
          html += `
            <div class="card mt-4">
              <h3 class="text-lg font-semibold">Dispositivos</h3>
          `;
          
          // Cateteres
          if (data.tipoCateter && data.tipoCateter.length > 0) {
            html += `
              <h4 class="text-md font-semibold mt-2">Cateteres</h4>
              <div class="table-container">
                <table>
                  <thead>
                    <tr>
                      <th>Tipo</th>
                      <th>Localização</th>
                      <th>Tempo de Uso</th>
                    </tr>
                  </thead>
                  <tbody>
            `;
            
            for (let i = 0; i < data.tipoCateter.length; i++) {
              html += `
                    <tr>
                      <td>${data.tipoCateter[i] || 'Não informado'}</td>
                      <td>${data.localizacaoCateter && data.localizacaoCateter[i] ? data.localizacaoCateter[i] : 'Não informado'}</td>
                      <td>${data.tempoUsoCateter && data.tempoUsoCateter[i] ? data.tempoUsoCateter[i] : 'Não calculado'}</td>
                    </tr>
              `;
            }
            
            html += `
                  </tbody>
                </table>
              </div>
            `;
          } else {
            html += `<p>Não há cateteres registrados.</p>`;
          }
          
          // Sondas
          if (data.tipoSonda && data.tipoSonda.length > 0) {
            html += `
              <h4 class="text-md font-semibold mt-4">Sondas e Drenos</h4>
              <div class="table-container">
                <table>
                  <thead>
                    <tr>
                      <th>Tipo</th>
                      <th>Valor Drenado (ml)</th>
                    </tr>
                  </thead>
                  <tbody>
            `;
            
            for (let i = 0; i < data.tipoSonda.length; i++) {
              html += `
                    <tr>
                      <td>${data.tipoSonda[i] || 'Não informado'}</td>
                      <td>${data.valorDrenado && data.valorDrenado[i] ? data.valorDrenado[i] : 'Não informado'}</td>
                    </tr>
              `;
            }
            
            html += `
                  </tbody>
                </table>
              </div>
            `;
          } else {
            html += `<p class="mt-4">Não há sondas ou drenos registrados.</p>`;
          }
          
          // Drogas Vasoativas
          if (data.drogaVasoativa && data.drogaVasoativa.length > 0) {
            html += `
              <h4 class="text-md font-semibold mt-4">Drogas Vasoativas</h4>
              <div class="table-container">
                <table>
                  <thead>
                    <tr>
                      <th>Droga</th>
                      <th>Vazão (ml/h)</th>
                    </tr>
                  </thead>
                  <tbody>
            `;
            
            for (let i = 0; i < data.drogaVasoativa.length; i++) {
              html += `
                    <tr>
                      <td>${data.drogaVasoativa[i] || 'Não informado'}</td>
                      <td>${data.vazaoDroga && data.vazaoDroga[i] ? data.vazaoDroga[i] : 'Não informado'}</td>
                    </tr>
              `;
            }
            
            html += `
                  </tbody>
                </table>
              </div>
            `;
          } else {
            html += `<p class="mt-4">Não há drogas vasoativas registradas.</p>`;
          }
          
          html += `</div>`;
          
          // Medicações
          html += `
            <div class="card mt-4">
              <h3 class="text-lg font-semibold">Medicações</h3>
          `;
          
          // Sedação
          if (data.medicacaosedacao && data.medicacaosedacao.length > 0) {
            html += `
              <h4 class="text-md font-semibold mt-2">Sedação</h4>
              <div class="table-container">
                <table>
                  <thead>
                    <tr>
                      <th>Medicação</th>
                      <th>Dose (mg/h)</th>
                    </tr>
                  </thead>
                  <tbody>
            `;
            
            for (let i = 0; i < data.medicacaosedacao.length; i++) {
              html += `
                    <tr>
                      <td>${data.medicacaosedacao[i] || 'Não informado'}</td>
                      <td>${data.dosesedacao && data.dosesedacao[i] ? data.dosesedacao[i] : 'Não informado'}</td>
                    </tr>
              `;
            }
            
            html += `
                  </tbody>
                </table>
              </div>
            `;
          } else {
            html += `<p>Não há medicações de sedação registradas.</p>`;
          }
          
          // Analgesia
          if (data.medicacaoanalgesia && data.medicacaoanalgesia.length > 0) {
            html += `
              <h4 class="text-md font-semibold mt-4">Analgesia</h4>
              <div class="table-container">
                <table>
                  <thead>
                    <tr>
                      <th>Medicação</th>
                      <th>Dose (mg)</th>
                    </tr>
                  </thead>
                  <tbody>
            `;
            
            for (let i = 0; i < data.medicacaoanalgesia.length; i++) {
              html += `
                    <tr>
                      <td>${data.medicacaoanalgesia[i] || 'Não informado'}</td>
                      <td>${data.doseanalgesia && data.doseanalgesia[i] ? data.doseanalgesia[i] : 'Não informado'}</td>
                    </tr>
              `;
            }
            
            html += `
                  </tbody>
                </table>
              </div>
            `;
          } else {
            html += `<p class="mt-4">Não há medicações de analgesia registradas.</p>`;
          }
          
          // Antibióticos
          if (data.antibiotico && data.antibiotico.length > 0) {
            html += `
              <h4 class="text-md font-semibold mt-4">Antibióticos</h4>
              <div class="table-container">
                <table>
                  <thead>
                    <tr>
                      <th>Antibiótico</th>
                      <th>Tempo de Uso</th>
                    </tr>
                  </thead>
                  <tbody>
            `;
            
            for (let i = 0; i < data.antibiotico.length; i++) {
              let antibioticoNome = data.antibiotico[i];
              if (antibioticoNome === 'Outro' && data.outroAntibiotico && data.outroAntibiotico[i]) {
                antibioticoNome = data.outroAntibiotico[i];
              }
              
              html += `
                    <tr>
                      <td>${antibioticoNome || 'Não informado'}</td>
                      <td>${data.tempoUsoAntibiotico && data.tempoUsoAntibiotico[i] ? data.tempoUsoAntibiotico[i] : 'Não calculado'}</td>
                    </tr>
              `;
            }
            
            html += `
                  </tbody>
                </table>
              </div>
            `;
          } else {
            html += `<p class="mt-4">Não há antibióticos registrados.</p>`;
          }
          
          html += `</div>`;
          
          // Outros Parâmetros
          html += `
            <div class="card mt-4">
              <h3 class="text-lg font-semibold">Outros Parâmetros</h3>
              <div class="flex-container">
                <div>
                  <h4 class="text-md font-semibold">Alimentação</h4>
                  <p><strong>Via:</strong> ${data.viaAlimentacao || 'Não informado'}</p>
                  ${data.quantidadeDiaria ? `<p><strong>Quantidade:</strong> ${data.quantidadeDiaria} ml/dia</p>` : ''}
                </div>
                <div>
                  <h4 class="text-md font-semibold">Trânsito Intestinal</h4>
                  <p><strong>Status:</strong> ${data.transitoIntestinal || 'Não informado'}</p>
                  <p><strong>Última Evacuação:</strong> ${data.tempoDesdeEvacuacao || 'Não calculado'}</p>
                </div>
              </div>
              
              <div class="flex-container mt-4">
                <div>
                  <h4 class="text-md font-semibold">Proteção Gástrica</h4>
                  <p><strong>Em uso:</strong> ${data.usoProtecaoGastrica || 'Não informado'}</p>
                  ${data.usoProtecaoGastrica === 'Sim' ? `<p><strong>Tipo:</strong> ${data.tipoProtecaoGastrica || 'Não informado'}</p>` : ''}
                </div>
                <div>
                  <h4 class="text-md font-semibold">Trombofilaxia</h4>
                  <p><strong>Em uso:</strong> ${data.usoTrombofilaxia || 'Não informado'}</p>
                  ${data.usoTrombofilaxia === 'Sim' ? `<p><strong>Tipo:</strong> ${data.tipoTrombofilaxia || 'Não informado'}</p>` : ''}
                </div>
              </div>
              
              <div class="flex-container mt-4">
                <div>
                  <h4 class="text-md font-semibold">Controle Glicêmico</h4>
                  <p><strong>Glicemia Atual:</strong> ${data.glicemiaAtual ? `${data.glicemiaAtual} mg/dL` : 'Não informado'}</p>
                  <p><strong>Controle:</strong> ${data.controleGlicemico || 'Não informado'}</p>
                </div>
                <div>
                  <h4 class="text-md font-semibold">Cabeceira e Conforto</h4>
                  <p><strong>Elevação da Cabeceira:</strong> ${data.elevacaoCabeceira || 'Não informado'}</p>
                  <p><strong>Nível de Conforto:</strong> ${data.nivelConforto || 'Não informado'}</p>
                </div>
              </div>
              
              ${data.pendenciasCondutas ? `
              <div class="mt-4">
                <h4 class="text-md font-semibold">Pendências / Condutas</h4>
                <p>${data.pendenciasCondutas.replace(/\n/g, '<br>')}</p>
              </div>
              ` : ''}
            </div>
          `;
          
          // Atualizar o conteúdo e esconder o loading
          loadingResumo.style.display = 'none';
          resumoContent.innerHTML = html;
        }, 500);
      }

      // Função para formatar datas
      function formatarData(dataString) {
        if (!dataString) return 'Não informado';
        
        const data = new Date(dataString);
        if (isNaN(data.getTime())) return 'Data inválida';
        
        return data.toLocaleDateString('pt-BR');
      }

      // Inicializar containers com uma entrada cada
      elements.cateteresContainer.appendChild(createCateterEntry());
      elements.sondasContainer.appendChild(createSondaEntry());
      elements.drogasContainer.appendChild(createDrogaEntry());
      elements.sedacaoContainer.appendChild(createMedicationEntry('sedacao'));
      elements.analgesiaContainer.appendChild(createMedicationEntry('analgesia'));
      elements.antibioticosContainer.appendChild(createAntibioticoEntry());

      // Event Listeners para adicionar elementos dinâmicos
      document.getElementById('addCateter').addEventListener('click', () => elements.cateteresContainer.appendChild(createCateterEntry()));
      document.getElementById('addSonda').addEventListener('click', () => elements.sondasContainer.appendChild(createSondaEntry()));
      document.getElementById('addDroga').addEventListener('click', () => elements.drogasContainer.appendChild(createDrogaEntry()));
      document.getElementById('addSedacao').addEventListener('click', () => elements.sedacaoContainer.appendChild(createMedicationEntry('sedacao')));
      document.getElementById('addAnalgesia').addEventListener('click', () => elements.analgesiaContainer.appendChild(createMedicationEntry('analgesia')));
      document.getElementById('addAntibiotico').addEventListener('click', () => elements.antibioticosContainer.appendChild(createAntibioticoEntry()));

      // Event Listeners para verificações condicionais
      elements.dataInternacao.addEventListener('change', function() {
        const dataInternacao = new Date(this.value);
        const dataPreenchimento = new Date(elements.dataPreenchimento.value);
        
        if (this.value && elements.dataPreenchimento.value) {
          const diffDias = calculateDays(dataInternacao, dataPreenchimento);
          elements.tempoInternacao.value = `${diffDias} dia(s)`;
        }
      });

      elements.dataPreenchimento.addEventListener('change', function() {
        const dataInternacao = new Date(elements.dataInternacao.value);
        const dataPreenchimento = new Date(this.value);
        
        if (elements.dataInternacao.value && this.value) {
          const diffDias = calculateDays(dataInternacao, dataPreenchimento);
          elements.tempoInternacao.value = `${diffDias} dia(s)`;
        }
      });

      elements.viaAlimentacao.addEventListener('change', () => {
        elements.quantidadeContainer.classList.toggle('hidden', 
          !['SNG', 'SNE', 'Gastrostomia', 'Jejunostomia'].includes(elements.viaAlimentacao.value));
      });

      elements.pacienteIntubado.addEventListener('change', function() {
        elements.intubacaoDetails.classList.toggle('hidden', this.value !== 'Sim');
        if (this.value !== 'Sim') {
          elements.dataIntubacao.value = '';
          limparCamposIntubacao();
          elements.modoVentilacao.value = '';
          elements.psvDetails.classList.add('hidden');
        }
      });

      elements.modoVentilacao.addEventListener('change', function() {
        elements.psvDetails.classList.toggle('hidden', this.value !== 'PSV');
      });

      elements.dataIntubacao.addEventListener('change', calcularTempoIntubacao);

      elements.realizouTraqueostomia.addEventListener('change', function() {
        elements.dataTraqueostomiaContainer.classList.toggle('hidden', !this.checked);
        if (!this.checked) {
          elements.dataTraqueostomia.value = '';
        }
      });

      elements.dataTraqueostomia.addEventListener('change', function() {
        if (!this.value) return;
        
        const dataTraq = new Date(this.value);
        const dataInt = new Date(elements.dataIntubacao.value);
        const agora = new Date();
        
        if (dataTraq > agora) {
          showToast('A data da traqueostomia não pode ser no futuro', 5000);
          this.value = '';
          return;
        }
        
        if (dataInt && dataTraq < dataInt) {
          showToast('A data da traqueostomia não pode ser anterior à data de intubação', 5000);
          this.value = '';
        }
      });

      elements.dataUltimaEvacuacao.addEventListener('change', calcularTempoDesdeEvacuacao);

      elements.usoProtecaoGastrica.addEventListener('change', function() {
        elements.protecaoGastricaDetails.classList.toggle('hidden', this.value !== 'Sim');
        if (this.value !== 'Sim') {
          elements.tipoProtecaoGastrica.value = '';
        }
      });

      elements.usoTrombofilaxia.addEventListener('change', function() {
        elements.trombofilaxiaDetails.classList.toggle('hidden', this.value !== 'Sim');
        if (this.value !== 'Sim') {
          elements.tipoTrombofilaxia.value = '';
        }
      });

      // Manipuladores para botões de ação
      elements.saveData.addEventListener('click', function() {
        if (!validateForm()) {
          showToast('Por favor, preencha todos os campos obrigatórios', 5000);
          return;
        }

        const formData = new FormData(document.getElementById('roundMatinalForm'));
        const dados = {};
        
        for (const [key, value] of formData.entries()) {
          dados[key] = value;
        }
        
        dados.timestamp = new Date().toISOString();
        
        try {
          // Salvar no armazenamento temporário do navegador (para fins de demonstração)
          // Em um aplicativo real, isto poderia ser substituído por um armazenamento mais permanente
          const salvosString = sessionStorage.getItem('formularios') || '[]';
          const salvos = JSON.parse(salvosString);
          salvos.push(dados);
          sessionStorage.setItem('formularios', JSON.stringify(salvos));
          
          formState.lastSaved = new Date();
          formState.patientData = { ...dados };
          
          showToast('Dados salvos com sucesso!', 3000);
        } catch (error) {
          showToast('Erro ao salvar dados: ' + error.message, 5000);
        }
      });

      elements.exportarCSV.addEventListener('click', function() {
        try {
          const salvosString = sessionStorage.getItem('formularios');
          const salvos = salvosString ? JSON.parse(salvosString) : [];
          
          if (salvos.length === 0) {
            // Se não houver dados salvos, usar os dados do formulário atual
            if (!validateForm()) {
              showToast('Por favor, preencha todos os campos obrigatórios para exportar', 5000);
              return;
            }
            
            const formData = new FormData(document.getElementById('roundMatinalForm'));
            const dados = {};
            
            for (const [key, value] of formData.entries()) {
              dados[key] = value;
            }
            
            dados.timestamp = new Date().toISOString();
            salvos.push(dados);
          }

          const headers = Object.keys(salvos[0]);
          const csvContent = [
            headers.join(','),
            ...salvos.map(row => headers.map(header => {
              // Colocar aspas duplas ao redor de valores que contêm vírgulas ou novas linhas
              const val = row[header] || '';
              if (val.includes(',') || val.includes('\n') || val.includes('"')) {
                return `"${val.replace(/"/g, '""')}"`;
              }
              return val;
            }).join(','))
          ].join('\n');

          // Criar um objeto Blob e um link para download
          const blob = new Blob([csvContent], { type: 'text/csv;charset=utf-8;' });
          const url = URL.createObjectURL(blob);
          const link = document.createElement('a');
          
          link.setAttribute('href', url);
          link.setAttribute('download', 'round_matinal_' + new Date().toISOString().slice(0,10) + '.csv');
          link.style.visibility = 'hidden';
          
          document.body.appendChild(link);
          link.click();
          document.body.removeChild(link);
          
          showToast('CSV exportado com sucesso!', 3000);
        } catch (error) {
          showToast('Erro ao exportar CSV: ' + error.message, 5000);
        }
      });

      elements.exportarPDF.addEventListener('click', function() {
        // Mostrar ao usuário como salvar usando funcionalidade nativa do navegador
        showToast('Use a função de impressão do navegador (Ctrl+P) para salvar como PDF', 6000);
        
        // Criar versão de impressão
        const resumoContent = document.getElementById('resumoContent');
        if (resumoContent.children.length <= 1) {
          // Se o resumo ainda não foi gerado
          showToast('Gerando resumo para exportação...', 3000);
          generateSummary();
        }
        
        // Atrasar um pouco para dar tempo de gerar o resumo
        setTimeout(() => {
          window.print();
        }, 1000);
      });

      elements.clearForm.addEventListener('click', function() {
        if (confirm('Tem certeza de que deseja limpar todos os dados do formulário?')) {
          document.getElementById('roundMatinalForm').reset();
          
          // Limpar containers dinâmicos
          elements.cateteresContainer.innerHTML = '';
          elements.sondasContainer.innerHTML = '';
          elements.drogasContainer.innerHTML = '';
          elements.sedacaoContainer.innerHTML = '';
          elements.analgesiaContainer.innerHTML = '';
          elements.antibioticosContainer.innerHTML = '';
          
          // Adicionar uma entrada em cada container
          elements.cateteresContainer.appendChild(createCateterEntry());
          elements.sondasContainer.appendChild(createSondaEntry());
          elements.drogasContainer.appendChild(createDrogaEntry());
          elements.sedacaoContainer.appendChild(createMedicationEntry('sedacao'));
          elements.analgesiaContainer.appendChild(createMedicationEntry('analgesia'));
          elements.antibioticosContainer.appendChild(createAntibioticoEntry());
          
          // Esconder seções condicionais
          elements.intubacaoDetails.classList.add('hidden');
          elements.psvDetails.classList.add('hidden');
          elements.traqueostomiaContainer.classList.add('hidden');
          elements.dataTraqueostomiaContainer.classList.add('hidden');
          elements.quantidadeContainer.classList.add('hidden');
          elements.protecaoGastricaDetails.classList.add('hidden');
          elements.trombofilaxiaDetails.classList.add('hidden');
          
          // Resetar valores calculados
          elements.tempoInternacao.value = '';
          elements.tempoIntubacao.value = '';
          elements.tempoDesdeEvacuacao.value = '';
          
          // Configurar data de preenchimento para hoje
          elements.dataPreenchimento.valueAsDate = new Date();
          
          // Voltar para a primeira aba
          showTab('identificacao');
          
          showToast('Formulário limpo com sucesso!', 3000);
        }
      });

      // Inicializações
      atualizarDataMaxima();
      
      // Atualizações automáticas para cálculos de tempo
      setInterval(() => {
        if (elements.dataIntubacao && elements.dataIntubacao.value) {
          calcularTempoIntubacao();
        }
        
        if (elements.dataUltimaEvacuacao && elements.dataUltimaEvacuacao.value) {
          calcularTempoDesdeEvacuacao();
        }
        
        // Atualizar tempos de uso de cateteres
        document.querySelectorAll('.data-insercao-cateter').forEach(input => {
          if (input.value) {
            const tempoUsoInput = input.closest('.medication-entry').querySelector('.tempo-uso-cateter');
            calcularTempoUso(input, tempoUsoInput);
          }
        });
        
        // Atualizar tempos de uso de antibióticos
        document.querySelectorAll('.data-inicio-antibiotico').forEach(input => {
          if (input.value) {
            const tempoUsoInput = input.closest('.medication-entry').querySelector('.tempo-uso-antibiotico');
            calcularTempoUsoAntibiotico(input, tempoUsoInput);
          }
        });
      }, 60000); // Atualizar a cada minuto
      
      // Atualizar datas máximas periodicamente
      setInterval(atualizarDataMaxima, 60000);
    });
  </script>
</body>
</html>
