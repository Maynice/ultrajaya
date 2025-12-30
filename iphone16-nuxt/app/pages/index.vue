<template>
  <div class="relative w-393px h-852px mx-auto" style="font-family: 'SF Pro', system-ui, sans-serif;">
    <!-- Background -->
      <img src="/images/test.png" alt="Background" class="absolute top-[0px] left-[0px] w-394 h-852 saturate-150" />
    <div>
    <img src="/images/UJ-LOGO.png" alt="UJ Logo" class="absolute top-[222px] left-[32px] w-[85px] h-[78px] aspect-w-3" />
<!-- Log In button -->
      <button @click="goLogin">
    <div
      class="absolute top-[201px] left-[134px] w-[228px] h-[120px] rounded-[30px]
             overflow-hidden
             backdrop-blur-[2px] backdrop-saturate-150
             shadow-[0_6px_6px_rgba(0,0,0,0.2),0_0_20px_rgba(0,0,0,0.1)]
             border border-white/20
             before:absolute before:inset-0
             before:rounded-[30px]
             before:shadow-[inset_1px_1px_0_rgba(255,255,255,0.75),inset_0_0_5px_rgba(255,255,255,0.75)]
             before:pointer-events-none
             after:absolute after:inset-0
             after:rounded-[30px]
             after:bg-white/25
             after:pointer-events-none
             z-20
             
             justified-center"> 
            <p
      class="absolute top-[15px] left-[42px] text-[50px] text-white font-bold font-sfpro
         [text-shadow:0_4px_12px_rgba(0,0,0,0.35)]">Log In</p></div>
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
