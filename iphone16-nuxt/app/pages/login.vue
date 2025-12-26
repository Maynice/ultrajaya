<template>
  <div class="relative w-[393px] h-[852px] mx-auto overflow-hidden font-sfpro">
    <img src="/images/backgroundsaturated.png" alt="Background" class="w-[393px] h-[852px]" />
    
    <img src="/images/UJ-LOGO.png" alt="UJ Logo" class="absolute top-[120px] left-[164px] w-[71px] h-[66px] object-cover" />
    
    <img src="/images/loginwhitetab.png" alt="white tab" class="absolute top-[209px] left-[36px] w-[320px] h-[107px]" />
    
    <img src="/images/loginglasstransparant.png" alt="Glass Overlay" class="absolute top-[259px] left-[31px] w-[330px] h-[308px]" />

    <div>
        <label class="absolute top-[285px] left-[62px] text-gray-800 text-[17px] font-light">Username</label>
        <input
          type="text"
          placeholder="insert username here..."
          class="absolute top-[316px] left-[57px] w-[278px] h-[41px] rounded-[11px] bg-stone-50/50 backdrop-blur-sm px-3 text-[12px] font-thin text-gray-800 border border-white/30"
        />
      </div>

      <div>
        <label class="absolute top-[365px] left-[62px] text-gray-800 text-[17px] font-light">Password</label>
        <input
          type="password"
          placeholder="insert password here..."
          class="absolute top-[397px] left-[57px] w-[278px] h-[41px] rounded-[11px] bg-stone-50/50 backdrop-blur-sm px-3 text-[12px] font-thin text-gray-800 border border-white/30"
        />
      </div>

      <button @click="handleLogin"
        class="absolute top-[450px] left-[57px] w-[278px] h-[40px] bg-white rounded-[11px] flex items-center justify-center text-[#0088FF] font-normal text-[17px] leading-[20px] font-sans"
      >
        Log In
      </button>

      <div>
        <button class="absolute top-[524px] left-[60px] text-white text-[10px] font-semibold underline">Forgot Password</button>
        <button class="absolute top-[524px] left-[260px] text-white text-[10px] font-semibold underline">Sign Up Instead</button>
      </div>

  </div>
</template>

<script setup lang="ts">
import { useRouter } from 'vue-router'
const router = useRouter()
const handleLogin = () => {
  router.push('/homepage')
}
</script>