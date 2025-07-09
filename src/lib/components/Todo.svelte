<script>
  export let todo;
  export let onToggle;
  export let onDelete;
</script>

<div class="flex items-center justify-between p-2 mb-2 bg-base-200 rounded-lg shadow">
  <div class="flex items-center">
    <input
      type="checkbox"
      class="checkbox checkbox-primary mr-3"
      checked={todo.completed}
      on:change={() => onToggle(todo.id)}
    />
    <span class="text-lg {todo.completed ? 'line-through text-gray-500' : ''}">
      {todo.text}
    </span>
  </div>
  <button class="btn btn-ghost btn-circle" on:click={() => onDelete(todo.id)}>
    <svg
      xmlns="http://www.w3.org/2000/svg"
      class="h-6 w-6 text-error"
      fill="none"
      viewBox="0 0 24 24"
      stroke="currentColor"
    >
      <path
        stroke-linecap="round"
        stroke-linejoin="round"
        stroke-width="2"
        d="M19 7l-.867 12.142A2 2 0 0116.138 21H7.862a2 2 0 01-1.995-1.858L5 7m5 4v6m4-6v6m1-10V4a1 1 0 00-1-1h-4a1 1 0 00-1 1v3M4 7h16"
      />
    </svg>
  </button>
</div>
