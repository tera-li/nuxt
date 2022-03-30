<template>
  <div>
    <NuxtLogo />
    <nuxt-link to="/goods/child">demo</nuxt-link>
    <br />
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
  transitions: 'index',
  middleware(context) {
    console.log('middleware-page')
  },
  validate({ params, query }) {
    console.log('validate')
    return true
  },
  data() {
    return {
      posts: '',
      select: 2,
    }
  },
  fetch() {
    console.log('fetch')
    // const res = await fetch('https://api.nuxtjs.dev/posts')
    // return { posts: await res.json }
  },
  // async asyncData() {
  //   console.log('asyncData')
  //   const res = await fetch('https://api.nuxtjs.dev/posts')
  //   const data = await res.json()
  //   return { posts: data }
  // },
  beforeCreate() {
    console.log('beforeCreate')
  },
  created() {
    console.log('created')
  },
  beforeMount() {
    console.log('beforeMount')
  },
  mounted() {
    console.log('mounted')
    // this.getData()
  },
  methods: {
    handleChange(e) {
      console.log(e)
    },
  },
}
</script>
