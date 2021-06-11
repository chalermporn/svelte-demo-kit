<script context="module" lang="ts">
  import { enhance } from '$lib/form'
  import type { Load } from '@sveltejs/kit'

  // see https://kit.svelte.dev/docs#loading
  export const load: Load = async ({ fetch }) => {
    const res = await fetch('/todos.json')

    if (res.ok) {
      const todos = await res.json()

      return {
        props: { todos }
      }
    }

    const { message } = await res.json()

    return {
      error: new Error(message)
    }
  }

</script>

<script lang="ts">
  import { scale } from 'svelte/transition'
  import { flip } from 'svelte/animate'

  type Todo = {
    uid: string
    created_at: Date
    text: string
    done: boolean
  }

  export let todos: Todo[]

  async function patch(res: Response) {
    const todo = await res.json()

    todos = todos.map(t => {
      if (t.uid === todo.uid) return todo
      return t
    })
  }

</script>

<svelte:head>
  <title>Todosd</title>
</svelte:head>

<div>Todo</div>
