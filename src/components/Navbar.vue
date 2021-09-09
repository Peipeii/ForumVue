<template>
  <nav class="navbar navbar-expand-lg fixed-top navbar-dark bg-white">
    <router-link class="navbar-brand text-danger" to="/">Alpha discussion forum</router-link>
    <a
      class="navbar-toggler text-danger pointer-link"
      data-toggle="collapse"
      data-target="#navbarSupportedContent"
      aria-controls="navbarSupportedContent"
      aria-expanded="false"
      aria-label="Toggle navigation"
    >
      <span>
        <font-awesome-icon icon="hamburger" size="lg" />
      </span>
    </a>

    <div id="navbarSupportedContent" class="navbar-collapse collapse">
      <div class="ml-auto d-flex align-items-center">
        <!-- is user is admin -->
        <router-link to="#" class="text-dark mr-3" v-if="currentUser.isAdmin">管理員後台</router-link>
        <!-- is user is login -->
        <template v-if="isAuthenticated">
          <router-link to="#" class="text-dark mr-3">{{ currentUser.name || '使用者' }} 您好</router-link>
          <button type="button" class="btn btn-sm btn-outline-dark my-2 my-sm-0">登出</button>
        </template>
      </div>
    </div>
  </nav>
</template>

<script>
// seed data
const dummyUser = {
  currentUser: {
    id: 1,
    name: "管理者",
    email: "root@example.com",
    image: "https://i.pravatar.cc/300",
    isAdmin: true
  },
  isAuthenticated: true
}

export default {
  // Vue 會在沒有資料時使用此預設值
  data () {
    return {
      currentUser: {
        id: -1,
        name: "",
        email: "",
        image: "",
        isAdmin: false
      },
      isAuthenticated: false
    }
  },
  methods: {
    // 會向後端 API 拉取資料
    fetchUser () {
      this.currentUser = {
        ...this.currentUser,
        ...dummyUser.currentUser // 把 dummyUser 蓋過 currentUser, 在 key 值相同，後者會覆蓋前者的資料
      }
      this.isAuthenticated = dummyUser.isAuthenticated
    }
  },
  created () {
    console.log("fetchUser")
    this.fetchUser()
  }
}
</script>

<style>
.pointer-link {
  cursor: pointer;
}
</style>
