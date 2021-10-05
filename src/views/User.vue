<template>
  <div class="container py-5">
    <UserProfileCard />
    <div class="row">
      <div class="col-md-4">
        <UserFollowingsCard />
        <br />
        <UserFollowersCard />
      </div>
      <div class="col-md-8">
        <UserCommentsCard />
        <br />
        <UserFavoritedRestaurantsCard />
      </div>
    </div>
  </div>
</template>

<script>
import UserProfileCard from './../components/UserProfileCard'
import UserFollowingsCard from './../components/UserFollowingsCard'
import UserFollowersCard from './../components/UserFollowersCard'
import UserCommentsCard from './../components/UserCommentsCard'
import UserFavoritedRestaurantsCard from './../components/UserFavoritedRestaurantsCard'

export default {
  name: 'User',
  components: {
    UserProfileCard,
    UserFollowingsCard,
    UserFollowersCard,
    UserCommentsCard,
    UserFavoritedRestaurantsCard
  }
}

</script>