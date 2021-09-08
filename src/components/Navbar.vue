<template>
  <nav class="navbar navbar-expand-lg fixed-top navbar-dark bg-white">
    <router-link
      class="navbar-brand text-danger"
      to="/"
    >
      Alpha discussion forum
    </router-link>
   
    
    
    <a 
      class="navbar-toggler text-danger pointer-link"
      data-toggle="collapse"
      data-target="#navbarSupportedContent"
      aria-controls="navbarSupportedContent"
      aria-expanded="false"
      aria-label="Toggle navigation">
      <span><font-awesome-icon icon="hamburger" size='lg'/></span>
    </a>
   
    <div
      id="navbarSupportedContent" 
      class="navbar-collapse collapse"
    >
      <div class="ml-auto d-flex align-items-center">
        <!-- is user is admin -->
        <router-link
          to="#" 
          class="text-danger mr-3"
        >
         管理員後台
       </router-link>

        <!-- is user is login -->
        <router-link
          to="#" 
          class="text-danger mr-3"
        > 
          使用者 您好
        </router-link>
        <button
          type="button" 
          class="btn btn-sm btn-outline-danger my-2 my-sm-0"
        >
          登出
        </button>
      </div>
    </div>
  </nav>
</template>

<style>
  .pointer-link {
      cursor: pointer;
  }
</style>