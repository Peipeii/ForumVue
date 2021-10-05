<template>
  <div class="container py-5">
    <div>
      <h1>{{ restaurant.name }}</h1>
      <span class="badge badge-secondary mt-1 mb-3">{{ restaurant.categoryName }}</span>
    </div>

    <hr />

    <ul>
      <li>評論數： {{ restaurant.commentsLength }}</li>
      <li>瀏覽次數： {{ restaurant.viewCounts }}</li>
    </ul>

    <button type="button" class="btn btn-link" @click="$router.back()">回上一頁</button>
  </div>
</template>

<script>
const dummyData = {
  "restaurant": {
    "id": 10,
    "name": "Ryder Hintz 588",
    "tel": "(590) 232-2052",
    "address": "188 Loraine Crescent",
    "opening_hours": "08:00",
    "description": "Corporis et tenetur inventore ipsam ex libero ab nihil cum. Aut molestias sed dignissimos repellendus et quam. Animi explicabo cupiditate accusamus cum eveniet facilis. Excepturi aut quo et nihil beatae praesentium ut et.",
    "image": "https://loremflickr.com/320/240/restaurant,food/?random=30.676668227125358",
    "viewCounts": 228,
    "createdAt": "2021-09-08T08:34:40.000Z",
    "updatedAt": "2021-09-30T10:30:16.000Z",
    "CategoryId": 5,
    "Category": {
      "id": 5,
      "name": "素食料理",
      "createdAt": "2021-09-08T08:34:40.000Z",
      "updatedAt": "2021-09-08T08:34:40.000Z"
    },
    "Comments": [
      {
        "id": 60,
        "text": "Nobis praesentium quibusdam vel sunt sit.",
        "UserId": 1,
        "RestaurantId": 10,
        "createdAt": "2021-09-08T08:34:40.000Z",
        "updatedAt": "2021-09-08T08:34:40.000Z",
        "User": {
          "id": 1,
          "name": "root",
          "email": "root@example.com",
          "password": "$2a$10$PM9K3ZslTQWzH3zTNX7JqOD9m5SmUR5eNfDRx6TV2Ujrbgr.7ie.a",
          "isAdmin": true,
          "image": null,
          "createdAt": "2021-09-08T08:34:40.000Z",
          "updatedAt": "2021-09-08T08:34:40.000Z"
        }
      },
      {
        "id": 491,
        "text": "bbbb",
        "UserId": 1,
        "RestaurantId": 10,
        "createdAt": "2021-09-10T10:18:16.000Z",
        "updatedAt": "2021-09-10T10:18:16.000Z",
        "User": {
          "id": 1,
          "name": "root",
          "email": "root@example.com",
          "password": "$2a$10$PM9K3ZslTQWzH3zTNX7JqOD9m5SmUR5eNfDRx6TV2Ujrbgr.7ie.a",
          "isAdmin": true,
          "image": null,
          "createdAt": "2021-09-08T08:34:40.000Z",
          "updatedAt": "2021-09-08T08:34:40.000Z"
        }
      },
      {
        "id": 641,
        "text": "sdafsdfsdcsxccv",
        "UserId": 1,
        "RestaurantId": 10,
        "createdAt": "2021-09-11T09:32:54.000Z",
        "updatedAt": "2021-09-11T09:32:54.000Z",
        "User": {
          "id": 1,
          "name": "root",
          "email": "root@example.com",
          "password": "$2a$10$PM9K3ZslTQWzH3zTNX7JqOD9m5SmUR5eNfDRx6TV2Ujrbgr.7ie.a",
          "isAdmin": true,
          "image": null,
          "createdAt": "2021-09-08T08:34:40.000Z",
          "updatedAt": "2021-09-08T08:34:40.000Z"
        }
      },
      {
        "id": 10,
        "text": "Voluptatem voluptatem consequuntur neque.",
        "UserId": 2,
        "RestaurantId": 10,
        "createdAt": "2021-09-08T08:34:40.000Z",
        "updatedAt": "2021-09-08T08:34:40.000Z",
        "User": {
          "id": 2,
          "name": "user1",
          "email": "user1@example.com",
          "password": "$2a$10$yVu0LNTtgpIx.ehwX6n/L.jJXKKnyE6AWdqsPdLV4.JvegiDZFtpK",
          "isAdmin": false,
          "image": null,
          "createdAt": "2021-09-08T08:34:40.000Z",
          "updatedAt": "2021-09-15T02:53:32.000Z"
        }
      },
      {
        "id": 110,
        "text": "Officiis delectus et et odio est quia rem.",
        "UserId": 2,
        "RestaurantId": 10,
        "createdAt": "2021-09-08T08:34:40.000Z",
        "updatedAt": "2021-09-08T08:34:40.000Z",
        "User": {
          "id": 2,
          "name": "user1",
          "email": "user1@example.com",
          "password": "$2a$10$yVu0LNTtgpIx.ehwX6n/L.jJXKKnyE6AWdqsPdLV4.JvegiDZFtpK",
          "isAdmin": false,
          "image": null,
          "createdAt": "2021-09-08T08:34:40.000Z",
          "updatedAt": "2021-09-15T02:53:32.000Z"
        }
      }
    ]
  }
}

export default {
  name: 'RestaurantDashboard',
  data () {
    return {
      retaurant: {
        id: -1,
        name: '',
        categoryName: '',
        commentsLength: 0,
        viewCounts: 0
      }
    }
  },
  created () {
    const { id: restaurantId } = this.$route.params
    this.fetchRestaurant(restaurantId)
  },
  methods: {
    fetchRestaurant (restaurantId) {
      console.log('id: ', restaurantId)
      const { name, Category, Comments, viewCounts } = dummyData.restaurant
      this.restaurant = {
        ...this.restaurant,
        id: restaurantId,
        name,
        categoryName: Category ? Category.name : '未分類',
        commentsLength: Comments.length,
        viewCounts
      }
    }
  }
}
</script>