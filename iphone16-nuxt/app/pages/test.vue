<template>
  <div class="relative w-[393px] h-[852px] mx-auto overflow-hidden font-sfpro">

    <!-- BACKGROUND -->
    <img
      src="/images/test3.png"
      class="absolute inset-0 w-full h-full object-cover"
    />
   
<div class="absolute top-0 left-0 w-[393px] h-[852px]"></div>
    <!-- ================= PROFILE HEADER ================= -->
    <div
  class="absolute top-[71px] left-[29.5px] w-[334px] h-[90px] 
         flex items-center px-5
         rounded-[28px]
         backdrop-blur-2xl bg-white/90
         border border-white/40
         shadow-[0_4px_20px_rgba(0,0,0,0.06),0_1px_2px_rgba(0,0,0,0.04)]"
>
  <div class="relative flex-shrink-0">
    <img
      src="/images/defaultprofile.png"
      class="w-[56px] h-[56px] rounded-full object-cover"
    />
  </div>

  <div class="ml-4 flex flex-col justify-center">
    <div class="text-[#007AFF] text-[17px] font-semibold tracking-tight antialiased leading-tight">
      Raissa Henardianti Hanifa
    </div>
    <div class="text-gray-500 text-[13px] tracking-tight mt-0.5 opacity-80">
      Info Akun, Ubah Data, Logout
    </div>
  </div>
</div>
    <!-- ================= MENU: PENGAJUAN CUTI ================= -->
    <div
      class="absolute top-[194px] left-[38px] w-[172px] h-[158px]
             rounded-[28px] cursor-pointer"
      @click="goPengajuanCuti"
    >
<div
  class="absolute top-[0px] left-[0px] w-[172px] h-[158px] rounded-[15px]
        backdrop-blur-[1px] backdrop-saturate-125
         shadow-[0_6px_6px_rgba(0,0,0,0.1),0_0_20px_rgba(0,0,0,0.1)]
         border border-white/20
         before:absolute before:inset-0
         before:rounded-[15px]
         before:shadow-[inset_1px_1px_0_rgba(255,255,255,0.75),inset_0_0_5px_rgba(255,255,255,0.75)]
         before:pointer-events-none
         after:absolute after:inset-0
         after:rounded-[15px]
         after:bg-white/25
         after:pointer-events-none"
></div>

      <div class="relative z-10 h-full w-full flex flex-col items-center justify-center gap-3 text-white">
        <div
          class="text-[28px] font-semibold text-center leading-[1.1] tracking-tight
         antialiased drop-shadow-[0_2px_4px_rgba(0,0,0,0.25)]"
        >
          Pengajuan<br />Cuti
        </div>

        <svg class="w-9 h-9 drop-shadow-[0_2px_6px_rgba(0,0,0,0.35)]"
             viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5">
          <path d="M8 7V3m8 4V3M3 11h18M5 21h14a2 2 0 0 0 2-2V7H3v12a2 2 0 0 0 2 2z"/>
        </svg>
      </div>
    </div>

    <!-- ================= MENU: ISI ABSENSI ================= -->
    <div
      class="absolute top-[307px] left-[180px] w-[172px] h-[158px]
             rounded-[28px] cursor-pointer"
      @click="goIsiAbsensi"
    >

      <div
  class="absolute top-[0px] left-[0px] w-[172px] h-[158px] rounded-[15px]
        backdrop-blur-[2px] backdrop-saturate-125
         shadow-[0_6px_6px_rgba(0,0,0,0.1),0_0_20px_rgba(0,0,0,0.1)]
         border border-white/20
         before:absolute before:inset-0
         before:rounded-[15px]
         before:shadow-[inset_1px_1px_0_rgba(255,255,255,0.75),inset_0_0_5px_rgba(255,255,255,0.75)]
         before:pointer-events-none
         after:absolute after:inset-0
         after:rounded-[15px]
         after:bg-white/25
         after:pointer-events-none"
></div>

      <div class="relative z-10 h-full w-full flex flex-col items-center justify-center gap-3 text-white">
        <div
          class="text-[28px] font-semibold text-center leading-[1.1] tracking-tight
         antialiased drop-shadow-[0_2px_4px_rgba(0,0,0,0.25)]"
        >
          Isi<br />Absensi
        </div>

        <svg class="w-9 h-9 drop-shadow-[0_2px_6px_rgba(0,0,0,0.35)]"
             viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5">
          <path d="M12 20h9"/>
          <path d="M16.5 3.5a2.1 2.1 0 0 1 3 3L7 19l-4 1 1-4Z"/>
        </svg>
      </div>
    </div>

    <!-- ================= MENU: RIWAYAT ABSENSI ================= -->
    <div
      class="absolute top-[403px] left-[38px] w-[172px] h-[158px]
             rounded-[28px] cursor-pointer"
      @click="goRiwayatAbsensi"
    >
      <div
  class="absolute top-[0px] left-[0px] w-[172px] h-[158px] rounded-[15px]
        backdrop-blur-[1px] backdrop-saturate-125
         shadow-[0_6px_6px_rgba(0,0,0,0.1),0_0_20px_rgba(0,0,0,0.1)]
         
         border border-white/0
         before:absolute before:inset-0
         before:rounded-[15px]
         before:shadow-[inset_1px_1px_0_rgba(255,255,255,0.75),inset_0_0_5px_rgba(255,255,255,0.75)]
         before:pointer-events-none
         after:absolute after:inset-0
         after:rounded-[15px]
         after:bg-white/25
         after:pointer-events-none"
></div>

      <div class="relative z-10 h-full w-full flex flex-col items-center justify-center gap-3 text-white">
        <div
          class="text-[28px] font-semibold text-center leading-[1.1] tracking-tight
         antialiased drop-shadow-[0_2px_4px_rgba(0,0,0,0.25)]"
        >
          Riwayat<br />Absensi
        </div>

        <svg class="w-9 h-9 drop-shadow-[0_2px_6px_rgba(0,0,0,0.35)]"
             viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5">
          <path d="M3 3v5h5"/>
          <path d="M3.05 13A9 9 0 1 0 6 5.3"/>
          <path d="M12 7v5l4 2"/>
        </svg>
      </div>
    </div>

    <!-- LOGO -->
    <img
      src="/images/UJ-LOGO.png"
      class="absolute bottom-[30px] right-[20px] w-[71px] h-[66px]"
    />

  </div>
</template>

<script setup lang="ts">
import { useRouter } from "vue-router"

const router = useRouter()

const goPengajuanCuti = () => router.push("/pengajuancuti")
const goIsiAbsensi = () => router.push("/isiabsensi")
const goRiwayatAbsensi = () => router.push("/riwayatabsensi")
</script>

<style>
.font-sfpro {
  font-family:
    -apple-system,
    BlinkMacSystemFont,
    "SF Pro Display",
    "SF Pro Text",
    system-ui,
    sans-serif;
}
</style>
