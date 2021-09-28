<template>
  <div class="container py-5">
    <NavTabs />
    <h1 class="mt-5">最新動態</h1>
    <hr />
    <div class="row">
      <div class="col-md-6">
        <h3>最新餐廳</h3>
        <NewestRestaurants :restaurants="restaurants" />
      </div>
      <div class="col-md-6">
        <h3>最新評論</h3>
        <NewestComments :comments="comments" />
      </div>
    </div>
  </div>
</template>

<script>
import NavTabs from './../components/NavTabs'
import NewestRestaurants from './../components/NewestRestaurants.vue'
import NewestComments from './../components/NewestComments.vue'

const dummyData = {
  "restaurants": [
    {
      "id": 191,
      "name": "Carter Howe",
      "tel": "12",
      "address": "12",
      "opening_hours": "14:01",
      "description": "12",
      "image": null,
      "viewCounts": 0,
      "createdAt": "2021-09-14T11:17:50.000Z",
      "updatedAt": "2021-09-14T11:17:50.000Z",
      "CategoryId": 2,
      "Category": {
        "id": 2,
        "name": "日本料理",
        "createdAt": "2021-09-08T08:34:40.000Z",
        "updatedAt": "2021-09-08T08:34:40.000Z"
      }
    },
    {
      "id": 181,
      "name": "TGI FRIDAYS",
      "tel": "",
      "address": "",
      "opening_hours": "",
      "description": "So apparently TGI Fridays started this mistletoe-drone thingy for the holiday season",
      "image": "https://imgur.com/gallery/ICiegQJ",
      "viewCounts": 0,
      "createdAt": "2021-09-13T11:30:45.000Z",
      "updatedAt": "2021-09-25T03:09:21.000Z",
      "CategoryId": 7,
      "Category": {
        "id": 7,
        "name": "美式料理",
        "createdAt": "2021-09-08T08:34:40.000Z",
        "updatedAt": "2021-09-08T08:34:40.000Z"
      }
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
      "Category": {
        "id": 3,
        "name": "義大利料理",
        "createdAt": "2021-09-08T08:34:40.000Z",
        "updatedAt": "2021-09-08T08:34:40.000Z"
      }
    },
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
      "Category": null
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
      "Category": null
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
      "Category": null
    },
    {
      "id": 61,
      "name": "McDonald's",
      "tel": "1234",
      "address": "台北市",
      "opening_hours": "08:00",
      "description": "123",
      "image": null,
      "viewCounts": 0,
      "createdAt": "2021-09-08T16:48:19.000Z",
      "updatedAt": "2021-09-08T16:48:19.000Z",
      "CategoryId": 6,
      "Category": {
        "id": 6,
        "name": "美式料理",
        "createdAt": "2021-09-08T08:34:40.000Z",
        "updatedAt": "2021-09-08T08:34:40.000Z"
      }
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
      "Category": {
        "id": 7,
        "name": "複合式料理",
        "createdAt": "2021-09-08T08:34:40.000Z",
        "updatedAt": "2021-09-08T08:34:40.000Z"
      }
    },
    {
      "id": 10,
      "name": "Ryder Hintz 588",
      "tel": "(590) 232-2052",
      "address": "188 Loraine Crescent",
      "opening_hours": "08:00",
      "description": "Corporis et tenetur inventore ipsam ex libero ab nihil cum. Aut molestias sed dignissimos repellendus et quam. Animi explicabo cupiditate accusamus cum eveniet facilis. Excepturi aut quo et nihil beatae praesentium ut et.",
      "image": "https://loremflickr.com/320/240/restaurant,food/?random=30.676668227125358",
      "viewCounts": 227,
      "createdAt": "2021-09-08T08:34:40.000Z",
      "updatedAt": "2021-09-25T19:48:11.000Z",
      "CategoryId": 5,
      "Category": {
        "id": 5,
        "name": "素食料理",
        "createdAt": "2021-09-08T08:34:40.000Z",
        "updatedAt": "2021-09-08T08:34:40.000Z"
      }
    },
    {
      "id": 11,
      "name": "Nat Altenwerth",
      "tel": "(781) 761-8520 x2731",
      "address": "803 Otho Fields",
      "opening_hours": "08:00",
      "description": "quisquam expedita magni",
      "image": "https://loremflickr.com/320/240/restaurant,food/?random=90.2625244386088",
      "viewCounts": 332,
      "createdAt": "2021-09-08T08:34:40.000Z",
      "updatedAt": "2021-09-24T05:50:50.000Z",
      "CategoryId": 2,
      "Category": {
        "id": 2,
        "name": "日本料理",
        "createdAt": "2021-09-08T08:34:40.000Z",
        "updatedAt": "2021-09-08T08:34:40.000Z"
      }
    }
  ],
  "comments": [
    {
      "id": 801,
      "text": "TEEEEEEEEEEEEEEEEEE",
      "UserId": 1,
      "RestaurantId": 26,
      "createdAt": "2021-09-18T09:44:41.000Z",
      "updatedAt": "2021-09-18T09:44:41.000Z",
      "User": {
        "id": 1,
        "name": "root",
        "email": "root@example.com",
        "password": "$2a$10$PM9K3ZslTQWzH3zTNX7JqOD9m5SmUR5eNfDRx6TV2Ujrbgr.7ie.a",
        "isAdmin": true,
        "image": null,
        "createdAt": "2021-09-08T08:34:40.000Z",
        "updatedAt": "2021-09-08T08:34:40.000Z"
      },
      "Restaurant": {
        "id": 26,
        "name": "Lily Champlin",
        "tel": "1-639-634-8228",
        "address": "98395 Dahlia Harbor",
        "opening_hours": "08:00",
        "description": "Dolores eius dolores maxime eaque ipsam. Culpa et facilis ea ipsam facere est. Et corrupti qui harum blanditiis aut molestiae rerum est eveniet. Ut sunt sit corporis iste molestiae et quia eum voluptatem. Autem commodi ullam inventore placeat quam ipsum.\n \rUt quae nihil dolore quod quos voluptas ex quia. Provident enim perferendis vitae. Eos error beatae quia. Nihil tenetur officia ipsum.\n \rRepudiandae voluptatem totam et. Eos atque ipsam excepturi quos sed eligendi eius dicta sint. Natus ex placeat molestias sequi ea et itaque minus optio. Quibusdam et architecto dolores aut quia et reprehenderit rem. Minima eos nostrum ea et aut voluptatibus delectus veniam suscipit. Quis qui quaerat eum dolorum doloribus repellendus.",
        "image": "https://loremflickr.com/320/240/restaurant,food/?random=46.13319532805094",
        "viewCounts": 20,
        "createdAt": "2021-09-08T08:34:40.000Z",
        "updatedAt": "2021-09-18T09:51:59.000Z",
        "CategoryId": 3
      }
    },
    {
      "id": 751,
      "text": "good",
      "UserId": 1,
      "RestaurantId": 26,
      "createdAt": "2021-09-12T15:20:27.000Z",
      "updatedAt": "2021-09-12T15:20:27.000Z",
      "User": {
        "id": 1,
        "name": "root",
        "email": "root@example.com",
        "password": "$2a$10$PM9K3ZslTQWzH3zTNX7JqOD9m5SmUR5eNfDRx6TV2Ujrbgr.7ie.a",
        "isAdmin": true,
        "image": null,
        "createdAt": "2021-09-08T08:34:40.000Z",
        "updatedAt": "2021-09-08T08:34:40.000Z"
      },
      "Restaurant": {
        "id": 26,
        "name": "Lily Champlin",
        "tel": "1-639-634-8228",
        "address": "98395 Dahlia Harbor",
        "opening_hours": "08:00",
        "description": "Dolores eius dolores maxime eaque ipsam. Culpa et facilis ea ipsam facere est. Et corrupti qui harum blanditiis aut molestiae rerum est eveniet. Ut sunt sit corporis iste molestiae et quia eum voluptatem. Autem commodi ullam inventore placeat quam ipsum.\n \rUt quae nihil dolore quod quos voluptas ex quia. Provident enim perferendis vitae. Eos error beatae quia. Nihil tenetur officia ipsum.\n \rRepudiandae voluptatem totam et. Eos atque ipsam excepturi quos sed eligendi eius dicta sint. Natus ex placeat molestias sequi ea et itaque minus optio. Quibusdam et architecto dolores aut quia et reprehenderit rem. Minima eos nostrum ea et aut voluptatibus delectus veniam suscipit. Quis qui quaerat eum dolorum doloribus repellendus.",
        "image": "https://loremflickr.com/320/240/restaurant,food/?random=46.13319532805094",
        "viewCounts": 20,
        "createdAt": "2021-09-08T08:34:40.000Z",
        "updatedAt": "2021-09-18T09:51:59.000Z",
        "CategoryId": 3
      }
    },
    {
      "id": 731,
      "text": "check",
      "UserId": 1,
      "RestaurantId": 38,
      "createdAt": "2021-09-12T13:54:50.000Z",
      "updatedAt": "2021-09-12T13:54:50.000Z",
      "User": {
        "id": 1,
        "name": "root",
        "email": "root@example.com",
        "password": "$2a$10$PM9K3ZslTQWzH3zTNX7JqOD9m5SmUR5eNfDRx6TV2Ujrbgr.7ie.a",
        "isAdmin": true,
        "image": null,
        "createdAt": "2021-09-08T08:34:40.000Z",
        "updatedAt": "2021-09-08T08:34:40.000Z"
      },
      "Restaurant": {
        "id": 38,
        "name": "Armani Heller",
        "tel": "418-473-0081 x8178",
        "address": "775 Bosco Port",
        "opening_hours": "08:00",
        "description": "Architecto aut quia unde necessitatibus accusantium quibusdam necessitatibus. Et debitis ut maxime. Aspernatur ipsum possimus aut esse nihil aut accusamus ducimus. Eveniet ut aut veniam. Qui impedit possimus atque non.",
        "image": "https://loremflickr.com/320/240/restaurant,food/?random=34.27728373058103",
        "viewCounts": 20,
        "createdAt": "2021-09-08T08:34:40.000Z",
        "updatedAt": "2021-09-12T15:19:45.000Z",
        "CategoryId": 3
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
      },
      "Restaurant": {
        "id": 10,
        "name": "Ryder Hintz 588",
        "tel": "(590) 232-2052",
        "address": "188 Loraine Crescent",
        "opening_hours": "08:00",
        "description": "Corporis et tenetur inventore ipsam ex libero ab nihil cum. Aut molestias sed dignissimos repellendus et quam. Animi explicabo cupiditate accusamus cum eveniet facilis. Excepturi aut quo et nihil beatae praesentium ut et.",
        "image": "https://loremflickr.com/320/240/restaurant,food/?random=30.676668227125358",
        "viewCounts": 227,
        "createdAt": "2021-09-08T08:34:40.000Z",
        "updatedAt": "2021-09-25T19:48:11.000Z",
        "CategoryId": 5
      }
    },
    {
      "id": 601,
      "text": "4444",
      "UserId": 1,
      "RestaurantId": 12,
      "createdAt": "2021-09-10T10:39:58.000Z",
      "updatedAt": "2021-09-10T10:39:58.000Z",
      "User": {
        "id": 1,
        "name": "root",
        "email": "root@example.com",
        "password": "$2a$10$PM9K3ZslTQWzH3zTNX7JqOD9m5SmUR5eNfDRx6TV2Ujrbgr.7ie.a",
        "isAdmin": true,
        "image": null,
        "createdAt": "2021-09-08T08:34:40.000Z",
        "updatedAt": "2021-09-08T08:34:40.000Z"
      },
      "Restaurant": {
        "id": 12,
        "name": "Diana Schaefer",
        "tel": "(084) 787-1373 x725",
        "address": "2059 Ledner Inlet",
        "opening_hours": "08:00",
        "description": "In repellat voluptas aut non qui. Voluptatem et architecto voluptas aliquid ut dolorem. Iusto doloribus dolores.",
        "image": "https://loremflickr.com/320/240/restaurant,food/?random=64.54266428046233",
        "viewCounts": 7496,
        "createdAt": "2021-09-08T08:34:40.000Z",
        "updatedAt": "2021-09-16T07:30:13.000Z",
        "CategoryId": 1
      }
    },
    {
      "id": 591,
      "text": "3333",
      "UserId": 1,
      "RestaurantId": 12,
      "createdAt": "2021-09-10T10:38:43.000Z",
      "updatedAt": "2021-09-10T10:38:43.000Z",
      "User": {
        "id": 1,
        "name": "root",
        "email": "root@example.com",
        "password": "$2a$10$PM9K3ZslTQWzH3zTNX7JqOD9m5SmUR5eNfDRx6TV2Ujrbgr.7ie.a",
        "isAdmin": true,
        "image": null,
        "createdAt": "2021-09-08T08:34:40.000Z",
        "updatedAt": "2021-09-08T08:34:40.000Z"
      },
      "Restaurant": {
        "id": 12,
        "name": "Diana Schaefer",
        "tel": "(084) 787-1373 x725",
        "address": "2059 Ledner Inlet",
        "opening_hours": "08:00",
        "description": "In repellat voluptas aut non qui. Voluptatem et architecto voluptas aliquid ut dolorem. Iusto doloribus dolores.",
        "image": "https://loremflickr.com/320/240/restaurant,food/?random=64.54266428046233",
        "viewCounts": 7496,
        "createdAt": "2021-09-08T08:34:40.000Z",
        "updatedAt": "2021-09-16T07:30:13.000Z",
        "CategoryId": 1
      }
    },
    {
      "id": 581,
      "text": "1212",
      "UserId": 1,
      "RestaurantId": 12,
      "createdAt": "2021-09-10T10:32:07.000Z",
      "updatedAt": "2021-09-10T10:32:07.000Z",
      "User": {
        "id": 1,
        "name": "root",
        "email": "root@example.com",
        "password": "$2a$10$PM9K3ZslTQWzH3zTNX7JqOD9m5SmUR5eNfDRx6TV2Ujrbgr.7ie.a",
        "isAdmin": true,
        "image": null,
        "createdAt": "2021-09-08T08:34:40.000Z",
        "updatedAt": "2021-09-08T08:34:40.000Z"
      },
      "Restaurant": {
        "id": 12,
        "name": "Diana Schaefer",
        "tel": "(084) 787-1373 x725",
        "address": "2059 Ledner Inlet",
        "opening_hours": "08:00",
        "description": "In repellat voluptas aut non qui. Voluptatem et architecto voluptas aliquid ut dolorem. Iusto doloribus dolores.",
        "image": "https://loremflickr.com/320/240/restaurant,food/?random=64.54266428046233",
        "viewCounts": 7496,
        "createdAt": "2021-09-08T08:34:40.000Z",
        "updatedAt": "2021-09-16T07:30:13.000Z",
        "CategoryId": 1
      }
    },
    {
      "id": 571,
      "text": "2121",
      "UserId": 1,
      "RestaurantId": 12,
      "createdAt": "2021-09-10T10:30:35.000Z",
      "updatedAt": "2021-09-10T10:30:35.000Z",
      "User": {
        "id": 1,
        "name": "root",
        "email": "root@example.com",
        "password": "$2a$10$PM9K3ZslTQWzH3zTNX7JqOD9m5SmUR5eNfDRx6TV2Ujrbgr.7ie.a",
        "isAdmin": true,
        "image": null,
        "createdAt": "2021-09-08T08:34:40.000Z",
        "updatedAt": "2021-09-08T08:34:40.000Z"
      },
      "Restaurant": {
        "id": 12,
        "name": "Diana Schaefer",
        "tel": "(084) 787-1373 x725",
        "address": "2059 Ledner Inlet",
        "opening_hours": "08:00",
        "description": "In repellat voluptas aut non qui. Voluptatem et architecto voluptas aliquid ut dolorem. Iusto doloribus dolores.",
        "image": "https://loremflickr.com/320/240/restaurant,food/?random=64.54266428046233",
        "viewCounts": 7496,
        "createdAt": "2021-09-08T08:34:40.000Z",
        "updatedAt": "2021-09-16T07:30:13.000Z",
        "CategoryId": 1
      }
    },
    {
      "id": 561,
      "text": "1212",
      "UserId": 1,
      "RestaurantId": 11,
      "createdAt": "2021-09-10T10:30:18.000Z",
      "updatedAt": "2021-09-10T10:30:18.000Z",
      "User": {
        "id": 1,
        "name": "root",
        "email": "root@example.com",
        "password": "$2a$10$PM9K3ZslTQWzH3zTNX7JqOD9m5SmUR5eNfDRx6TV2Ujrbgr.7ie.a",
        "isAdmin": true,
        "image": null,
        "createdAt": "2021-09-08T08:34:40.000Z",
        "updatedAt": "2021-09-08T08:34:40.000Z"
      },
      "Restaurant": {
        "id": 11,
        "name": "Nat Altenwerth",
        "tel": "(781) 761-8520 x2731",
        "address": "803 Otho Fields",
        "opening_hours": "08:00",
        "description": "quisquam expedita magni",
        "image": "https://loremflickr.com/320/240/restaurant,food/?random=90.2625244386088",
        "viewCounts": 332,
        "createdAt": "2021-09-08T08:34:40.000Z",
        "updatedAt": "2021-09-24T05:50:50.000Z",
        "CategoryId": 2
      }
    },
    {
      "id": 551,
      "text": "0000",
      "UserId": 1,
      "RestaurantId": 11,
      "createdAt": "2021-09-10T10:29:57.000Z",
      "updatedAt": "2021-09-10T10:29:57.000Z",
      "User": {
        "id": 1,
        "name": "root",
        "email": "root@example.com",
        "password": "$2a$10$PM9K3ZslTQWzH3zTNX7JqOD9m5SmUR5eNfDRx6TV2Ujrbgr.7ie.a",
        "isAdmin": true,
        "image": null,
        "createdAt": "2021-09-08T08:34:40.000Z",
        "updatedAt": "2021-09-08T08:34:40.000Z"
      },
      "Restaurant": {
        "id": 11,
        "name": "Nat Altenwerth",
        "tel": "(781) 761-8520 x2731",
        "address": "803 Otho Fields",
        "opening_hours": "08:00",
        "description": "quisquam expedita magni",
        "image": "https://loremflickr.com/320/240/restaurant,food/?random=90.2625244386088",
        "viewCounts": 332,
        "createdAt": "2021-09-08T08:34:40.000Z",
        "updatedAt": "2021-09-24T05:50:50.000Z",
        "CategoryId": 2
      }
    }
  ]
}

export default {
  components: {
    NavTabs,
    NewestRestaurants,
    NewestComments
  },
  data () {
    return {
      restaurants: [],
      comments: []
    }
  },
  created () {
    this.fetchFeeds()
  },
  methods: {
    fetchFeeds () {
      const { restaurants, comments } = dummyData
      this.restaurants = restaurants
      this.comments = comments.filter(comment => { comment.Restaurant && comment.text })  //若餐廳不存在則不顯示此評論
    }
  }
}
</script>