<template>
	<div class="col-large push-top">
      <h1>{{thread.title}}</h1>

      <PostList :posts="posts" />

      <form @submit.prevent="addPost">
        <div class="form-group">
          <textarea 
            cols="30" 
            rows="10" 
            class="form-input"
            v-model="postListText"
          ></textarea>
        </div>

        <div class="form-actions">
          <button class="btn-blue">Submit post</button>
        </div>
      </form>
    </div>
</template>

<script>
import sourceData from '@/data'
import PostList from '@/components/PostList'

export default {
  props: {
    id: {
      required: true,
      type: String
    }
  },
  components: {
    PostList
  },
  data () {
    return {
      thread: sourceData.threads[this.id],
      postListText: ''
    }
  },
  computed: {
    posts () {
      const postIds = Object.values(this.thread.posts)

      return Object.values(sourceData.posts)
        .filter(post => postIds.includes(post['.key']))
    }
  },
  methods: {
    addPost () {
      let postId = `greatPost${Math.random()}`

      let post = {
        text: this.postListText,
        publishedAt: Math.floor(Date.now() / 1000),
        threadId: this.id,
        userId: '7uVPJS9GHoftN58Z2MXCYDqmNAh2',
        '.key': postId
      }

      this.$set(sourceData.posts, postId, post)
      this.$set(this.thread.posts, postId, postId)
      this.$set(sourceData.users[post.userId].posts, postId, postId)

      console.log('here')

      this.postListText = ''
    }
  }
}
</script>