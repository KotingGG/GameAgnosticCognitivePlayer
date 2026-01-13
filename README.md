# Game-Agnostic Cognitive Player
[Main project document in Russian + roadmap](https://docs.google.com/document/d/1EvqQ1nDP_K-V4drSLzz3AxfX93gLw4JFqVFeqKXyCfk/edit?tab=t.0#heading=h.gjdgxs) (move everything from there to here)

[Русская версия](README.md) | [English Version](README_en.md)

![Python Version](https://img.shields.io/badge/python-3.13%252B-blue.svg) ![uv](https://img.shields.io/badge/uv-ready-5A45FF.svg) ![License](https://img.shields.io/badge/license-MIT-black.svg)

**Game-Agnostic Cognitive Player (GACP)** – это архитектура автономного LLM-агента для видеоигр, построенная с использованием **LangGraph**. Агент учится играть с чистого листа, не зная правил, путём наблюдения, формирования внутренней модели мира и экспериментов, демонстрируя переносимое между разными играми когнитивное развитие и способность к интроспективному общению.

## ✨ Особенности
todo: заполни


## 🚀 Быстрый старт
**Предварительные требования**
- Python 3.13+
- uv (рекомендуется для управления Python-пакетами)

### Установка и запуск

**Клонируйте и настройте проект:**
```bash
git clone https://github.com/KotingGG/GameAgnosticCognitivePlayer.git
cd GameAgnosticCognitivePlayer
```

**Установите зависимости:**
```bash
# Установите uv, если нужно
curl -LsSf https://astral.sh/uv/install.sh | sh
uv sync
```

todo: заполни.

**Запустите проект:**
todo: заполни.

## 🎮 Как это работает
todo: заполни

## Архитектура AI-агента
todo: заполни

```mermaid
graph TB
    subgraph "COGNITIVE CORE (Game-Agnostic)"
        B["Perception Module"]
        C["Memory System"]
        D["World Model"]
        E["Decision Module"]
        F["Action Module"]
        
        B -->|"observation JSON"| C
        C -->|"context + history"| D
        D -->|"predictions + explanations"| E
        E -->|"action_abstract JSON"| F
    end
    
    A["Game Environment<br/>(NetHack / Factorio)"]
    A -->|"Raw data<br/>pixels / audio"| B
    F -->|"keyboard / mouse<br/>signals"| A
    
    subgraph "Perception Module"
        B1["Data Capture Layer"]
        B2["Configurable Interpreter"]
        B1 --> B2
        B2 -.-> B
    end
    
    subgraph "Memory System"
        C1["Episodic Buffer"]
        C2["Vector Database"]
        C3["Knowledge Graph"]
        C1 --> C2 --> C3
        C3 -.-> C
    end
    
    subgraph "World Model"
        D1["State Prediction"]
        D2["Abductive Inference"]
        D3["Query Processor"]
        D1 --> D2
        D2 -.-> D
        D3 -.-> D
    end
    
    subgraph "Decision Module"
        E1["Goal Manager"]
        E2["Planner"]
        E3["Action Selector"]
        E1 --> E2 --> E3
        E3 -.-> E
    end
    
    subgraph "Action Module"
        F1["Action Executor"]
        F2["Low-Level Controller"]
        F1 --> F2
        F2 -.-> F
    end
    
    U["User / Operator"]:::external
    
    subgraph "Introspection & Communication Layer"
        G["Introspection Module<br/>(State Analyzer + Dialogue Agent)"]
    end
    
    H["TTS / Chat Interface"]:::utility
    
    C -.->|"① live memory stream"| G
    
    U -->|"② query/command"| G
    G -->|"③ formulated query +<br/>memory context"| D3
    D3 -->|"④ reasoned response"| G
    
    G -->|"⑤ text response"| H
    H --> U
    
    D -->|"predictions"| E
    
    C -.->|"hypothesis validation"| B2
    D -.->|"recalibration"| B2
    C3 -.->|"transferable knowledge"| D
    C1 -.->|"immediate learning"| E2
    
    class A external
    class B,C,D,E,F coreModule
    class B1,B2,F1,F2 adapter
    class C1,C2,C3,D1,D2,D3,E1,E2,E3 subComponent
    class G introspection
    class H utility
    class U user
```

## ⚙️ Конфигурация
todo: заполни

## 📊 Метрики и оценка
todo: заполни

## 🛠️ Разработка

### Структура проекта
text
```
LieGraph/
├── src/
│   ├── gacp/
│   │   ├── cognitive_core/          # 
│   │   ├── environments/            # 
│   │   ├── interfaces/              # 
│   │   ├── modules/                 #
│   │   │   ├── action/              #
│   │   │   ├── decision/            #
│   │   │   ├── introspection/       #
│   │   │   ├── memory/              #
│   │   │   ├── perception/          #
│   │   │   ├── world_model/         #
│   │   │   ├── base_module.py       #
│   │   └── main.py                  # 
├── tests/                           # 
├── configs/
│   ├── games/                       #
│   └── prompts/                     #
└── docs/                            # 

```
### Архитектура системы
Подробная информация об архитектуре, дизайне компонентов и паттернах интеграции находится в [ARCHITECTURE.md](ARCHITECTURE.md).

### Запуск тестов
todo: заполни

## 📄 Лицензия
Этот проект лицензирован под лицензией MIT — подробности смотрите в файле [LICENSE](LICENSE).
