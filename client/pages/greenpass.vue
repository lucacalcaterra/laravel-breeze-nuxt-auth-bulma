<template>
  <section class="section">
    <div class="container">
      <h1 class="title">
        GreenPass
      </h1>

      <p v-if="user">
        Hi {{ user.name }}
      </p>
      <a href="#" @click.prevent="logout">Logout</a>
    </div>
  </section>
</template>

<script>
export default {
  name: 'GreenpassPage',
  auth: 'guest',
  data () {
    return {
      user: this.$auth.$state.user
    }
  },
  methods: {
    async logout () {
      await this.$auth.logout()
      this.$router.push('/login')
    }
  }
}
</script>
