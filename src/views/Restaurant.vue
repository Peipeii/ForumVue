<template>
  <div class="container py-5">
    <h1>餐廳描述頁</h1>
    <!-- 餐廳資訊頁 -->
    <RestaurantDetail :initial-restaurant="restaurant" />
    <hr />
    <!-- 餐廳評論 RestaurantComments -->
    <!-- 新增評論 CreateComment -->
  </div>
</template>

<script>
import RestaurantDetail from './../components/RestaurantDetail'

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
    "updatedAt": "2021-09-30T10:30:16.201Z",
    "CategoryId": 5,
    "Category": {
      "id": 5,
      "name": "素食料理",
      "createdAt": "2021-09-08T08:34:40.000Z",
      "updatedAt": "2021-09-08T08:34:40.000Z"
    },
    "FavoritedUsers": [
      {
        "id": 1,
        "name": "root",
        "email": "root@example.com",
        "password": "$2a$10$PM9K3ZslTQWzH3zTNX7JqOD9m5SmUR5eNfDRx6TV2Ujrbgr.7ie.a",
        "isAdmin": true,
        "image": null,
        "createdAt": "2021-09-08T08:34:40.000Z",
        "updatedAt": "2021-09-08T08:34:40.000Z",
        "Favorite": {
          "UserId": 1,
          "RestaurantId": 10,
          "createdAt": "2021-09-13T15:07:06.000Z",
          "updatedAt": "2021-09-13T15:07:06.000Z"
        }
      }
    ],
    "LikedUsers": [],
    "Comments": [
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
      }
    ]
  },
  "isFavorited": true,
  "isLiked": false
}

export default {
  components: {
    RestaurantDetail
  },
  data () {
    return {
      restaurant: {
        id: -1,
        name: '',
        tel: '',
        address: '',
        openingHours: '',
        description: '',
        image: '',
        categoryName: '',
        isFavorited: false,
        isLiked: false
      },
      restaurantComments: []
    }
  },
  created () {
    const { id } = this.$route.params
    this.fetchRestaurant(id)
  },
  methods: {
    fetchRestaurant (restaurantId) {
      console.log('id: ', restaurantId)
      const { restaurant, isFavorited, isLiked } = dummyData
      this.restaurant = {
        id: restaurant.id,
        name: restaurant.name,
        tel: restaurant.tel,
        address: restaurant.address,
        openingHours: restaurant.opening_hours,
        description: restaurant.description,
        image: restaurant.image,
        categoryName: restaurant.Category ? restaurant.Category.name : '未分類',
        isFavorited,
        isLiked,
      }
      this.restaurantComments = restaurant.Comments
    }
  }
}
</script>