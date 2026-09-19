# Вячеслав Квочкин | AI Architect & Lead MAS Engineer

🚀 Full-Cycle AI-архитектор мультиагентных систем (MAS) и основатель ИТ-компании **Lotus Digital Agents**. Специализируюсь на проектировании децентрализованных "звездных" архитектур и отказоустойчивых автономных конвейеров (Action-oriented AI) корпоративного уровня. Более 10 лет в веб-разработке, последние 3 года — исключительно в сфере сквозной AI-автоматизации, Enterprise RAG и многоагентного взаимодействия. Перевожу искусственный интеллект из режима текстового «консультанта» в режим полностью автономного «исполнителя» бизнес-задач. ---

### 🛠 Профессиональный технологический стек

#### 🔹 Core & Languages
<p align="left">
  <img src="https://img.shields.io/badge/Python-3.11+-141923?style=for-the-badge&logo=python&logoColor=3776AB" /> <img src="https://img.shields.io/badge/JavaScript-ES6+-141923?style=for-the-badge&logo=javascript&logoColor=F7DF1E" /> <img src="https://img.shields.io/badge/SQL-Advanced--Optimization-141923?style=for-the-badge&logo=databricks&logoColor=4169E1" /> </p>

#### 🔹 AI & Multi-Agent Frameworks
<p align="left">
  <img src="https://img.shields.io/badge/LangGraph-MAS--Orchestration-141923?style=for-the-badge" /> <img src="https://img.shields.io/badge/LangChain-AI--Core-141923?style=for-the-badge" /> <img src="https://img.shields.io/badge/LlamaIndex-Data--Framework-141923?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Pydantic_v2-Strict--Validation-141923?style=for-the-badge&logo=pydantic&logoColor=E92063" />
</p>

#### 🔹 Local LLM & Inference Pool (On-Premise)
<p align="left">
  <img src="https://img.shields.io/badge/LLAMA_3.x-Secure--Models-141923?style=for-the-badge&logo=meta&logoColor=044AF4" />
  <img src="https://img.shields.io/badge/vLLM-High--Performance-141923?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Ollama-Local--Inference-141923?style=for-the-badge" />
</p>

#### 🔹 Orchestration & Infrastructure
<p align="left">
  <img src="https://img.shields.io/badge/n8n-Enterprise--Workflows-141923?style=for-the-badge&logo=n8n&logoColor=FF6C37" /> <img src="https://img.shields.io/badge/PostgreSQL-pgvector-141923?style=for-the-badge&logo=postgresql&logoColor=4169E1" /> <img src="https://img.shields.io/badge/Docker-Self--Hosted-141923?style=for-the-badge&logo=docker&logoColor=2496ED" />
</p>

#### 🔹 CRM & Omnichannel Integrations
<p align="left">
  <img src="https://img.shields.io/badge/Bitrix24-CRM--API-141923?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Telegram-Bot--Interface-141923?style=for-the-badge&logo=telegram&logoColor=26A5E4" /> <img src="https://img.shields.io/badge/WhatsApp-Business-141923?style=for-the-badge&logo=whatsapp&logoColor=25D366" /> <img src="https://img.shields.io/badge/VK--API-Communication-141923?style=for-the-badge&logo=vk&logoColor=0077FF" /> </p>

---

### 📐 Эталонная архитектура омниканального AI-отдела продаж полного цикла (MAS-AI-Sales)

В рамках проекта **MAS-AI-Sales** реализуется полностью автономный закрытый контур многоагентных систем, оркеструющих воронку продаж от первого касания в любом канале до автоматического закрытия сделки и выставления счета. Система развернута в защищенном локальном контуре (On-Premise) на базе российских стандартов безопасности данных.

```mermaid
%%{init: {
  'theme': 'base',
  'themeVariables': {
    'primaryColor': '#141923',
    'primaryTextColor': '#C9D1D9',
    'primaryBorderColor': '#30363D',
    'lineColor': '#58A6FF',
    'secondaryColor': '#1F242F',
    'tertiaryColor': '#0D1117'
  }
}}%%
graph TD
    %% Omnichannel Ingress
    subgraph Ingress [Омниканальный слой / Входные каналы]
        TG_WA([Клиенты: Telegram / WhatsApp / Web])
        Voice_SIP([Клиенты: Телефонный канал / SIP Trunk])
        Manager_Bot([Менеджеры: Telegram CRM Bot])
    end

    %% Orchestration
    subgraph Orchestration [Слой оркестрации и менеджмента состояний]
        N8N[n8n Enterprise / API Gateway / Очереди]
        LGraph{LangGraph Orchestrator / State Manager}
    end

    %% Multi-Agent System
    subgraph Agent_Core [Мультиагентный департамент продаж]
        QualAgent[Agent: Квалификация и Скоринг]
        SalesAgent[Agent: Чат-бот Продажник / Сheckout]
        VoiceAgent[Agent: Голосовой ИИ-оператор STT->LLM->TTS]
        KPAgent[Agent: Динамическая генерация КП]
        FinAgent[Agent: Выставление счетов и Скидки]
        CRMAgent[Agent: Интегратор Битрикс24]
    end

    %% Secure Infrastructure
    subgraph Secure_Contour [Локальный защищенный контур / On-Premise]
        LIndex[LlamaIndex / Advanced RAG Engine]
        VectorDB[(PostgreSQL + pgvector / База знаний)]
        LocalLLM[Local LLAMA 3.x / vLLM Inference]
    end

    %% Connections: Ingress to Orchestration
    TG_WA --> N8N
    Manager_Bot --> N8N
    Voice_SIP <--> VoiceAgent
    
    N8N <--> LGraph

    %% Connections: Orchestration to Agents
    LGraph --> QualAgent
    LGraph --> SalesAgent
    LGraph --> VoiceAgent
    LGraph --> KPAgent
    LGraph --> FinAgent
    LGraph --> CRMAgent

    %% Connections: Agents to Core & Systems
    Agent_Core <--> LIndex
    LIndex <--> VectorDB
    Agent_Core <--> LocalLLM
    CRMAgent <--> B24[(Корпоративная CRM Bitrix24)]

```

#### 🧩 Функциональные роли агентов внутри MAS:

* **Агент квалификации и скоринга:** Извлекает сущности (BANT-методология) из диалогов, определяет боли, бюджет и готовность к покупке, автоматически приоритизируя лид в CRM. * **Чат-бот Продажник (Sales-Agent):** Ведет клиента по воронке, обрабатывает сложные возражения, используя корпоративную базу знаний через **LlamaIndex RAG**, доводит до этапа сделки. * **Голосовой робот (Voice AI Agent):** Интегрирован с SIP-телефонией, осуществляет холодный/теплый обзвон, распознает речь (STT), генерирует ответ через локальную LLM с минимальной задержкой (Low-Latency Inference) и синтезирует естественный голос (TTS).
* **Агент генерации КП:** На основе данных квалификации автоматически собирает кастомное коммерческое предложение в PDF под конкретный запрос клиента и отправляет в чат. * **Финансовый агент:** Реализует триггерную логику отправки персональных скидок для догрева, генерирует платежные ссылки и автоматически выставляет счета через API платежных шлюзов.
* **CRM Bot (Битрикс24):** Синхронизирует состояния агентов с CRM, двигает карточки сделок, ставит задачи и мгновенно тегает живых менеджеров через Telegram-бот в случае необходимости перехвата диалога. #### 🛡 Технологический базис суверенного контура (Self-Hosted):

1. **LangGraph + n8n:** n8n выступает в роли масштабируемого API-шлюза для работы с вебхуками мессенджеров, CRM и генерации документов, а LangGraph управляет сложными циклическими графами, контекстом (State) и цепочками рассуждений агентов. 2. **Local LLAMA & vLLM:** Все вычисления производятся внутри компании. Модели семейства Llama развернуты на собственных GPU-серверах с использованием высокопроизводительного движка vLLM, что исключает отправку конфиденциальных данных клиентов за рубеж.
2. **LlamaIndex + PostgreSQL (pgvector):** Полноценная RAG-архитектура для мгновенного поиска по терабайтам внутренних регламентов, прайс-листов и технических документов. ---

### 📈 Избранные кейсы и подтвержденный бизнес-эффект

#### 🏛 Enterprise RAG-MAS проверки экспертизы | Холдинг «Ровер Групп»

* **Архитектура:** Мультиагентная RAG-система сквозного аудита нормативно-технической документации. * **Реализация:** Построен конвейер полного цикла: интеллектуальное извлечение данных из документов ➡️ векторизация ➡️ гибридный поиск по базе знаний ➡️ генерация объяснимых аргументированных ответов для аудиторов. * **Метрики:** Точность ответов системы **превысила средний уровень экспертов-оценщиков** компании по внутренним тестам, а время проверки кейсов сократилось в разы. #### 📊 NL2SQL BI-надстройка над корпоративными СУБД
* **Архитектура:** Главный агент-оркестратор на базе n8n принимает бизнес-запросы на естественном языке, транслирует их в валидный сложный SQL к базе данных и визуализирует результат. * **Реализация:** Автоматическая генерация аналитических графиков и диаграмм без участия человека. * **Метрики:** Снижение операционной нагрузки на команду аналитики за счет автоматизации 80% типовых отчетов для топ-менеджмента. ---

### 🎓 Образование и квалификация

* **Профильное высшее:** ФГБОУ ВО "Уфимский государственный нефтяной университет" — *09.03.03 Прикладная информатика*. * **Специализированное:** АНО ВПО "Университет Иннополис" — *Архитектор в области искусственного интеллекта*. * **Аналитическое:** МГТУ "Станкин" — *Аналитика — искусство управлять данными*. ---

### 📫 Контакты для связи

* **Email:** [data.guru@ya.ru]() / [app.data.guru@gmail.com]() * **Telegram:** [@dataguru_ai](https://t.me/dataguru_ai)
* **Статус:** Рассматриваю амбициозные Enterprise-предложения (уровень **Lead AI Architect / Team Lead MAS** в компаниях экосистемы **СБЕР**) и архитектурный консалтинг для крупного бизнеса.

---
