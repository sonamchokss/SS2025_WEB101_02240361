# Practical 6: Todo List Application with Zustand  

## Introduction  
This project demonstrates state management in React using **Zustand**, a lightweight state management library. It includes:  
- A functional Todo List with CRUD operations.  
- Persistence via `localStorage`.  
- Optimized re-renders with Zustand's selective state subscriptions.  

## Instructions  

### Project Setup  
1. **Create React App**:  
   ```bash
   npx create-vite@latest todo-zustand --template react
   cd todo-zustand
   npm install zustand
   ```

2. **Folder Structure:**
```
src/
├── components/
│   ├── TodoInput.jsx
│   ├── TodoItem.jsx
│   └── TodoList.jsx
├── store/
│   └── todoStore.js
├── App.js
└── index.js
```

### Key Steps
1. Zustand Store:
- Created in todoStore.js with state (todos) and actions (addTodo, toggleTodo, etc.).
- Added persist middleware for localStorage persistence.

2. Components:
- TodoInput: Form to add new todos.
- TodoItem: Displays a todo with toggle/delete options.
- TodoList: Renders all todos and a "Clear Completed" button.

3. App Integration:
- Combined all components in App.js with todo counters.

### Solution Code
#### todoStore.js (Persistence Enabled)
```javascript
import { create } from 'zustand';
import { persist } from 'zustand/middleware';

const useTodoStore = create(
  persist(
    (set) => ({
      todos: [],
      addTodo: (text) => set((state) => ({
        todos: [...state.todos, { id: Date.now(), text, completed: false }],
      })),
      // ... (other actions)
    }),
    { name: 'todo-storage' }
  )
);
```

#### TodoItem.jsx (Example Component)
```jsx
function TodoItem({ todo }) {
  const toggleTodo = useTodoStore((state) => state.toggleTodo);
  return (
    <li>
      <input 
        type="checkbox" 
        checked={todo.completed} 
        onChange={() => toggleTodo(todo.id)} 
      />
      <span style={{ textDecoration: todo.completed ? 'line-through' : 'none' }}>
        {todo.text}
      </span>
    </li>
  );
}
```