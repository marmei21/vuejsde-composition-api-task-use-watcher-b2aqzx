# Vuejs.de - Composition API - Task: Use a watcher

1. Add a prop for the title. Add a minus sign to the property both as prefix and suffix before using it in the markup. Use a computed for this updating behaviour.
2. Show the user the length of the current todo item, i.e. TodoLength: {{ todoLength }}. It should reflect the length of the input value
3. Also add the current items count to your template, i.e. Items quantity: {{ itemsQuantity }}
4. Add an area under the todo list, where the individual todo entries are output concatenated (There are multiple ways to implement this, use a watcher here)
5. Add a prop for the initial input value
6. Show an alert if the current todo exceeds a length of 10 chars
