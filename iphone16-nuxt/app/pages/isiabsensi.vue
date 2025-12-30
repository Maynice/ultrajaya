<template>
  <div class="relative w-[393px] h-[852px] mx-auto overflow-hidden font-sfpro ">
  <!-- Background images -->
    <img src="/images/test3.png" alt="Background" class="w-[393px] h-[852px]" />  
      <!-- HEADER -->
       <img 
      src="/images/headerisiabsensi.png" 
      alt="header" 
      class="absolute top-[134px] left-[30px] w-[331px] h-[106px] cursor-pointer"/>
      <!-- GLASS GRAY -->
      <div
      class="absolute top-[190px] left-[33px] w-[324px] h-[347px] rounded-[15px]
             backdrop-blur-[10px] backdrop-saturate-125
             shadow-[0_6px_6px_rgba(0,0,0,0.2),0_0_20px_rgba(0,0,0,0.1)]
             border border-white/30
             before:absolute before:inset-0
             before:rounded-[15px]
             before:shadow-[inset_1px_1px_0_rgba(255,255,255,0.75),inset_0_0_5px_rgba(255,255,255,0.75)]
             before:pointer-events-none
             after:absolute after:inset-0
             after:rounded-[15px]
             after:bg-white/25
             after:pointer-events-none"></div>
      
      <!-- INPUT ABSENSI -->
      <div>
        <label class="absolute top-[205px] left-[62px] text-gray-800 text-[17px] font-light">Tanggal</label>
       <!-- tanggal -->
  <input
    type="date"
    placeholder="pilih tanggal hari ini"
    class="absolute top-[240px] left-[62px] w-[270px] h-[41px] rounded-[11px] bg-stone-50/50 backdrop-blur-sm px-3 text-[12px] font-thin text-gray-800 border border-white/30"/>
      <!-- clock in -->
      
        <label class="absolute top-[293px] left-[62px] text-gray-800 text-[17px] font-light">Jam Masuk</label>
        <input
          type="time"
          placeholder="pilih jam masuk"
    class="absolute top-[330px] left-[62px] w-[270px] h-[41px] rounded-[11px] bg-stone-50/50 backdrop-blur-sm px-3 text-[12px] font-thin text-gray-800 border border-white/30"
        />
      <!-- clock out -->
      
        <label class="absolute top-[381px] left-[62px] text-gray-800 text-[17px] font-light">Jam Keluar</label>
        <input
          type="time"
          placeholder="pilih jam keluar"
    class="absolute top-[420px] left-[62px] w-[270px] h-[41px] rounded-[11px] bg-stone-50/50 backdrop-blur-sm px-3 text-[12px] font-thin text-gray-800 border border-white/30"
        />
      </div>

      <!-- SUBMIT BUTTON -->
       <button @click="handleSubmit"
  class="absolute top-[477px] left-[62px] w-[270px] h-[40px] bg-white rounded-[11px] flex items-center justify-center text-[#0088FF] font-normal text-[17px] leading-[20px] font-sans"
>
  Submit
</button>
    
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "BoxTailwindSimple",
  methods: {
    handleSubmit() {
      // Dummy submit handler
      console.log("Submit button clicked");

      // Optional: simple feedback
      alert("Absensi submitted (dummy action)");
    }
  }
});
</script>
