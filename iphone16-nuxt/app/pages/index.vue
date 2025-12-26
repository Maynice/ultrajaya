<template>
  <div class="relative w-393px h-852px mx-auto" style="font-family: 'SF Pro', system-ui, sans-serif;">
    <!-- Background -->
      <img src="/images/backgroundsaturated.png" alt="Background" class="absolute top-[0px] left-[0px] w-394 h-852" />
    <div>
    <img src="/images/UJ-LOGO.png" alt="UJ Logo" class="absolute top-[572px] left-[32px] w-[85px] h-[78px] aspect-w-3" />
    <!-- Log In button -->
      <button @click="goLogin">
        <img src="/images/loginbuttonindex.png" alt="Log In" class="absolute top-[551px] left-[134px] w-[228px] h-[120px] aspect-w-3" />
      </button>
    </div>
  </div>
</template>


 <!-- masih ts belum js :( )-->
<script setup lang="ts">
import { useRouter } from 'vue-router'

const router = useRouter()
const goLogin = () => router.push('/login')
</script>
