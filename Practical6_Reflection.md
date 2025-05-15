# Practical 6 Reflection: Todo List with Zustand  

## Documentation  
### Concepts Applied  
1. **Zustand State Management**:  
   - Created a centralized store for state (`todos`) and actions (e.g., `addTodo`).  
   - Avoided prop drilling by directly accessing state in components.  

2. **Persistence Middleware**:  
   - Used `persist` to save todos to `localStorage` automatically.  

3. **Optimized Rendering**:  
   - Components subscribe only to necessary state (e.g., `TodoList` only watches `todos`).  

## Reflection  
### What I Learned  
- Zustand simplifies state management compared to Redux or Context API.  
- Middleware (like `persist`) can extend store functionality without complex code.  
- Selective state subscriptions reduce unnecessary re-renders.  

### Challenges & Solutions  
1. **Challenge: Persistence Not Working**  
   - **Issue**: Todos disappeared on page refresh.  
   - **Solution**: Added the `persist` middleware with a unique `name` key.  

2. **Challenge: TypeScript Errors**  
   - **Issue**: Props in `TodoItem` caused type warnings.  
   - **Solution**: Defined a `Todo` interface for type safety.  
   ```typescript
   interface Todo {
     id: number;
     text: string;
     completed: boolean;
   }
   ```

3. **Challenge: Stale State in Actions**
    - **Issue**: set function in actions didn’t update state immediately.
    - **Solution**: Used the functional form of set to ensure correctness:
    ```javascript
    set((state) => ({ todos: state.todos.filter(todo => !todo.completed) }))
    ```