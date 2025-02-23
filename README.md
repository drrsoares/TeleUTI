<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Round Matinal - UTI</title>
    <style>
      /* Estilos Gerais */
    body {
      font-family: Arial, sans-serif;
      background-color: #f3f4f6;
      margin: 0;
      padding: 10px;
    }

    .container {
      max-width: 900px;
      margin: 0 auto;
      background: #ffffff;
      padding: 20px;
      border-radius: 8px;
      box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    }

    h1, h2 {
      text-align: center;
      color: #333;
      margin-bottom: 20px;
    }

    h1 {
      font-size: 1.8rem;
    }

    h2 {
      font-size: 1.4rem;
      color: #555;
    }

    label {
      font-weight: bold;
      display: block;
      margin-bottom: 5px;
    }

    input, select, textarea, button {
      width: 100%;
      padding: 10px;
      margin-bottom: 15px;
      border: 1px solid #ccc;
      border-radius: 4px;
      font-size: 1rem;
      box-sizing: border-box;
    }

    textarea {
      resize: vertical;
    }

    button {
      background-color: #007bff;
      color: white;
      border: none;
      cursor: pointer;
      font-size: 1rem;
      padding: 10px 15px;
      border-radius: 4px;
    }

    button:hover {
      background-color: #0056b3;
    }

    .remove-btn {
      background-color: #dc3545;
      color: white;
      font-size: 0.9rem;
    }

    .remove-btn:hover {
      background-color: #c82333;
    }

    .hidden {
      display: none;
    }

    .flex-container {
      display: flex;
      gap: 10px;
    }

    .flex-container > div {
      flex: 1;
    }

    .export-buttons {
      display: flex;
      justify-content: center;
      gap: 10px;
    }

    /* Modal Styles */
    .modal {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0, 0, 0, 0.5);
      display: flex;
      justify-content: center;
      align-items: center;
      z-index: 1000;
    }

    .modal.hidden {
      display: none;
    }

    .modal-content {
      background: #ffffff;
      padding: 20px;
      border-radius: 8px;
      box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
      text-align: center;
      max-width: 400px;
      width: 90%;
    }

    .modal-actions {
      display: flex;
      justify-content: space-around;
      margin-top: 20px;
    }

    .confirm-btn {
      background-color: #28a745;
      color: white;
    }

    .confirm-btn:hover {
      background-color: #218838;
    }

    @media (max-width: 600px) {
      body {
        padding: 0 5px;
      }

      h1 {
        font-size: 1.5rem;
      }

      input, select, textarea, button {
        font-size: 0.9rem;
        padding: 8px;
      }
    }

    /* Add new styles for validation */
    .invalid {
        border-color: #dc3545;
    }

    .validation-message {
        color: #dc3545;
        font-size: 0.8rem;
        margin-top: -10px;
        margin-bottom: 10px;
    }

    /* Add style for the print preview */
    @media print {
        .no-print {
            display: none;
        }
        .container {
            box-shadow: none;
            padding: 0;
        }
    }
    /* Adicione estes estilos ao seu CSS existente */
    .status-container {
      position: relative;
      display: flex;
      align-items: center;
    }

    .status-indicator {
      width: 12px;
      height: 12px;
      border-radius: 50%;
      margin-left: 10px;
      background-color: #ccc;
    }

    .status-ok {
      background-color: #28a745;
    }

    .status-warning {
      background-color: #ffc107;
    }

    .status-danger {
      background-color: #dc3545;
      animation: pulse 1s infinite;
    }

    .alert-box {
      background-color: #fff3cd;
      border: 1px solid #ffeeba;
      color: #856404;
      padding: 10px;
      border-radius: 4px;
      margin: 10px 0;
    }

    .checkbox-container {
      margin: 10px 0;
      display: flex;
      align-items: center;
      gap: 10px;
    }

    .checkbox-container input[type="checkbox"] {
      width: auto;
      margin: 0;
    }

    #tempoIntubacao.warning {
      color: #856404;
      background-color: #fff3cd;
    }

    #tempoIntubacao.danger {
      color: #721c24;
      background-color: #f8d7da;
    }

    @keyframes pulse {
      0% { transform: scale(1); }
      50% { transform: scale(1.2); }
      100% { transform: scale(1); }
    }
    </style>
    
    </style>
</head>
<body>

  <div class="container">
    <h1>Round Matinal - UTI</h1>
    <form id="roundMatinalForm">
      <!-- Identificação do Paciente -->
      <section class="section">
        <h2>Identificação do Paciente</h2>
        <label for="nomePaciente">Nome:</label>
        <input type="text" id="nomePaciente" name="nomePaciente" placeholder="Digite o nome do paciente" required>

        <div class="flex-container">
          <div>
            <label for="registroHospitalar">Registro Hospitalar:</label>
            <input type="text" id="registroHospitalar" name="registroHospitalar" placeholder="Digite o registro hospitalar" required>
          </div>
          <div>
            <label for="leito">Leito:</label>
            <input type="text" id="leito" name="leito" placeholder="Digite o número do leito" required>
          </div>
        </div>

        <div class="flex-container">
          <div>
            <label for="dataInternacao">Data de Internação:</label>
            <input type="date" id="dataInternacao" name="dataInternacao" required>
          </div>
          <div>
            <label for="dataPreenchimento">Data do Preenchimento:</label>
            <input type="date" id="dataPreenchimento" name="dataPreenchimento">
          </div>
        </div>

        <label for="tempoInternacao">Tempo de Internação (dias):</label>
        <input type="text" id="tempoInternacao" name="tempoInternacao" readonly placeholder="Será calculado automaticamente">
      
      </section>
      <!-- Ventilação Mecânica -->
<section class="section">
  <h2>Ventilação Mecânica</h2>
  <label for="pacienteIntubado">Paciente Intubado?</label>
  <select id="pacienteIntubado" name="pacienteIntubado" required>
    <option value="" disabled selected>Selecione uma opção</option>
    <option value="Sim">Sim</option>
    <option value="Não">Não</option>
  </select>

  <div id="intubacaoDetails" class="hidden">
    <div class="flex-container">
      <div>
        <label for="dataIntubacao">Data de Intubação:</label>
        <input type="datetime-local" id="dataIntubacao" name="dataIntubacao">
      </div>
      <div>
        <label for="tempoIntubacao">Tempo de Intubação:</label>
        <div class="status-container">
          <input type="text" id="tempoIntubacao" name="tempoIntubacao" readonly 
            placeholder="Será calculado automaticamente">
          <span id="statusIntubacao" class="status-indicator"></span>
        </div>
      </div>
    </div>

    <label for="modoVentilacao">Modo de Ventilação:</label>
    <select id="modoVentilacao" name="modoVentilacao">
      <option value="" disabled selected>Selecione um modo</option>
      <option value="PCV">PCV</option>
      <option value="VCV">VCV</option>
      <option value="PSV">PSV</option>
      <option value="Outros">Outros</option>
    </select>

    <div id="psvDetails" class="hidden">
      <label for="podeExtubar">Paciente Pode Extubar?</label>
      <select id="podeExtubar" name="podeExtubar">
        <option value="" disabled selected>Selecione uma opção</option>
        <option value="Sim">Sim</option>
        <option value="Não">Não</option>
      </select>
    </div>

    <div id="traqueostomiaContainer" class="hidden">
      <div class="alert-box">
        <p>Paciente com mais de 5 dias de intubação. Considerar traqueostomia.</p>
      </div>
      <div class="checkbox-container">
        <input type="checkbox" id="realizouTraqueostomia" name="realizouTraqueostomia">
        <label for="realizouTraqueostomia">Realizou Traqueostomia?</label>
      </div>
      <div id="dataTraqueostomiaContainer" class="hidden">
        <label for="dataTraqueostomia">Data da Traqueostomia:</label>
        <input type="datetime-local" id="dataTraqueostomia" name="dataTraqueostomia">
      </div>
    </div>
      </div>
    </section>

      <!-- Sedação -->
      <section class="section">
        <h2>Sedação</h2>
        <div id="sedacaoContainer">
          <div class="medication-entry">
            <label for="medicacaoSedacao">Medicação:</label>
            <select class="medicacao-dropdown" name="medicacaoSedacao[]" required>
              <option value="" disabled selected>Selecione uma opção</option>
              <option value="Midazolan">Midazolan</option>
              <option value="Propofol">Propofol</option>
              <option value="Cetamina">Cetamina</option>
              <option value="Dexmedetomidina">Dexmedetomidina</option>
              <option value="Outros">Outros</option>
            </select>
            <input type="text" class="dose-input" name="doseSedacao[]" placeholder="Dose em uso (mg/h)">
            <button type="button" class="remove-btn">Remover</button>
          </div>
        </div>
        <button type="button" id="addSedacao">Adicionar Sedação</button>
      </section>

      <!-- Analgesia -->
      <section class="section">
        <h2>Analgesia</h2>
        <div id="analgesiaContainer">
          <div class="medication-entry">
            <label for="medicacaoAnalgesia">Medicação:</label>
            <select class="medicacao-dropdown" name="medicacaoAnalgesia[]" required>
              <option value="" disabled selected>Selecione uma opção</option>
              <option value="Dipirona">Dipirona</option>
              <option value="Morfina">Morfina</option>
              <option value="Fentanil">Fentanil</option>
              <option value="Metadona">Metadona</option>
              <option value="Outros">Outros</option>
            </select>
            <input type="text" class="dose-input" name="doseAnalgesia[]" placeholder="Dose em uso (mg)">
            <button type="button" class="remove-btn">Remover</button>
          </div>
        </div>
        <button type="button" id="addAnalgesia">Adicionar Analgesia</button>
      </section>
      
      <!-- Alimentação -->
      <section class="section">
        <h2>Alimentação</h2>
        <label for="viaAlimentacao">Via de Alimentação:</label>
        <select id="viaAlimentacao" name="viaAlimentacao" required>
          <option value="" disabled selected>Selecione uma opção</option>
          <option value="VO">VO</option>
          <option value="SNG">SNG</option>
          <option value="SNE">SNE</option>
          <option value="Gastrostomia">Gastrostomia</option>
          <option value="Jejunostomia">Jejunostomia</option>
          <option value="Jejum">Jejum</option>
        </select>

        <div id="quantidadeContainer" class="hidden">
          <label for="quantidadeDiaria">Quantidade Diária (ml):</label>
          <input type="number" id="quantidadeDiaria" name="quantidadeDiaria" placeholder="Informe a quantidade diária">
        </div>
      </section>

 <!-- Trombofilaxia -->
      <section class="section">
        <h2>Trombofilaxia</h2>
        <label for="usoTrombofilaxia">Uso de Trombofilaxia:</label>
        <select id="usoTrombofilaxia" name="usoTrombofilaxia" required>
          <option value="" disabled selected>Selecione uma opção</option>
          <option value="Sim">Sim</option>
          <option value="Não">Não</option>
        </select>

        <div id="trombofilaxiaDetails" class="hidden">
          <label for="tipoTrombofilaxia">Tipo de Trombofilaxia:</label>
          <select id="tipoTrombofilaxia" name="tipoTrombofilaxia">
            <option value="" disabled selected>Selecione um tipo</option>
            <option value="Heparina">Heparina</option>
            <option value="Enoxaparina">Enoxaparina</option>
            <option value="Outros">Outros</option>
          </select>
        </div>
      </section>

      <!-- Cabeceira e Conforto -->
      <section class="section">
        <h2>Cabeceira e Conforto</h2>
        <label for="elevacaoCabeceira">Elevação da Cabeceira:</label>
        <select id="elevacaoCabeceira" name="elevacaoCabeceira" required>
          <option value="" disabled selected>Selecione uma opção</option>
          <option value="0 graus">0 graus</option>
          <option value="30 graus">30 graus</option>
          <option value="45 graus">45 graus</option>
          <option value="Acima de 45 graus">Acima de 45 graus</option>
        </select>

        <label for="nivelConforto">Nível de Conforto do Paciente:</label>
        <select id="nivelConforto" name="nivelConforto" required>
          <option value="" disabled selected>Selecione uma opção</option>
          <option value="Confortável">Confortável</option>
          <option value="Moderadamente desconfortável">Moderadamente desconfortável</option>
          <option value="Muito desconfortável">Muito desconfortável</option>
        </select>
      </section>

      <!-- Proteção Gástrica -->
      <section class="section">
        <h2>Proteção Gástrica</h2>
        <label for="usoProtecaoGastrica">Uso de Proteção Gástrica:</label>
        <select id="usoProtecaoGastrica" name="usoProtecaoGastrica" required>
          <option value="" disabled selected>Selecione uma opção</option>
          <option value="Sim">Sim</option>
          <option value="Não">Não</option>
        </select>

        <div id="protecaoGastricaDetails" class="hidden">
          <label for="tipoProtecaoGastrica">Tipo de Proteção Gástrica:</label>
          <select id="tipoProtecaoGastrica" name="tipoProtecaoGastrica">
            <option value="" disabled selected>Selecione uma opção</option>
            <option value="Omeprazol">Omeprazol</option>
            <option value="Pantoprazol">Pantoprazol</option>
            <option value="Ranitidina">Ranitidina</option>
            <option value="Outros">Outros</option>
          </select>
        </div>
      </section>

      <!-- Controle Glicêmico -->
      <section class="section">
        <h2>Controle Glicêmico</h2>
        <label for="glicemiaAtual">Glicemia Atual (mg/dL):</label>
        <input type="number" id="glicemiaAtual" name="glicemiaAtual" placeholder="Informe a glicemia atual">

        <label for="controleGlicemico">Controle Glicêmico:</label>
        <select id="controleGlicemico" name="controleGlicemico" required>
          <option value="" disabled selected>Selecione uma opção</option>
          <option value="Insulina NPH">Insulina NPH</option>
          <option value="Insulina Regular">Insulina Reg</option>
          <option value="Nenhum">Nenhum</option>
        </select>
      </section>

     <!-- Modifique a seção Trânsito Intestinal no HTML -->
    <section class="section">
      <h2>Trânsito Intestinal</h2>
      <label for="transitoIntestinal">Trânsito Intestinal:</label>
      <select id="transitoIntestinal" name="transitoIntestinal" required>
    <option value="" disabled selected>Selecione uma opção</option>
    <option value="Normal">Normal</option>
    <option value="Constipado">Constipado</option>
    <option value="Diarreia">Diarreia</option>
      </select>

      <div class="flex-container">
    <div>
      <label for="dataUltimaEvacuacao">Data da Última Evacuação:</label>
      <input type="datetime-local" id="dataUltimaEvacuacao" name="dataUltimaEvacuacao">
    </div>
    <div>
      <label for="tempoDesdeEvacuacao">Tempo desde Última Evacuação:</label>
      <input type="text" id="tempoDesdeEvacuacao" name="tempoDesdeEvacuacao" readonly 
        placeholder="Será calculado automaticamente">
    </div>
      </div>
    </section>

       <!-- Uso de Antibióticos -->
      <section class="section">
        <h2>Uso de Antibióticos</h2>
        <div id="antibioticosContainer">
          <div class="medication-entry">
            <label for="antibiotico">Antibiótico:</label>
            <select class="antibiotico-dropdown" name="antibiotico[]" required>
              <option value="" disabled selected>Selecione um antibiótico</option>
              <option value="Vancomicina">Vancomicina</option>
              <option value="Ceftriaxone">Ceftriaxone</option>
              <option value="Meropenem">Meropenem</option>
              <option value="Tazocin">Tazocin</option>
              <option value="Poli B">Poli B</option>
              <option value="Outro">Outro</option>
            </select>

            <div class="outro-antibiotico hidden">
              <label for="outroAntibiotico">Nome do Antibiótico:</label>
              <input type="text" name="outroAntibiotico[]" placeholder="Digite o nome do antibiótico">
            </div>

            <div class="flex-container">
              <div>
                <label for="dataInicioAntibiotico">Data de Início:</label>
                <input type="date" name="dataInicioAntibiotico[]" class="data-inicio-antibiotico" required>
              </div>
              <div>
                <label for="tempoUsoAntibiotico">Tempo de Uso (dias):</label>
                <input type="text" name="tempoUsoAntibiotico[]" class="tempo-uso-antibiotico" readonly placeholder="Calculado automaticamente">
              </div>
            </div>

            <button type="button" class="remove-btn">Remover</button>
          </div>
        </div>
        <button type="button" id="addAntibiotico">Adicionar Antibiótico</button>
      </section>


      <!-- Botões de Ação -->
      <div class="export-buttons">
        <button type="button" id="saveData">Salvar Dados</button>
        <button type="button" id="exportarCSV">Exportar para CSV</button>
        <button type="button" id="exportarPDF">Exportar Resumo em PDF</button>
      </div>
    </form>
  </div>

     <script>
    // Adicionar lógica para exibir campos de alimentação
    const viaAlimentacao = document.getElementById("viaAlimentacao");
    const quantidadeContainer = document.getElementById("quantidadeContainer");

    viaAlimentacao.addEventListener("change", () => {
      if (["SNG", "SNE", "Gastrostomia", "Jejunostomia"].includes(viaAlimentacao.value)) {
        quantidadeContainer.classList.remove("hidden");
      } else {
        quantidadeContainer.classList.add("hidden");
      }
    });

    // Função para salvar dados no LocalStorage
    document.getElementById('saveData').addEventListener('click', () => {
      const form = document.getElementById('roundMatinalForm');
      const formData = new FormData(form);
      const dados = {};
      formData.forEach((value, key) => {
        dados[key] = value;
      });

      // Salvar no LocalStorage
      const salvos = JSON.parse(localStorage.getItem('formularios')) || [];
      salvos.push(dados);
      localStorage.setItem('formularios', JSON.stringify(salvos));
      alert('Dados salvos com sucesso!');
    });

    // Função para exportar para CSV
    document.getElementById('exportarCSV').addEventListener('click', () => {
      const salvos = JSON.parse(localStorage.getItem('formularios')) || [];
      if (salvos.length === 0) {
        alert('Nenhum dado salvo para exportar!');
        return;
      }

      const headers = Object.keys(salvos[0]);
      const rows = salvos.map(obj => headers.map(header => obj[header]));

      let csv = headers.join(',') + '\n';
      rows.forEach(row => {
        csv += row.join(',') + '\n';
      });

      const blob = new Blob([csv], { type: 'text/csv' });
      const a = document.createElement('a');
      a.href = URL.createObjectURL(blob);
      a.download = 'dados_pacientes.csv';
      a.click();
    });

    // Exibir campos adicionais para ventilação mecânica
    const pacienteIntubado = document.getElementById('pacienteIntubado');
    const intubacaoDetails = document.getElementById('intubacaoDetails');
    const modoVentilacao = document.getElementById('modoVentilacao');
    const psvDetails = document.getElementById('psvDetails');

    pacienteIntubado.addEventListener('change', () => {
      if (pacienteIntubado.value === 'Sim') {
        intubacaoDetails.classList.remove('hidden');
      } else {
        intubacaoDetails.classList.add('hidden');
      }
    });

    modoVentilacao.addEventListener('change', () => {
      if (modoVentilacao.value === 'PSV') {
        psvDetails.classList.remove('hidden');
      } else {
        psvDetails.classList.add('hidden');
      }
    });

    // Adicionar/remover sedação
    const sedacaoContainer = document.getElementById('sedacaoContainer');
    const addSedacaoButton = document.getElementById('addSedacao');

    addSedacaoButton.addEventListener('click', () => {
      const entry = document.createElement('div');
      entry.classList.add('medication-entry');
      entry.innerHTML = `
        <label for="medicacaoSedacao">Medicação:</label>
        <select class="medicacao-dropdown" name="medicacaoSedacao[]" required>
          <option value="" disabled selected>Selecione uma opção</option>
          <option value="Midazolan">Midazolan</option>
          <option value="Propofol">Propofol</option>
          <option value="Cetamina">Cetamina</option>
          <option value="Dexmedetomidina">Dexmedetomidina</option>
          <option value="Outros">Outros</option>
        </select>
        <input type="text" class="dose-input" name="doseSedacao[]" placeholder="Dose em uso (mg/h)">
        <button type="button" class="remove-btn">Remover</button>
      `;

      entry.querySelector('.remove-btn').addEventListener('click', () => {
        entry.remove();
      });

      sedacaoContainer.appendChild(entry);
    });

    // Adicionar/remover analgesia
    const analgesiaContainer = document.getElementById('analgesiaContainer');
    const addAnalgesiaButton = document.getElementById('addAnalgesia');

    addAnalgesiaButton.addEventListener('click', () => {
      const entry = document.createElement('div');
      entry.classList.add('medication-entry');
      entry.innerHTML = `
        <label for="medicacaoAnalgesia">Medicação:</label>
        <select class="medicacao-dropdown" name="medicacaoAnalgesia[]" required>
          <option value="" disabled selected>Selecione uma opção</option>
          <option value="Dipirona">Dipirona</option>
          <option value="Morfina">Morfina</option>
          <option value="Fentanil">Fentanil</option>
          <option value="Metadona">Metadona</option>
          <option value="Outros">Outros</option>
        </select>
        <input type="text" class="dose-input" name="doseAnalgesia[]" placeholder="Dose em uso (mg)">
        <button type="button" class="remove-btn">Remover</button>
      `;

      entry.querySelector('.remove-btn').addEventListener('click', () => {
        entry.remove();
      });

      analgesiaContainer.appendChild(entry);
    });
  </script>

<script>
    // Seções Dinâmicas (Trombofilaxia, Proteção Gástrica e Antibióticos)
    const usoTrombofilaxia = document.getElementById('usoTrombofilaxia');
    const trombofilaxiaDetails = document.getElementById('trombofilaxiaDetails');
    usoTrombofilaxia.addEventListener('change', () => {
      trombofilaxiaDetails.classList.toggle('hidden', usoTrombofilaxia.value !== 'Sim');
    });

    const usoProtecaoGastrica = document.getElementById('usoProtecaoGastrica');
    const protecaoGastricaDetails = document.getElementById('protecaoGastricaDetails');
    usoProtecaoGastrica.addEventListener('change', () => {
      protecaoGastricaDetails.classList.toggle('hidden', usoProtecaoGastrica.value !== 'Sim');
    });

    // Adicionar/remover antibióticos
    const antibioticosContainer = document.getElementById('antibioticosContainer');
    const addAntibioticoButton = document.getElementById('addAntibiotico');
    addAntibioticoButton.addEventListener('click', () => {
      const entry = document.createElement('div');
      entry.classList.add('medication-entry');
      entry.innerHTML = `
        <label for="antibiotico">Antibiótico:</label>
        <input type="text" class="antibiotico-input" name="antibiotico[]" placeholder="Nome do antibiótico">
        <input type="text" class="dose-input" name="doseAntibiotico[]" placeholder="Dose em uso">
        <button type="button" class="remove-btn">Remover</button>
      `;

      entry.querySelector('.remove-btn').addEventListener('click', () => {
        entry.remove();
      });

      antibioticosContainer.appendChild(entry);
    });
  </script>

   <script>
    document.addEventListener('DOMContentLoaded', function() {
        // Automatic date calculations
        function calculateDays(startDate, endDate) {
            const start = new Date(startDate);
            const end = new Date(endDate);
            const diffTime = Math.abs(end - start);
            return Math.ceil(diffTime / (1000 * 60 * 60 * 24));
        }

        // Set default date for dataPreenchimento
        document.getElementById('dataPreenchimento').valueAsDate = new Date();

        // Calculate internment duration
        document.getElementById('dataInternacao').addEventListener('change', function() {
            const internmentDate = this.value;
            const currentDate = document.getElementById('dataPreenchimento').value;
            if (internmentDate && currentDate) {
                document.getElementById('tempoInternacao').value = calculateDays(internmentDate, currentDate);
            }
        });

        // Calculate antibiotics usage duration
        document.querySelectorAll('.data-inicio-antibiotico').forEach(input => {
            input.addEventListener('change', function() {
                const startDate = this.value;
                const currentDate = document.getElementById('dataPreenchimento').value;
                if (startDate && currentDate) {
                    const daysElement = this.closest('.medication-entry').querySelector('.tempo-uso-antibiotico');
                    daysElement.value = calculateDays(startDate, currentDate);
                }
            });
        });

        // Form validation
        function validateForm() {
            let isValid = true;
            const requiredFields = document.querySelectorAll('[required]');
            
            requiredFields.forEach(field => {
                if (!field.value) {
                    field.classList.add('invalid');
                    isValid = false;
                    
                    // Add validation message
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

        // Enhanced save functionality
        document.getElementById('saveData').addEventListener('click', function() {
            if (!validateForm()) {
                alert('Por favor, preencha todos os campos obrigatórios');
                return;
            }

            const form = document.getElementById('roundMatinalForm');
            const formData = new FormData(form);
            const dados = Object.fromEntries(formData);
            
            // Add timestamp
            dados.timestamp = new Date().toISOString();
            
            // Save to localStorage
            const salvos = JSON.parse(localStorage.getItem('formularios')) || [];
            salvos.push(dados);
            localStorage.setItem('formularios', JSON.stringify(salvos));
            
            alert('Dados salvos com sucesso!');
        });

        // Enhanced PDF export
        document.getElementById('exportarPDF').addEventListener('click', function() {
            if (!validateForm()) {
                alert('Por favor, preencha todos os campos obrigatórios antes de exportar');
                return;
            }

            // Create print-friendly version
            const printContent = document.createElement('div');
            printContent.innerHTML = `
                <h1>Resumo do Round Matinal - UTI</h1>
                <p><strong>Paciente:</strong> ${document.getElementById('nomePaciente').value}</p>
                <p><strong>Registro:</strong> ${document.getElementById('registroHospitalar').value}</p>
                <p><strong>Leito:</strong> ${document.getElementById('leito').value}</p>
                <p><strong>Data:</strong> ${new Date().toLocaleDateString()}</p>
                <!-- Add more relevant fields -->
            `;

            // Open print dialog
            const printWindow = window.open('', '_blank');
            printWindow.document.write('<html><head><title>Round Matinal - UTI</title>');
            printWindow.document.write('</head><body>');
            printWindow.document.write(printContent.innerHTML);
            printWindow.document.write('</body></html>');
            printWindow.document.close();
            printWindow.print();
        });
    });
    </script>
   
   <script>
document.addEventListener('DOMContentLoaded', function() {
    // ... (mantenha os scripts anteriores)

    // Função para calcular o tempo desde a última evacuação
    function calcularTempoDesdeEvacuacao() {
        const dataEvacuacao = new Date(document.getElementById('dataUltimaEvacuacao').value);
        const agora = new Date();
        
        if (isNaN(dataEvacuacao.getTime())) {
            document.getElementById('tempoDesdeEvacuacao').value = '';
            return;
        }

        const diffMs = agora - dataEvacuacao;
        const diffHoras = Math.floor(diffMs / (1000 * 60 * 60));
        const diffDias = Math.floor(diffHoras / 24);
        const horasRestantes = diffHoras % 24;

        let resultado = '';
        if (diffDias > 0) {
            resultado += `${diffDias} dia(s) `;
        }
        if (horasRestantes > 0 || diffDias === 0) {
            resultado += `${horasRestantes} hora(s)`;
        }

        document.getElementById('tempoDesdeEvacuacao').value = resultado;

        // Atualizar estilo baseado no tempo
        const tempoEvacuacaoInput = document.getElementById('tempoDesdeEvacuacao');
        if (diffHoras >= 72) { // Mais de 72 horas
            tempoEvacuacaoInput.style.color = 'red';
            tempoEvacuacaoInput.style.fontWeight = 'bold';
        } else if (diffHoras >= 48) { // Mais de 48 horas
            tempoEvacuacaoInput.style.color = 'orange';
            tempoEvacuacaoInput.style.fontWeight = 'bold';
        } else {
            tempoEvacuacaoInput.style.color = 'green';
            tempoEvacuacaoInput.style.fontWeight = 'normal';
        }
    }

    // Adicionar evento para calcular o tempo quando a data for alterada
    document.getElementById('dataUltimaEvacuacao').addEventListener('change', calcularTempoDesdeEvacuacao);

    // Atualizar o tempo a cada minuto
    setInterval(calcularTempoDesdeEvacuacao, 60000);

    // Definir a data e hora atual como valor máximo para o input
    const dataUltimaEvacuacaoInput = document.getElementById('dataUltimaEvacuacao');
    const agora = new Date();
    const anoAtual = agora.getFullYear();
    const mesAtual = String(agora.getMonth() + 1).padStart(2, '0');
    const diaAtual = String(agora.getDate()).padStart(2, '0');
    const horaAtual = String(agora.getHours()).padStart(2, '0');
    const minutoAtual = String(agora.getMinutes()).padStart(2, '0');
    
    dataUltimaEvacuacaoInput.max = `${anoAtual}-${mesAtual}-${diaAtual}T${horaAtual}:${minutoAtual}`;
});

    <script>
        
       <script>
document.addEventListener('DOMContentLoaded', function() {
    const pacienteIntubado = document.getElementById('pacienteIntubado');
    const intubacaoDetails = document.getElementById('intubacaoDetails');
    const dataIntubacao = document.getElementById('dataIntubacao');
    const tempoIntubacao = document.getElementById('tempoIntubacao');
    const statusIntubacao = document.getElementById('statusIntubacao');
    const traqueostomiaContainer = document.getElementById('traqueostomiaContainer');
    const realizouTraqueostomia = document.getElementById('realizouTraqueostomia');
    const dataTraqueostomiaContainer = document.getElementById('dataTraqueostomiaContainer');
    const dataTraqueostomia = document.getElementById('dataTraqueostomia');
    const modoVentilacao = document.getElementById('modoVentilacao');
    const psvDetails = document.getElementById('psvDetails');

    function calcularTempoIntubacao() {
        const dataInicio = new Date(dataIntubacao.value);
        const agora = new Date();
        
        if (isNaN(dataInicio.getTime())) {
            tempoIntubacao.value = '';
            statusIntubacao.className = 'status-indicator';
            traqueostomiaContainer.classList.add('hidden');
            return;
        }

        if (dataInicio > agora) {
            alert('A data de intubação não pode ser no futuro');
            dataIntubacao.value = '';
            return;
        }

        const diffMs = agora - dataInicio;
        const diffDias = Math.floor(diffMs / (1000 * 60 * 60 * 24));
        const diffHoras = Math.floor((diffMs % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));

        tempoIntubacao.value = `${diffDias} dia(s) e ${diffHoras} hora(s)`;

        // Atualizar status visual
        tempoIntubacao.classList.remove('warning', 'danger');
        statusIntubacao.classList.remove('status-ok', 'status-warning', 'status-danger');

        if (diffDias >= 11) {
            tempoIntubacao.classList.add('danger');
            statusIntubacao.classList.add('status-danger');
        } else if (diffDias >= 6) {
            tempoIntubacao.classList.add('warning');
            statusIntubacao.classList.add('status-warning');
        } else {
            statusIntubacao.classList.add('status-ok');
        }

        // Mostrar opção de traqueostomia após 5 dias
        if (diffDias > 5) {
            traqueostomiaContainer.classList.remove('hidden');
        } else {
            traqueostomiaContainer.classList.add('hidden');
            realizouTraqueostomia.checked = false;
            dataTraqueostomia.value = '';
        }
    }

    // Eventos
    pacienteIntubado.addEventListener('change', function() {
        intubacaoDetails.classList.toggle('hidden', this.value !== 'Sim');
        if (this.value !== 'Sim') {
            dataIntubacao.value = '';
            tempoIntubacao.value = '';
            statusIntubacao.className = 'status-indicator';
            traqueostomiaContainer.classList.add('hidden');
            realizouTraqueostomia.checked = false;
            dataTraqueostomia.value = '';
            modoVentilacao.value = '';
            psvDetails.classList.add('hidden');
        }
    });

    modoVentilacao.addEventListener('change', function() {
        psvDetails.classList.toggle('hidden', this.value !== 'PSV');
    });

    dataIntubacao.addEventListener('change', calcularTempoIntubacao);

    realizouTraqueostomia.addEventListener('change', function() {
        dataTraqueostomiaContainer.classList.toggle('hidden', !this.checked);
        if (!this.checked) {
            dataTraqueostomia.value = '';
        }
    });

    dataTraqueostomia.addEventListener('change', function() {
        if (!this.value) return;
        
        const dataTraq = new Date(this.value);
        const dataInt = new Date(dataIntubacao.value);
        const agora = new Date();
        
        if (dataTraq > agora) {
            alert('A data da traqueostomia não pode ser no futuro');
            this.value = '';
            return;
        }
        
        if (dataTraq < dataInt) {
            alert('A data da traqueostomia não pode ser anterior à data de intubação');
            this.value = '';
            return;
        }
    });

    // Atualizar a cada hora
    setInterval(calcularTempoIntubacao, 3600000);

    // Definir máximo como data/hora atual
    function atualizarDataMaxima() {
        const agora = new Date();
        const dataFormatada = agora.toISOString().slice(0, 16);
        dataIntubacao.max = dataFormatada;
        dataTraqueostomia.max = dataFormatada;
    }

    atualizarDataMaxima();
    setInterval(atualizarDataMaxima, 60000);
});
</script>
</body>
</html>
