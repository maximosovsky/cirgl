# Architecture — Cirgl (Cir.gl)

## Overview

Cirgl — визуализация связей через круги (circle packing). Настройка предприятия через функциональные связи людей. Импорт данных из Excel, интерактивный canvas с drag-and-drop.

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Framework | React 18 + TypeScript |
| Build | Create React App (react-scripts) |
| Canvas | Konva + react-konva |
| Circle Packing | @nivo/circle-packing |
| UI Components | MUI (Material UI) v5 |
| CSS | Emotion (@emotion/react, @emotion/styled) |
| BEM | bem-cn |
| Data Import | xlsx (SheetJS) |
| Colors | randomcolor |
| Images | use-image |

## Project Structure

```
src/
├── App.tsx                      # Root → MainLayout
├── App.css                      # App-level styles
├── index.tsx                    # Entry point
├── index.css                    # Global styles
├── mock/
│   └── mock.ts                  # Mock data for circles/users
├── pages/
│   ├── MainLayout.tsx           # Two-column layout: ListUsers + Canvas
│   ├── MainLayout.less          # Layout styles (LESS)
│   └── components/
│       ├── Canvas.tsx           # Konva Stage — interactive circle canvas
│       ├── Circle.tsx           # Individual circle element on canvas
│       └── ListUsers.tsx        # Sidebar user list
├── types/
│   └── types.ts                 # TypeScript interfaces
├── App.test.tsx                 # Tests
├── setupTests.ts                # Test setup
├── reportWebVitals.ts           # Performance metrics
└── react-app-env.d.ts           # CRA type declarations
```

## UI Layout

```
┌──────────────┬─────────────────────────────────┐
│  ListUsers   │           Canvas                │
│  (sidebar)   │    (Konva interactive area)      │
│  xs=2,       │    80% window width              │
│  minW=300px  │    Full window height             │
└──────────────┴─────────────────────────────────┘
```

## Key Concepts

- **Circle Packing** — вложенные круги (Nivo) для визуализации иерархий
- **Konva Canvas** — интерактивное перетаскивание кругов
- **xlsx Import** — загрузка данных из Excel-файлов
- **Mock data** — демо-данные в `mock/mock.ts`
