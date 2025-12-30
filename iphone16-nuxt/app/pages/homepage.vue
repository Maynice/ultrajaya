<template>
  <div class="relative w-[393px] h-[852px] mx-auto overflow-hidden font-sfpro">

    <!-- BACKGROUND -->
    <img src="/images/test3.png" class="absolute inset-0 w-full h-full object-cover" />

    <!-- ================= CLOCK ================= -->
    <div class="absolute top-[10px] left-0 w-full text-center z-50">
      <div class="text-white/80 text-[14px] absolute top-[11px] left-[130px] drop-shadow">
        Tuesday, December 30
      </div>
      <div class="text-white text-[90px] font-bold tracking-tight drop-shadow-lg">
        08:43
      </div>
      
    </div>

    <!-- ================= PROFILE HEADER ================= -->
    <div
      class="absolute top-[150px] left-[29.5px] w-[334px] h-[90px]
             flex items-centr px-5
             rounded-[28px]
             backdrop-blur-2xl bg-white
             border border-white/60
             shadow-[0_6px_24px_rgba(0,0,0,0.08)]
             z-50"
    >
      <img src="/images/defaultprofile.png" class="absolute top-[17px] w-[56px] h-[56px] rounded-full" />
      <div class="ml-4">
        <div class="absolute top-[20px] left-[90px] text-blue-500 text-[17px] font-semibold">
          Raissa Henardianti Hanifa
        </div>
        <div class="absolute top-[45px] left-[90px] text-black/60 text-[13px]">
          Info Akun, Ubah Data, Logout
        </div>
      </div>
    </div>

    <!-- ================= FILE-STYLE SCROLL AREA ================= -->
    <div
      class="absolute top-[265px] left-0 w-full h-[430px]
             overflow-y-auto scrollbar-hide px-[30px]"
    >
      <div class="flex flex-col gap-6 pb-32">

        <!-- ===== EXISTING MENU: PENGAJUAN CUTI ===== -->
        <div class="relative h-[110px] cursor-pointer" @click="goPengajuanCuti">
          <div class="absolute inset-0 rounded-[20px]
              backdrop-blur-[1px] backdrop-saturate-125
              shadow-[0_10px_20px_rgba(0,0,0,0.12)]
              border border-white/30
              before:absolute before:inset-0 before:rounded-[20px]
              before:shadow-[inset_1px_1px_0_rgba(255,255,255,0.75)]
              after:absolute after:inset-0 after:rounded-[20px] after:bg-white/25"></div>

          <div class="relative z-10 h-full flex items-center justify-between px-6 text-white">
            <div class="text-[22px] font-semibold drop-shadow">Pengajuan Cuti</div>
            <svg class="w-7 h-7 text-white drop-shadow"
                 viewBox="0 0 24 24" fill="none" stroke="currentColor"
                 stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round">
              <rect x="3" y="4" width="18" height="17" rx="2"/>
              <line x1="8" y1="2" x2="8" y2="6"/>
              <line x1="16" y1="2" x2="16" y2="6"/>
              <line x1="3" y1="10" x2="21" y2="10"/>
            </svg>
          </div>
        </div>

        <!-- ===== EXISTING MENU: ISI ABSENSI ===== -->
        <div class="relative h-[110px] cursor-pointer" @click="goIsiAbsensi">
          <div class="absolute inset-0 rounded-[20px]
              backdrop-blur-[1px] backdrop-saturate-125
              shadow-[0_10px_20px_rgba(0,0,0,0.12)]
              border border-white/30
              before:absolute before:inset-0 before:rounded-[20px]
              before:shadow-[inset_1px_1px_0_rgba(255,255,255,0.75)]
              after:absolute after:inset-0 after:rounded-[20px] after:bg-white/25"></div>

          <div class="relative z-10 h-full flex items-center justify-between px-6 text-white">
            <div class="text-[22px] font-semibold drop-shadow">Isi Absensi</div>
            <svg class="w-7 h-7 text-white drop-shadow"
                 viewBox="0 0 24 24" fill="none" stroke="currentColor"
                 stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round">
              <path d="M12 20h9"/>
              <path d="M16.5 3.5a2.1 2.1 0 0 1 3 3L7 19l-4 1 1-4Z"/>
            </svg>
          </div>
        </div>

        <!-- ===== EXISTING MENU: RIWAYAT ABSENSI ===== -->
        <div class="relative h-[110px] cursor-pointer" @click="goRiwayatAbsensi">
          <div class="absolute inset-0 rounded-[20px]
              backdrop-blur-[1px] backdrop-saturate-125
              shadow-[0_10px_20px_rgba(0,0,0,0.12)]
              border border-white/30
              before:absolute before:inset-0 before:rounded-[20px]
              before:shadow-[inset_1px_1px_0_rgba(255,255,255,0.75)]
              after:absolute after:inset-0 after:rounded-[20px] after:bg-white/25"></div>

          <div class="relative z-10 h-full flex items-center justify-between px-6 text-white">
            <div class="text-[22px] font-semibold drop-shadow">Riwayat Absensi</div>
            <svg class="w-7 h-7 text-white drop-shadow"
                 viewBox="0 0 24 24" fill="none" stroke="currentColor"
                 stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round">
              <circle cx="12" cy="12" r="9"/>
              <path d="M12 7v5l3 3"/>
            </svg>
          </div>
        </div>

        <!-- ===== EXTRA DUMMY FILE MENUS ===== -->
        <div
          v-for="n in 15"
          :key="n"
          class="relative h-[110px]"
        >
          <div class="absolute inset-0 rounded-[20px]
              backdrop-blur-[1px] backdrop-saturate-125
              shadow-[0_10px_20px_rgba(0,0,0,0.12)]
              border border-white/30
              before:absolute before:inset-0 before:rounded-[20px]
              before:shadow-[inset_1px_1px_0_rgba(255,255,255,0.75)]
              after:absolute after:inset-0 after:rounded-[20px] after:bg-white/25"></div>

          <div class="relative z-10 h-full flex items-center justify-between px-6 text-white">
            <div class="text-[22px] font-semibold drop-shadow">
              Menu {{ n }}
            </div>
            <svg class="w-7 h-7 text-white drop-shadow"
                 viewBox="0 0 24 24" fill="none" stroke="currentColor"
                 stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round">
              <rect x="4" y="4" width="16" height="16" rx="3"/>
            </svg>
          </div>
        </div>

      </div>
    </div>

    <!-- LOGO -->
    <img src="/images/UJ-LOGO.png"
         class="absolute bottom-[30px] right-[20px] w-[71px] h-[66px]" />
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

.scrollbar-hide::-webkit-scrollbar {
  display: none;
}
.scrollbar-hide {
  -ms-overflow-style: none;
  scrollbar-width: none;
}
</style>
