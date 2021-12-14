<template lang="pug">
#app
  b-navbar(toggleable='lg' type='dark' variant='info')
    b-container
      b-navbar-brand(to='/') 番茄鐘
      b-navbar-toggle(target='nav-collapse')
      b-collapse#nav-collapse(is-nav)
        b-navbar-nav
          b-nav-item(to='/list') 清單
          b-nav-item(to='/settings') 設定
    //- keep-alive => 因為 setInterval 的關係，沒有的話換頁之後暫停鍵會消失，變開始鍵
  keep-alive
    router-view(v-if="$route.meta.keepAlive")
  router-view(v-if="!$route.meta.keepAlive")
</template>
