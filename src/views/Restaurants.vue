<template>
  <div class="container py-5">
    <!-- 使用 NavTabs 元件 -->
    <NavTabs />
    <!-- 餐廳類別標籤 -->
    <RestaurantsNavPills :categories="categories" />
    <div class="row">
      <!-- 餐廳卡片 -->
      <RestaurantCard
        v-for="restaurant in restaurants"
        :key="restaurant.id"
        :initial-restaurant="restaurant"
      />
    </div>
    <!-- 分頁標籤 -->
    <RestaurantPagination
      v-if="totalPage.length > 1"
      :current-page="currentPage"
      :total-page="totalPage"
      :category-id="categoryId"
      :previous-page="previousPage"
      :next-page="nextPage"
    />
  </div>
</template>

<script>
import NavTabs from './../components/NavTabs'
import RestaurantCard from './../components/RestaurantCard.vue'
import RestaurantsNavPills from './../components/RestaurantsNavPills.vue'
import RestaurantPagination from './../components/RestaurantsPagination.vue'

const dummyData = {
  "restaurants": [
    {
      "id": 10,
      "name": "Ryder Hintz 588",
      "tel": "(590) 232-2052",
      "address": "188 Loraine Crescent",
      "opening_hours": "08:00",
      "description": "Corporis et tenetur inventore ipsam ex libero ab n",
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
      },
      "isFavorited": true,
      "isLiked": false
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
      },
      "isFavorited": false,
      "isLiked": false
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
      "Category": {
        "id": 1,
        "name": "中式料理",
        "createdAt": "2021-09-08T08:34:40.000Z",
        "updatedAt": "2021-09-08T08:34:40.000Z"
      },
      "isFavorited": false,
      "isLiked": true
    },
    {
      "id": 13,
      "name": "Izabella Barrows",
      "tel": "692.671.8299 x416",
      "address": "45272 Jacey Stream",
      "opening_hours": "08:00",
      "description": "Et aut eius quae consequatur laborum soluta et.\nNi",
      "image": "https://loremflickr.com/320/240/restaurant,food/?random=29.28907805634793",
      "viewCounts": 4,
      "createdAt": "2021-09-08T08:34:40.000Z",
      "updatedAt": "2021-09-24T05:51:54.000Z",
      "CategoryId": 4,
      "Category": {
        "id": 4,
        "name": "墨西哥料理",
        "createdAt": "2021-09-08T08:34:40.000Z",
        "updatedAt": "2021-09-08T08:34:40.000Z"
      },
      "isFavorited": false,
      "isLiked": false
    },
    {
      "id": 14,
      "name": "Manuela Shanahan",
      "tel": "1-046-033-0874",
      "address": "1644 Lacy Fields",
      "opening_hours": "08:00",
      "description": "Inventore temporibus inventore architecto quia sed",
      "image": "https://loremflickr.com/320/240/restaurant,food/?random=21.157703558140327",
      "viewCounts": 10,
      "createdAt": "2021-09-08T08:34:40.000Z",
      "updatedAt": "2021-09-13T07:03:54.000Z",
      "CategoryId": 2,
      "Category": {
        "id": 2,
        "name": "日本料理",
        "createdAt": "2021-09-08T08:34:40.000Z",
        "updatedAt": "2021-09-08T08:34:40.000Z"
      },
      "isFavorited": false,
      "isLiked": false
    },
    {
      "id": 15,
      "name": "Leo Schuster",
      "tel": "289-295-4390 x352",
      "address": "67999 Heaven Circles",
      "opening_hours": "08:00",
      "description": "Dolor numquam ea eos quasi. Quia voluptas velit al",
      "image": "https://loremflickr.com/320/240/restaurant,food/?random=77.58862598258239",
      "viewCounts": 3,
      "createdAt": "2021-09-08T08:34:40.000Z",
      "updatedAt": "2021-09-13T07:11:51.000Z",
      "CategoryId": 2,
      "Category": {
        "id": 2,
        "name": "日本料理",
        "createdAt": "2021-09-08T08:34:40.000Z",
        "updatedAt": "2021-09-08T08:34:40.000Z"
      },
      "isFavorited": false,
      "isLiked": false
    },
    {
      "id": 16,
      "name": "Brandon Zboncak",
      "tel": "1-210-685-7689 x67279",
      "address": "62874 Maxie Springs",
      "opening_hours": "08:00",
      "description": "Dolorum omnis quidem omnis voluptatum omnis qui. S",
      "image": "https://loremflickr.com/320/240/restaurant,food/?random=58.08820774504386",
      "viewCounts": 1,
      "createdAt": "2021-09-08T08:34:40.000Z",
      "updatedAt": "2021-09-13T06:22:15.000Z",
      "CategoryId": 4,
      "Category": {
        "id": 4,
        "name": "墨西哥料理",
        "createdAt": "2021-09-08T08:34:40.000Z",
        "updatedAt": "2021-09-08T08:34:40.000Z"
      },
      "isFavorited": false,
      "isLiked": false
    },
    {
      "id": 17,
      "name": "Kimberly Raynor",
      "tel": "239-698-9774 x99353",
      "address": "22299 Thompson Ferry",
      "opening_hours": "08:00",
      "description": "Alias sapiente est repellat.\nIpsa in temporibus re",
      "image": "https://loremflickr.com/320/240/restaurant,food/?random=92.62853612461623",
      "viewCounts": 7,
      "createdAt": "2021-09-08T08:34:40.000Z",
      "updatedAt": "2021-09-13T06:14:48.000Z",
      "CategoryId": 4,
      "Category": {
        "id": 4,
        "name": "墨西哥料理",
        "createdAt": "2021-09-08T08:34:40.000Z",
        "updatedAt": "2021-09-08T08:34:40.000Z"
      },
      "isFavorited": false,
      "isLiked": false
    },
    {
      "id": 18,
      "name": "Concepcion Bode",
      "tel": "450-934-5004 x5179",
      "address": "57460 Rempel Square",
      "opening_hours": "08:00",
      "description": "Neque animi repellendus dolorem repellat et veniam",
      "image": "https://loremflickr.com/320/240/restaurant,food/?random=7.355597283564896",
      "viewCounts": 0,
      "createdAt": "2021-09-08T08:34:40.000Z",
      "updatedAt": "2021-09-08T08:34:40.000Z",
      "CategoryId": 4,
      "Category": {
        "id": 4,
        "name": "墨西哥料理",
        "createdAt": "2021-09-08T08:34:40.000Z",
        "updatedAt": "2021-09-08T08:34:40.000Z"
      },
      "isFavorited": false,
      "isLiked": false
    },
    {
      "id": 19,
      "name": "Eve Corkery",
      "tel": "633.665.7995 x7554",
      "address": "592 Farrell Forge",
      "opening_hours": "08:00",
      "description": "Et ut sed nesciunt quia aspernatur. Laborum ut aut",
      "image": "https://loremflickr.com/320/240/restaurant,food/?random=29.497026011014494",
      "viewCounts": 4,
      "createdAt": "2021-09-08T08:34:40.000Z",
      "updatedAt": "2021-09-12T15:21:18.000Z",
      "CategoryId": 1,
      "Category": {
        "id": 1,
        "name": "中式料理",
        "createdAt": "2021-09-08T08:34:40.000Z",
        "updatedAt": "2021-09-08T08:34:40.000Z"
      },
      "isFavorited": false,
      "isLiked": true
    }
  ],
  "categories": [
    {
      "id": 1,
      "name": "中式料理",
      "createdAt": "2021-09-08T08:34:40.000Z",
      "updatedAt": "2021-09-08T08:34:40.000Z"
    },
    {
      "id": 2,
      "name": "日本料理",
      "createdAt": "2021-09-08T08:34:40.000Z",
      "updatedAt": "2021-09-08T08:34:40.000Z"
    },
    {
      "id": 3,
      "name": "義大利料理",
      "createdAt": "2021-09-08T08:34:40.000Z",
      "updatedAt": "2021-09-08T08:34:40.000Z"
    },
    {
      "id": 4,
      "name": "墨西哥料理",
      "createdAt": "2021-09-08T08:34:40.000Z",
      "updatedAt": "2021-09-08T08:34:40.000Z"
    },
    {
      "id": 5,
      "name": "素食料理",
      "createdAt": "2021-09-08T08:34:40.000Z",
      "updatedAt": "2021-09-08T08:34:40.000Z"
    },
    {
      "id": 6,
      "name": "美式料理",
      "createdAt": "2021-09-08T08:34:40.000Z",
      "updatedAt": "2021-09-08T08:34:40.000Z"
    },
    {
      "id": 7,
      "name": "複合式料理",
      "createdAt": "2021-09-08T08:34:40.000Z",
      "updatedAt": "2021-09-08T08:34:40.000Z"
    },
    {
      "id": 61,
      "name": "宇宙料理",
      "createdAt": "2021-09-13T12:20:10.000Z",
      "updatedAt": "2021-09-15T03:06:25.000Z"
    }
  ],
  "categoryId": "",
  "page": 1,
  "totalPage": [
    1,
    2,
    3,
    4,
    5
  ],
  "prev": 1,
  "next": 2
}

export default {
  name: 'Restaurants',
  components: {
    NavTabs,
    RestaurantCard,
    RestaurantsNavPills,
    RestaurantPagination
  },
  data () {
    return {
      restaurants: [],
      categories: [],
      categoryId: -1,
      currentPage: 1,
      totalPage: [],
      previousPage: -1,
      nextPage: -1
    }
  },
  created () {
    console.log("fetchRestaurants")
    this.fetchRestaurants()
  },
  methods: {
    fetchRestaurants () {
      const {
        restaurants,
        categories,
        categoryId,
        page,
        totalPage,
        prev,
        next
      } = dummyData
      this.restaurants = restaurants
      this.categories = categories
      this.categoryId = categoryId
      this.currentPage = page
      this.totalPage = totalPage
      this.previousPage = prev
      this.nextPage = next
    }
  }
}
</script>