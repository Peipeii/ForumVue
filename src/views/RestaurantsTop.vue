<template>
  <div class="container py-5">
    <NavTabs />
    <h1 class="mt-5">人氣餐廳</h1>
    <hr />
    <div
      v-for="restaurant in restaurants"
      :key="restaurant.id"
      class="card mb-3"
      style="max-width: 540px; margin: auto;"
    >
      <div class="row no-gutters">
        <div class="col-md-4">
          <a href="#">
            <img class="card-img" :src="restaurant.image" />
          </a>
        </div>
        <div class="col-md-8">
          <div class="card-body">
            <h5 class="card-title">{{ restaurant.name }}</h5>
            <span class="badge badge-secondary">收藏數：{{ restaurant.FavoriteCount }}</span>
            <p class="card-text">{{ restaurant.description }}</p>
            <a href="#" class="btn btn-primary mr-2">Show</a>

            <button type="button" class="btn btn-danger mr-2" v-if="restaurant.isFavorited">移除最愛</button>
            <button type="button" class="btn btn-primary" v-else>加到最愛</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>


<script>
import NavTabs from './../components/NavTabs'

const dummyData = {
  "restaurants": [
    {
      "id": 141,
      "name": "Daniel",
      "tel": "",
      "address": "",
      "opening_hours": "",
      "description": "",
      "image": null,
      "viewCounts": 0,
      "createdAt": "2021-09-09T09:10:47.000Z",
      "updatedAt": "2021-09-09T09:10:47.000Z",
      "CategoryId": 0,
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
            "RestaurantId": 141,
            "createdAt": "2021-09-25T12:56:05.000Z",
            "updatedAt": "2021-09-25T12:56:05.000Z"
          }
        }
      ],
      "isFavorited": true,
      "FavoriteCount": 1
    },
    {
      "id": 12,
      "name": "Diana Schaefer",
      "tel": "(084) 787-1373 x725",
      "address": "2059 Ledner Inlet",
      "opening_hours": "08:00",
      "description": "In repellat voluptas aut non qui. Voluptatem et ar",
      "image": "https://loremflickr.com/320/240/restaurant,food/?random=64.54266428046233",
      "viewCounts": 7496,
      "createdAt": "2021-09-08T08:34:40.000Z",
      "updatedAt": "2021-09-16T07:30:13.000Z",
      "CategoryId": 1,
      "FavoritedUsers": [
        {
          "id": 2,
          "name": "user1",
          "email": "user1@example.com",
          "password": "$2a$10$yVu0LNTtgpIx.ehwX6n/L.jJXKKnyE6AWdqsPdLV4.JvegiDZFtpK",
          "isAdmin": false,
          "image": null,
          "createdAt": "2021-09-08T08:34:40.000Z",
          "updatedAt": "2021-09-15T02:53:32.000Z",
          "Favorite": {
            "UserId": 2,
            "RestaurantId": 12,
            "createdAt": "2021-09-15T04:22:59.000Z",
            "updatedAt": "2021-09-15T04:22:59.000Z"
          }
        }
      ],
      "isFavorited": false,
      "FavoriteCount": 1
    },
    {
      "id": 10,
      "name": "Ryder Hintz 588",
      "tel": "(590) 232-2052",
      "address": "188 Loraine Crescent",
      "opening_hours": "08:00",
      "description": "Corporis et tenetur inventore ipsam ex libero ab n",
      "image": "https://loremflickr.com/320/240/restaurant,food/?random=30.676668227125358",
      "viewCounts": 228,
      "createdAt": "2021-09-08T08:34:40.000Z",
      "updatedAt": "2021-09-30T10:30:16.000Z",
      "CategoryId": 5,
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
      "isFavorited": true,
      "FavoriteCount": 1
    },
    {
      "id": 191,
      "name": "Carter Howe",
      "tel": "12",
      "address": "12",
      "opening_hours": "14:01",
      "description": "Voluptates veritatis blanditiis ipsam. Tempora mol",
      "image": null,
      "viewCounts": 0,
      "createdAt": "2021-09-14T11:17:50.000Z",
      "updatedAt": "2021-09-27T07:12:03.000Z",
      "CategoryId": 2,
      "FavoritedUsers": [],
      "isFavorited": false,
      "FavoriteCount": 0
    },
    {
      "id": 181,
      "name": "新增測試2",
      "tel": "",
      "address": "",
      "opening_hours": "",
      "description": "123321123",
      "image": "https://i.imgur.com/2rEGDYA.jpeg",
      "viewCounts": 1,
      "createdAt": "2021-09-13T11:30:45.000Z",
      "updatedAt": "2021-09-27T07:10:56.000Z",
      "CategoryId": 7,
      "FavoritedUsers": [],
      "isFavorited": false,
      "FavoriteCount": 0
    },
    {
      "id": 161,
      "name": "曼谷6",
      "tel": "0223546789",
      "address": "台大對面",
      "opening_hours": "11:00",
      "description": "一間泰式料理",
      "image": "https://i.imgur.com/WPhKoIJ.jpeg",
      "viewCounts": 13,
      "createdAt": "2021-09-09T16:32:13.000Z",
      "updatedAt": "2021-09-13T11:58:55.000Z",
      "CategoryId": 3,
      "FavoritedUsers": [],
      "isFavorited": false,
      "FavoriteCount": 0
    },
    {
      "id": 131,
      "name": "Ricky",
      "tel": "",
      "address": "",
      "opening_hours": "",
      "description": "",
      "image": null,
      "viewCounts": 0,
      "createdAt": "2021-09-09T09:10:22.000Z",
      "updatedAt": "2021-09-09T09:10:22.000Z",
      "CategoryId": 0,
      "FavoritedUsers": [],
      "isFavorited": false,
      "FavoriteCount": 0
    },
    {
      "id": 121,
      "name": "HintzZzZzZz",
      "tel": "",
      "address": "",
      "opening_hours": "",
      "description": "",
      "image": null,
      "viewCounts": 0,
      "createdAt": "2021-09-09T09:00:39.000Z",
      "updatedAt": "2021-09-09T09:00:39.000Z",
      "CategoryId": 0,
      "FavoritedUsers": [],
      "isFavorited": false,
      "FavoriteCount": 0
    },
    {
      "id": 61,
      "name": "麥當勞",
      "tel": "1234",
      "address": "台北市",
      "opening_hours": "08:00",
      "description": "123",
      "image": null,
      "viewCounts": 0,
      "createdAt": "2021-09-08T16:48:19.000Z",
      "updatedAt": "2021-09-08T16:48:19.000Z",
      "CategoryId": 6,
      "FavoritedUsers": [],
      "isFavorited": false,
      "FavoriteCount": 0
    },
    {
      "id": 51,
      "name": "Reeds Cafe",
      "tel": "+886227903266",
      "address": "114台北市內湖區成功路三段146號",
      "opening_hours": "11:00",
      "description": "室內設計很棒！麵包及飲料也很有品質，怕冰塊太多的人可以事先告知店員去冰",
      "image": "https://i.imgur.com/16jIbQP.jpeg",
      "viewCounts": 7,
      "createdAt": "2021-09-08T09:24:01.000Z",
      "updatedAt": "2021-09-13T06:22:04.000Z",
      "CategoryId": 7,
      "FavoritedUsers": [],
      "isFavorited": false,
      "FavoriteCount": 0
    }
  ]
}

export default {
  components: {
    NavTabs
  },
  data () {
    return {
      restaurants: dummyData.restaurants
    }
  }
}
</script>