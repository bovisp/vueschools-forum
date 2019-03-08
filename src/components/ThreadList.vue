<template>
	<div class="thread-list">
    <h2 class="list-title">Threads</h2>

    <ThreadListItem 
      v-if="threads.length"
      v-for="thread in threads"
      :thread="thread"
      :key="thread['.key']"
    />
  </div>
</template>

<script>
import ThreadListItem from '@/components/ThreadListItem'

export default {
  props: {
    threads: {
      required: true,
      type: Array
    }
  },
  components: {
    ThreadListItem
  }
}
</script>