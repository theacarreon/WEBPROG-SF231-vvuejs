<template>
    <h1>Comments</h1>
<ul>
  <li v-for="comment in comments" :key="comment.id">
    {{ comment.name }}: {{ comment.comment }}
  </li>
</ul>

<p v-if="comments.length === 0">No comments yet.</p>

<!-- Debugging output -->
<pre>{{ comments }}</pre>
</template>

<script setup>
    import { ref, onMounted } from 'vue'
    import { supabase } from '../lib/supabaseClient'

    const comments = ref([])

async function getComments() {
  const { data, error } = await supabase.from("comments").select();

  if (error) {
    console.error("Error fetching comments:", error);
    return;
  }

  comments.value = data; // Update the comments array
}

    onMounted(() => {
    getComments()
    })

</script>


<style>
  #app > div {
    border: dashed black 1px;
    display: inline-block;
    margin: 10px;
    padding: 10px;
    background-color: lightyellow;
  }
</style>