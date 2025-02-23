<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Round Matinal - UTI</title>
    <style>
    /* Previous CSS remains the same */

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
          <label for="dataIntubacao">Data de Intubação:</label>
          <input type="date" id="dataIntubacao" name="dataIntubacao">

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

      <!-- Trânsito Intestinal -->
      <section class="section">
        <h2>Trânsito Intestinal</h2>
        <label for="transitoIntestinal">Trânsito Intestinal:</label>
        <select id="transitoIntestinal" name="transitoIntestinal" required>
          <option value="" disabled selected>Selecione uma opção</option>
          <option value="Normal">Normal</option>
          <option value="Constipado">Constipado</option>
          <option value="Diarreia">Diarreia</option>
        </select>
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
</body>
</html>
