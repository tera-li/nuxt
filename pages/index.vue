<template>
  <div>
    <NuxtLogo />
    <nuxt-link to="/views">demo</nuxt-link>
    <el-select v-model="select" @change="handleChange">
      <el-option
        v-for="item of posts"
        :key="item.id"
        :value="item.id"
        :label="item.title"
      ></el-option>
    </el-select>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  middleware: 'auth',
  data() {
    return {
      posts: '',
      select: 2,
    }
  },
  fetch() {
    fetch('https://api.nuxtjs.dev/posts')
      .then((res) => {
        return res.json()
      })
      .then((res) => {
        this.posts = res
      })
  },
  mounted() {
    // this.getData()
  },
  methods: {
    handleChange(e) {
      console.log(e)
    },
  },
}
</script>
