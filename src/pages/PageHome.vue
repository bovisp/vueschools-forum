<template>
  <section class="col-full">
    <h1>Welcome to the Forum</h1>
    <ThreadList 
      v-if="threads.length"
      :threads="threads"
    />
  </section>
</template>

<script>
import sourceData from '@/data'
import ThreadList from '@/components/ThreadList'

export default {
  components: {
    ThreadList
  },
  data () {
    return {
      threads: Object.values(sourceData.threads),
      posts: sourceData.posts,
      users: sourceData.users
    }
  }
}
</script>