<template>
  <div class="container py-5">
    <div class="row text-center">
      <div class="col-3" v-for="user in users" :key="user.id">
        <router-link :to="{ name: 'user', params: { id: user.id }}">
          <img
            :src="user.image ? user.image : 'http://via.placeholder.com/300x300?text=No+Image'"
            width="140px"
            height="140px"
          />
        </router-link>
        <h2>{{user.name}}</h2>
        <span class="badge badge-secondary">追蹤人數：{{user.FollowerCount}}</span>
        <p class="mt-3">
          <button
            type="button"
            class="btn btn-danger"
            v-if="user.isFollowed"
            @click.stop.prevent="deleteFollow(user)"
          >取消追蹤</button>
          <button
            type="button"
            class="btn btn-primary"
            v-else
            @click.stop.prevent="addFollow(user)"
          >追蹤</button>
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    initialUsers: {
      type: Array,
      required: true
    }
  },
  data () {
    return {
      users: this.initialUsers,
    }
  },
  methods: {
    addFollow (user) {
      user.isFollowed = true
    },
    deleteFollow (user) {
      user.isFollowed = false
    }
  }
}
</script>