<template>
  <div class="relative w-[393px] h-[852px] mx-auto overflow-hidden font-sfpro">

    <!-- Background -->
    <img
      src="/images/test3it add.png"
      class="absolute top-[-50px] left-[0px] w-[393px] h-852px]"
    />

    <!-- Logo -->
    <img
      src="/images/UJ-LOGO.png"
      class="absolute top-[120px] left-[164px] w-[71px] h-[66px] z-30"
    />

    <!-- GLASS  -->
    <div
      class="absolute top-[259px] left-[35px] w-[321px] h-[308px]
             rounded-[15px] overflow-hidden
             bg-white/20
             backdrop-blur-md backdrop-saturate-125
             shadow-[0_6px_6px_rgba(0,0,0,0.2),0_0_20px_rgba(0,0,0,0.1)]
             border border-white/20
             before:absolute before:inset-0
             before:rounded-[15px]
             before:shadow-[inset_1px_1px_0_rgba(255,255,255,0.75),inset_0_0_5px_rgba(255,255,255,0.75)]
             before:pointer-events-none
             after:absolute after:inset-0
             after:rounded-[15px]
             after:bg-white/25
             after:pointer-events-none
             z-10">
    </div>

    <!-- White tab -->
    <div
  class="absolute top-[209px] left-[35px] w-[321px] h-[70px]
         bg-white rounded-[20px] z-5"
>
  <span class="absolute top-[5px] left-[125px] text-[22px] font-bold font-sfpro">
    Log In
  </span>
</div>

    <!-- Username -->
    <label
      class="absolute top-[285px] left-[62px] text-gray-800 text-[17px] font-light z-30">
      Username
    </label>
    <input
      type="text"
      placeholder="insert username here..."
      class="absolute top-[316px] left-[57px] w-[278px] h-[41px]
             rounded-[11px] bg-stone-50/60 backdrop-blur-sm
             px-3 text-[12px] text-gray-800 border border-white/30 z-30"
    />

    <!-- Password -->
    <label
      class="absolute top-[365px] left-[62px] text-gray-800 text-[17px] font-light z-30">
      Password
    </label>
    <input
      type="password"
      placeholder="insert password here..."
      class="absolute top-[397px] left-[57px] w-[278px] h-[41px]
             rounded-[11px] bg-stone-50/60 backdrop-blur-sm
             px-3 text-[12px] text-gray-800 border border-white/30 z-30"
    />

    <!-- Login button -->
    <button
      @click="handleLogin"
      class="absolute top-[460px] left-[57px] w-[278px] h-[40px]
             bg-white rounded-[11px]
             flex items-center justify-center
             text-[#0088FF] text-[17px] z-30">
      Log In
    </button>

    <!-- Links -->
    <button
      class="absolute top-[524px] left-[60px]
             text-white text-[10px] font-semibold underline z-30">
      Forgot Password
    </button>

    <button
      class="absolute top-[524px] left-[260px]
             text-white text-[10px] font-semibold underline z-30">
      Sign Up Instead
    </button>

  </div>
</template>

<script setup lang="ts">
import { useRouter } from 'vue-router'

const router = useRouter()
const handleLogin = () => {
  router.push('/homepage')
}
</script>
