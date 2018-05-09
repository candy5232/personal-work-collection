<template>
  <div id="app">
      <div class="nav-box">
        <ul class="nav">
          <router-link to="/" exact tag="li" event="mouseover">
            <i class="fa fa-home"></i>
            <span>home</span>
          </router-link>
          <li>
            <router-link :to="{path:'/document'}" event="mouseover" active-class="activeClass">document</router-link>
          </li>
          <li>
            <router-link to="/about"  event="mouseover">about</router-link>
          </li>
          <li>
            <router-link to="/user"  event="mouseover">user</router-link>
          </li>
        </ul>
      </div>
    <transition name="left" mode="out-in">
      <router-view class="center"></router-view>
    </transition>

  </div>
</template>

<script>
export default {
  name: 'App',
  data(){
       return{
         index: '/home'
       }
  }
}
</script>

<style>
   .v-enter{
     opacity: 0;
   }
  .v-enter-to{
    opacity: 1;
  }
  .v-enter-active{
    transition: 1s;
  }
  .v-leave{
    opacity: 1;
  }
  .v-leave-to{
    opacity: 0;
  }
  .v-leave-active{
    transition: 2s;
  }

  .left-enter{
    transform: translateX(100%);
  }
   .left-enter-to{
     transform: translateX(0);
   }
   .left-enter-active, .left-leave-active{
     transition: 1s;
   }

   .left-enter-active{
     transition:1s;
   }
  .left-leave-to{
    transform: translateX(-100%);
  }

</style>
