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

      .clear-btn {
        background-color: #dc3545;
        color: white;
      }

      .clear-btn:hover {
        background-color: #c82333;
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
            <select id="leito" name="leito" required>
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
      </section>
      
 <!-- Uso de Cateteres -->
      <section class="section">
        <h2>Uso de Cateteres</h2>
        <div class="checkbox-container">
          <input type="checkbox" id="usoCateterCentral" name="usoCateterCentral">
          <label for="usoCateterCentral">Cateter Central</label>
        </div>

        <div id="cateterCentralDetails" class="hidden">
          <label for="localizacaoCateter">Localização:</label>
          <select id="localizacaoCateter" name="localizacaoCateter">
            <option value="" disabled selected>Selecione a localização</option>
            <option value="VJD">VJD</option>
            <option value="VJE">VJE</option>
            <option value="VSCD">VSCD</option>
            <option value="VSCE">VSCE</option>
            <option value="FD">FD</option>
            <option value="FE">FE</option>
            <option value="Outro">Outro</option>
          </select>

          <label for="dataInsercaoCateter">Data de Inserção do Cateter:</label>
          <input type="date" id="dataInsercaoCateter" name="dataInsercaoCateter">

          <label for="tempoUsoCateter">Tempo de Uso do Cateter:</label>
          <input type="text" id="tempoUsoCateter" name="tempoUsoCateter" readonly placeholder="Será calculado automaticamente">
        </div>
    

        <!-- Uso de Sondas -->
<section class="section">
    <h2>Uso de Sondas</h2>
    <div id="sondasContainer">
        <!-- As sondas serão adicionadas dinamicamente -->
    </div>
    <button type="button" id="addSonda">Adicionar Sonda</button>
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

<!-- Pendências/Condutas -->
      <section class="section">
        <h2>Pendências / Condutas</h2>
        <label for="pendenciasCondutas">Observações:</label>
        <textarea id="pendenciasCondutas" name="pendenciasCondutas" rows="5" placeholder="Insira aqui as pendências ou condutas do paciente"></textarea>
      </section>

      <!-- Botões de Ação -->
      <div class="export-buttons">
        <button type="button" id="saveData">Salvar Dados</button>
        <button type="button" id="exportarCSV">Exportar para CSV</button>
        <button type="button" id="exportarPDF">Exportar Resumo em PDF</button>
        <button type="button" id="clearForm" class="clear-btn">Limpar Formulário</button>
      </div>
    </form>
     </div>

<script>
document.addEventListener('DOMContentLoaded', function() {
    // Elementos DOM
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
        nivelConforto: document.getElementById('nivelConforto')
    };

    // Configurações iniciais
    elements.dataPreenchimento.valueAsDate = new Date();

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
        elements.dataIntubacao.max = dataFormatada;
        elements.dataTraqueostomia.max = dataFormatada;
        elements.dataUltimaEvacuacao.max = dataFormatada;
    }

    // Funções de Ventilação Mecânica
    function limparCamposIntubacao() {
        elements.tempoIntubacao.value = '';
        elements.statusIntubacao.className = 'status-indicator';
        elements.traqueostomiaContainer.classList.add('hidden');
        elements.realizouTraqueostomia.checked = false;
        elements.dataTraqueostomia.value = '';
    }

    function calcularTempoIntubacao() {
        const dataInicio = new Date(elements.dataIntubacao.value);
        const agora = new Date();
        
        if (isNaN(dataInicio.getTime())) {
            limparCamposIntubacao();
            return;
        }

        if (dataInicio > agora) {
            alert('A data de intubação não pode ser no futuro');
            elements.dataIntubacao.value = '';
            limparCamposIntubacao();
            return;
        }

        const diffMs = agora - dataInicio;
        const diffDias = Math.floor(diffMs / (1000 * 60 * 60 * 24));
        const diffHoras = Math.floor((diffMs % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));

        elements.tempoIntubacao.value = `${diffDias} dia(s) e ${diffHoras} hora(s)`;

        // Atualizar status visual
        elements.tempoIntubacao.classList.remove('warning', 'danger');
        elements.statusIntubacao.classList.remove('status-ok', 'status-warning', 'status-danger');

        if (diffDias >= 11) {
            elements.tempoIntubacao.classList.add('danger');
            elements.statusIntubacao.classList.add('status-danger');
        } else if (diffDias >= 6) {
            elements.tempoIntubacao.classList.add('warning');
            elements.statusIntubacao.classList.add('status-warning');
        } else {
            elements.statusIntubacao.classList.add('status-ok');
        }

        // Verificar necessidade de traqueostomia
        if (diffDias > 5) {
            elements.traqueostomiaContainer.classList.remove('hidden');
        } else {
            elements.traqueostomiaContainer.classList.add('hidden');
            elements.realizouTraqueostomia.checked = false;
            elements.dataTraqueostomia.value = '';
        }
    }
    // Função para cálculo do tempo desde última evacuação
    function calcularTempoDesdeEvacuacao() {
        const dataEvacuacao = new Date(elements.dataUltimaEvacuacao.value);
        const agora = new Date();
        
        if (isNaN(dataEvacuacao.getTime())) {
            elements.tempoDesdeEvacuacao.value = '';
            return;
        }

        if (dataEvacuacao > agora) {
            alert('A data da última evacuação não pode ser no futuro');
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
            elements.tempoDesdeEvacuacao.style.color = 'red';
            elements.tempoDesdeEvacuacao.style.fontWeight = 'bold';
        } else if (diffHoras >= 48) {
            elements.tempoDesdeEvacuacao.style.color = 'orange';
            elements.tempoDesdeEvacuacao.style.fontWeight = 'bold';
        } else {
            elements.tempoDesdeEvacuacao.style.color = 'green';
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

    // Função para criar entradas de medicação
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
            <label for="medicacao${type}">Medicação:</label>
            <select class="medicacao-dropdown" name="medicacao${type}[]" required>
                <option value="" disabled selected>Selecione uma opção</option>
                ${selectOptions}
                <option value="Outros">Outros</option>
            </select>
            <input type="text" class="dose-input" name="dose${type}[]" 
                placeholder="Dose em uso (${type === 'sedacao' ? 'mg/h' : 'mg'})">
            <button type="button" class="remove-btn">Remover</button>
        `;

        entry.querySelector('.remove-btn').addEventListener('click', () => entry.remove());
        return entry;
    }

    // Função para cálculo do tempo de uso de antibióticos
    function calcularTempoUsoAntibiotico(dataInicioInput) {
        const dataInicio = new Date(dataInicioInput.value);
        const hoje = new Date();
        
        if (isNaN(dataInicio.getTime())) return;
        
        if (dataInicio > hoje) {
            alert('A data de início não pode ser no futuro');
            dataInicioInput.value = '';
            return;
        }

        const tempoUsoElement = dataInicioInput.closest('.medication-entry')
            .querySelector('.tempo-uso-antibiotico');
        const diffDias = calculateDays(dataInicio, hoje);
        tempoUsoElement.value = `${diffDias} dia(s)`;
    }

    // Event Listeners
    elements.dataInternacao.addEventListener('change', function() {
        const dataInternacao = new Date(this.value);
        const dataPreenchimento = new Date(elements.dataPreenchimento.value);
        
        if (dataInternacao && dataPreenchimento) {
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
            alert('A data da traqueostomia não pode ser no futuro');
            this.value = '';
            return;
        }
        
        if (dataTraq < dataInt) {
            alert('A data da traqueostomia não pode ser anterior à data de intubação');
            this.value = '';
        }
    });

    elements.dataUltimaEvacuacao.addEventListener('change', calcularTempoDesdeEvacuacao);

    // Event Listeners para proteção gástrica e trombofilaxia
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

    // Event Listeners para adicionar medicações
    document.getElementById('addSedacao').addEventListener('click', () => {
        elements.sedacaoContainer.appendChild(createMedicationEntry('sedacao'));
    });

    document.getElementById('addAnalgesia').addEventListener('click', () => {
        elements.analgesiaContainer.appendChild(createMedicationEntry('analgesia'));
    });

    document.getElementById('addAntibiotico').addEventListener('click', () => {
        const entry = document.createElement('div');
        entry.classList.add('medication-entry');
        entry.innerHTML = `
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
            <div class="flex-container">
                <div>
                    <label for="dataInicioAntibiotico">Data de Início:</label>
                    <input type="date" name="dataInicioAntibiotico[]" class="data-inicio-antibiotico" required>
                </div>
                <div>
                    <label for="tempoUsoAntibiotico">Tempo de Uso (dias):</label>
                    <input type="text" name="tempoUsoAntibiotico[]" class="tempo-uso-antibiotico" readonly>
                </div>
            </div>
            <button type="button" class="remove-btn">Remover</button>
        `;

        entry.querySelector('.remove-btn').addEventListener('click', () => entry.remove());
        entry.querySelector('.data-inicio-antibiotico').addEventListener('change', (e) => 
            calcularTempoUsoAntibiotico(e.target));

        elements.antibioticosContainer.appendChild(entry);
    });

    // Event Listeners para botões de ação
    document.getElementById('saveData').addEventListener('click', function() {
        if (!validateForm()) {
            alert('Por favor, preencha todos os campos obrigatórios');
            return;
        }

        const formData = new FormData(document.getElementById('roundMatinalForm'));
        const dados = Object.fromEntries(formData);
        dados.timestamp = new Date().toISOString();
        
        const salvos = JSON.parse(localStorage.getItem('formularios')) || [];
        salvos.push(dados);
        localStorage.setItem('formularios', JSON.stringify(salvos));
        
        alert('Dados salvos com sucesso!');
    });

    document.getElementById('exportarCSV').addEventListener('click', function() {
        const salvos = JSON.parse(localStorage.getItem('formularios')) || [];
        if (salvos.length === 0) {
            alert('Nenhum dado salvo para exportar!');
            return;
        }

        const headers = Object.keys(salvos[0]);
        const csvContent = [
            headers.join(','),
            ...salvos.map(row => headers.map(header => row[header] || '').join(','))
        ].join('\n');

        const blob = new Blob([csvContent], { type: 'text/csv;charset=utf-8;' });
        const link = document.createElement('a');
        link.href = URL.createObjectURL(blob);
        link.download = 'round_matinal_' + new Date().toISOString().slice(0,10) + '.csv';
        link.click();
    });

    document.getElementById('exportarPDF').addEventListener('click', function() {
        if (!validateForm()) {
            alert('Por favor, preencha todos os campos obrigatórios antes de exportar');
            return;
        }

        const printContent = document.createElement('div');
        printContent.innerHTML = `
            <style>
                body { font-family: Arial, sans-serif; padding: 20px; }
                .header { text-align: center; margin-bottom: 30px; }
                .section { margin-bottom: 20px; }
                .section-title { font-weight: bold; margin-bottom: 10px; }
                .info-row { margin-bottom: 8px; }
            </style>
            
            <div class="header">
                <h1>Resumo do Round Matinal - UTI</h1>
                <p>${new Date().toLocaleDateString()} ${new Date().toLocaleTimeString()}</p>
            </div>

            <div class="section">
                <div class="section-title">Identificação do Paciente</div>
                <div class="info-row"><strong>Nome:</strong> ${elements.nomePaciente.value}</div>
                <div class="info-row"><strong>Registro:</strong> ${elements.registroHospitalar.value}</div>
                <div class="info-row"><strong>Leito:</strong> ${elements.leito.value}</div>
                <div class="info-row"><strong>Tempo de Internação:</strong> ${elements.tempoInternacao.value}</div>
            </div>

            <div class="section">
                <div class="section-title">Status Ventilatório</div>
                <div class="info-row"><strong>Intubado:</strong> ${elements.pacienteIntubado.value}</div>
                ${elements.pacienteIntubado.value === 'Sim' ? `
                    <div class="info-row"><strong>Tempo de Intubação:</strong> ${elements.tempoIntubacao.value}</div>
                    <div class="info-row"><strong>Modo Ventilação:</strong> ${elements.modoVentilacao.value}</div>
                ` : ''}
            </div>

            <div class="section">
                <div class="section-title">Alimentação</div>
                <div class="info-row"><strong>Via:</strong> ${elements.viaAlimentacao.value}</div>
                ${elements.quantidadeDiaria.value ? `
                    <div class="info-row"><strong>Quantidade:</strong> ${elements.quantidadeDiaria.value} ml/dia</div>
                ` : ''}
            </div>

            <div class="section">
                <div class="section-title">Trânsito Intestinal</div>
                <div class="info-row"><strong>Status:</strong> ${elements.transitoIntestinal.value}</div>
                <div class="info-row"><strong>Última Evacuação:</strong> ${elements.tempoDesdeEvacuacao.value}</div>
            </div>
        `;

        const printWindow = window.open('', '_blank');
        printWindow.document.write(printContent.innerHTML);
        printWindow.document.close();
        printWindow.print();
    });

    // Inicializações
    atualizarDataMaxima();
    
    // Atualizações automáticas
    setInterval(calcularTempoIntubacao, 3600000);
    setInterval(calcularTempoDesdeEvacuacao, 60000);
    setInterval(atualizarDataMaxima, 60000);
});

const calcularTempo = (inicio, fim) => {
    const diff = fim - inicio;
    return Math.floor(diff / (1000 * 60 * 60 * 24));
};
document.addEventListener('DOMContentLoaded', function() {
      const usoCateterCentral = document.getElementById('usoCateterCentral');
      const cateterCentralDetails = document.getElementById('cateterCentralDetails');
      const dataInsercaoCateter = document.getElementById('dataInsercaoCateter');
      const tempoUsoCateter = document.getElementById('tempoUsoCateter');

      // Exibir ou ocultar os detalhes do cateter central
      usoCateterCentral.addEventListener('change', function() {
        if (usoCateterCentral.checked) {
          cateterCentralDetails.classList.remove('hidden');
        } else {
          cateterCentralDetails.classList.add('hidden');
          dataInsercaoCateter.value = '';
          tempoUsoCateter.value = '';
        }
      });

      // Calcular o tempo de uso do cateter
      dataInsercaoCateter.addEventListener('change', function() {
        const dataInsercao = new Date(dataInsercaoCateter.value);
        const hoje = new Date();

        if (isNaN(dataInsercao.getTime())) {
          tempoUsoCateter.value = '';
          return;
        }

        if (dataInsercao > hoje) {
          alert('A data de inserção não pode ser no futuro.');
          dataInsercaoCateter.value = '';
          tempoUsoCateter.value = '';
          return;
        }

        const diffMs = hoje - dataInsercao;
        const diffDias = Math.floor(diffMs / (1000 * 60 * 60 * 24));

        tempoUsoCateter.value = `${diffDias} dia(s)`;
      });
    });
    // Função para limpar o formulário
      clearButton.addEventListener('click', function() {
        if (confirm('Tem certeza de que deseja limpar o formulário?')) {
          form.reset(); // Reseta todos os campos do formulário para os valores padrão
          
          // Limpa campos calculados ou gerados dinamicamente
          document.querySelectorAll('input[readonly]').forEach(input => input.value = '');
          document.querySelectorAll('.hidden').forEach(el => el.classList.add('hidden'));
        }
      });
    });
     // Função para criar uma nova entrada de sonda
      function createSondaEntry() {
        const entry = document.createElement('div');
        entry.classList.add('flex-container');
        entry.innerHTML = `
          <div>
            <label for="tipoSonda">Tipo de Sonda:</label>
            <select class="tipo-sonda-dropdown" name="tipoSonda[]" required>
              <option value="" disabled selected>Selecione uma opção</option>
              <option value="SVD">SVD</option>
              <option value="SR">SR</option>
              <option value="Dreno de Torax">Dreno de Tórax</option>
              <option value="Drenos Abdominais">Drenos Abdominais</option>
              <option value="Outros Drenos">Outros Drenos</option>
            </select>
          </div>
          <div class="hidden valor-drenado-container">
            <label for="valorDrenado">Valor Drenado (ml):</label>
            <input type="number" name="valorDrenado[]" placeholder="Insira o valor drenado">
          </div>
          <div>
            <button type="button" class="remove-btn">Remover</button>
          </div>
        `;

        // Listener para mostrar/ocultar o valor drenado
        const tipoSondaDropdown = entry.querySelector('.tipo-sonda-dropdown');
        const valorDrenadoContainer = entry.querySelector('.valor-drenado-container');

        tipoSondaDropdown.addEventListener('change', function() {
          if (
            tipoSondaDropdown.value === 'Dreno de Torax' ||
            tipoSondaDropdown.value === 'Drenos Abdominais' ||
            tipoSondaDropdown.value === 'Outros Drenos'
          ) {
            valorDrenadoContainer.classList.remove('hidden');
          } else {
            valorDrenadoContainer.classList.add('hidden');
          }
        });

        // Listener para remover a entrada
        const removeButton = entry.querySelector('.remove-btn');
        removeButton.addEventListener('click', () => entry.remove());

        return entry;
      }

      document.addEventListener('DOMContentLoaded', function () {
    const form = document.getElementById('roundMatinalForm');
    const sondasContainer = document.getElementById('sondasContainer');
    const addSondaButton = document.getElementById('addSonda');
    const clearButton = document.getElementById('clearForm');

    // Função para criar uma nova entrada de sonda
    function createSondaEntry() {
        const entry = document.createElement('div');
        entry.classList.add('flex-container');
        entry.innerHTML = `
            <div>
                <label for="tipoSonda">Tipo de Sonda:</label>
                <select class="tipo-sonda-dropdown" name="tipoSonda[]" required>
                    <option value="" disabled selected>Selecione uma opção</option>
                    <option value="SVD">SVD</option>
                    <option value="SR">SR</option>
                    <option value="Dreno de Torax">Dreno de Tórax</option>
                    <option value="Drenos Abdominais">Drenos Abdominais</option>
                    <option value="Outros Drenos">Outros Drenos</option>
                </select>
            </div>
            <div class="hidden valor-drenado-container">
                <label for="valorDrenado">Valor Drenado (ml):</label>
                <input type="number" name="valorDrenado[]" placeholder="Insira o valor drenado">
            </div>
            <div>
                <button type="button" class="remove-btn">Remover</button>
            </div>
        `;

        // Listener para mostrar/ocultar o valor drenado
        const tipoSondaDropdown = entry.querySelector('.tipo-sonda-dropdown');
        const valorDrenadoContainer = entry.querySelector('.valor-drenado-container');

        tipoSondaDropdown.addEventListener('change', function () {
            if (['Dreno de Torax', 'Drenos Abdominais', 'Outros Drenos'].includes(tipoSondaDropdown.value)) {
                valorDrenadoContainer.classList.remove('hidden');
            } else {
                valorDrenadoContainer.classList.add('hidden');
            }
        });

        // Listener para remover a entrada
        const removeButton = entry.querySelector('.remove-btn');
        removeButton.addEventListener('click', () => entry.remove());

        return entry;
    }

    // Adiciona uma nova entrada de sonda
    addSondaButton.addEventListener('click', function () {
        const newEntry = createSondaEntry();
        sondasContainer.appendChild(newEntry);
    });

    // Função para limpar o formulário
    clearButton.addEventListener('click', function () {
        if (confirm('Tem certeza de que deseja limpar o formulário?')) {
            form.reset(); // Reseta todos os campos do formulário para os valores padrão

            // Limpa campos calculados ou gerados dinamicamente
            sondasContainer.innerHTML = ''; // Remove todas as entradas de sondas
        }
    });

    // Adiciona uma entrada inicial de sonda
    const initialSondaEntry = createSondaEntry();
    sondasContainer.appendChild(initialSondaEntry);
});
</script>
</body>
</html>
