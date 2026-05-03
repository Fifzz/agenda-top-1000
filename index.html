<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Agenda Milpau 2k26</title>
    <style>
        :root {
            --bg: #ffffff;
            --text: #111111;
            --accent: #007aff;
            --gray: #f2f2f7;
            --border: #d2d2d7;
            --white: #ffffff;
        }

        @media (prefers-color-scheme: dark) {
            :root {
                --bg: #1c1c1e;
                --text: #ffffff;
                --accent: #0a84ff;
                --gray: #2c2c2e;
                --border: #38383a;
                --white: #1c1c1e;
            }
        }

        * { box-sizing: border-box; -webkit-tap-highlight-color: transparent; }
        body {
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
            background-color: var(--bg);
            color: var(--text);
            margin: 0;
            padding: 20px;
            display: flex;
            justify-content: center;
        }

        .container { width: 100%; max-width: 500px; }

        .header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
        }

        h1 { font-size: 24px; margin: 0; }

        .selectors { display: flex; gap: 10px; }
        select {
            padding: 8px;
            border-radius: 8px;
            border: 1px solid var(--border);
            background: var(--gray);
            color: var(--text);
            font-weight: 600;
        }

        /* Calendário */
        .calendar-card {
            background: var(--white);
            border: 1px solid var(--border);
            border-radius: 20px;
            padding: 15px;
            box-shadow: 0 4px 12px rgba(0,0,0,0.05);
            margin-bottom: 20px;
        }

        .weekdays {
            display: grid;
            grid-template-columns: repeat(7, 1fr);
            text-align: center;
            font-size: 12px;
            color: #8e8e93;
            margin-bottom: 10px;
            font-weight: bold;
        }

        .days-grid {
            display: grid;
            grid-template-columns: repeat(7, 1fr);
            gap: 8px;
        }

        .day {
            aspect-ratio: 1;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
            font-size: 16px;
            cursor: pointer;
            position: relative;
            transition: 0.2s;
        }

        .day:hover { background: var(--gray); }
        .day.selected { background: var(--accent) !important; color: white; font-weight: bold; }
        .day.has-event::after {
            content: '';
            position: absolute;
            bottom: 4px;
            width: 4px;
            height: 4px;
            background: #ff3b30;
            border-radius: 50%;
        }

        /* Área de Cadastro */
        .event-form {
            background: var(--gray);
            padding: 20px;
            border-radius: 20px;
            margin-bottom: 20px;
        }

        .form-title { font-weight: bold; margin-bottom: 10px; display: block; color: var(--accent); }
        
        input {
            width: 100%;
            padding: 12px;
            margin-bottom: 10px;
            border-radius: 10px;
            border: 1px solid var(--border);
            background: var(--white);
            color: var(--text);
            font-size: 16px;
        }

        .row { display: flex; gap: 10px; }
        
        button#addBtn {
            flex: 1;
            padding: 12px;
            background: var(--accent);
            color: white;
            border: none;
            border-radius: 10px;
            font-weight: bold;
            cursor: pointer;
        }

        /* Lista de Compromissos */
        .event-list { list-style: none; padding: 0; }
        .event-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px;
            background: var(--white);
            border: 1px solid var(--border);
            border-radius: 12px;
            margin-bottom: 8px;
        }

        .event-details b { color: var(--accent); margin-right: 10px; }
        .delete-btn { color: #ff3b30; font-size: 13px; font-weight: bold; cursor: pointer; }
    </style>
</head>
<body>

<div class="container">
    <div class="header">
        <h1>Agenda 2k26</h1>
        <div class="selectors">
            <select id="monthSelect"></select>
            <select id="yearSelect"></select>
        </div>
    </div>

    <div class="calendar-card">
        <div class="weekdays">
            <div>DOM</div><div>SEG</div><div>TER</div><div>QUA</div><div>QUI</div><div>SEX</div><div>SÁB</div>
        </div>
        <div id="daysGrid" class="days-grid"></div>
    </div>

    <div class="event-form">
        <span class="form-title" id="displayDate">Selecione um dia</span>
        <input type="text" id="taskInput" placeholder="O que vamos fazer?">
        <div class="row">
            <input type="time" id="timeInput">
            <button id="addBtn" onclick="saveEvent()">Salvar</button>
        </div>
    </div>

    <ul id="eventList" class="event-list"></ul>
</div>

<script>
    const daysGrid = document.getElementById('daysGrid');
    const monthSelect = document.getElementById('monthSelect');
    const yearSelect = document.getElementById('yearSelect');
    const displayDate = document.getElementById('displayDate');
    const eventList = document.getElementById('eventList');

    let selectedDate = new Date();
    const months = ["Janeiro", "Fevereiro", "Março", "Abril", "Maio", "Junho", "Julho", "Agosto", "Setembro", "Outubro", "Novembro", "Dezembro"];

    function init() {
        // Preencher Meses
        months.forEach((m, i) => {
            const opt = document.createElement('option');
            opt.value = i; opt.innerText = m;
            if(i === selectedDate.getMonth()) opt.selected = true;
            monthSelect.appendChild(opt);
        });

        // Preencher Anos
        for(let y = 2024; y <= 2030; y++) {
            const opt = document.createElement('option');
            opt.value = y; opt.innerText = y;
            if(y === selectedDate.getFullYear()) opt.selected = true;
            yearSelect.appendChild(opt);
        }

        renderCalendar();
        updateDisplay();
    }

    function renderCalendar() {
        daysGrid.innerHTML = '';
        const month = parseInt(monthSelect.value);
        const year = parseInt(yearSelect.value);
        
        const firstDay = new Date(year, month, 1).getDay();
        const daysInMonth = new Date(year, month + 1, 0).getDate();
        
        const events = JSON.parse(localStorage.getItem('agenda_milpau') || '{}');

        // Espaços vazios para alinhar o primeiro dia da semana
        for(let i = 0; i < firstDay; i++) {
            daysGrid.appendChild(document.createElement('div'));
        }

        // Criar os dias do mês
        for(let d = 1; d <= daysInMonth; d++) {
            const dayDiv = document.createElement('div');
            dayDiv.className = 'day';
            dayDiv.innerText = d;
            
            const dateKey = `${year}-${month}-${d}`;
            
            if(events[dateKey] && events[dateKey].length > 0) dayDiv.classList.add('has-event');
            
            // Marca o dia selecionado
            if(d === selectedDate.getDate() && month === selectedDate.getMonth() && year === selectedDate.getFullYear()) {
                dayDiv.classList.add('selected');
            }

            dayDiv.onclick = () => {
                selectedDate = new Date(year, month, d);
                renderCalendar();
                updateDisplay();
            };
            daysGrid.appendChild(dayDiv);
        }
    }

    function updateDisplay() {
        const d = selectedDate.getDate();
        const m = months[selectedDate.getMonth()];
        const y = selectedDate.getFullYear();
        displayDate.innerText = `Agendar para: ${d} de ${m}`;
        renderEvents();
    }

    function saveEvent() {
        const task = document.getElementById('taskInput').value;
        const time = document.getElementById('timeInput').value;
        if(!task || !time) {
            alert("Digite a tarefa e o horário!");
            return;
        }

        const dateKey = `${selectedDate.getFullYear()}-${selectedDate.getMonth()}-${selectedDate.getDate()}`;
        const events = JSON.parse(localStorage.getItem('agenda_milpau') || '{}');
        
        if(!events[dateKey]) events[dateKey] = [];
        events[dateKey].push({ id: Date.now(), task, time });
        
        // Ordena por horário
        events[dateKey].sort((a,b) => a.time.localeCompare(b.time));

        localStorage.setItem('agenda_milpau', JSON.stringify(events));
        document.getElementById('taskInput').value = '';
        renderCalendar();
        renderEvents();
    }

    function renderEvents() {
        eventList.innerHTML = '';
        const dateKey = `${selectedDate.getFullYear()}-${selectedDate.getMonth()}-${selectedDate.getDate()}`;
        const events = JSON.parse(localStorage.getItem('agenda_milpau') || '{}');
        
        if(events[dateKey] && events[dateKey].length > 0) {
            events[dateKey].forEach(ev => {
                const li = document.createElement('li');
                li.className = 'event-item';
                li.innerHTML = `
                    <div class="event-details"><b>${ev.time}</b> ${ev.task}</div>
                    <div class="delete-btn" onclick="deleteEvent(${ev.id})">Apagar</div>
                `;
                eventList.appendChild(li);
            });
        } else {
            eventList.innerHTML = '<p style="text-align:center; color:#8e8e93;">Nenhum compromisso neste dia.</p>';
        }
    }

    function deleteEvent(id) {
        const dateKey = `${selectedDate.getFullYear()}-${selectedDate.getMonth()}-${selectedDate.getDate()}`;
        let events = JSON.parse(localStorage.getItem('agenda_milpau') || '{}');
        events[dateKey] = events[dateKey].filter(e => e.id !== id);
        localStorage.setItem('agenda_milpau', JSON.stringify(events));
        renderCalendar();
        renderEvents();
    }

    monthSelect.onchange = renderCalendar;
    yearSelect.onchange = renderCalendar;

    init();
</script>

</body>
</html>
