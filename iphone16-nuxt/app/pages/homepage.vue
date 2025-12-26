<template>
  <div class="relative w-[393px] h-[852px] mx-auto overflow-hidden font-sfpro">
  <img src="/images/backgrounddull.png" alt="Background" class="w-[393px] h-[852px]" />
    <div class="absolute top-[-23px] left-[-89px] w-[584px] h-[875px] bg-gradient-to-b from-[#e2f9ff]/78 via-[#f6eaba]/40 to-[#1d206d]/50"></div>

    <img 
      src="/images/pengajuancutibtn.png" 
      alt="tombol cuti" 
      class="absolute top-[194px] left-[38px] w-[172px] h-[158px] cursor-pointer"
      @click="goPengajuanCuti"
    />

    <img 
      src="/images/isiabsensibtn.png" 
      alt="tombol isi absensi" 
      class="absolute top-[307px] left-[180px] w-[172px] h-[158px] cursor-pointer"
      @click="goIsiAbsensi"
    />

    <img 
      src="/images/riwayatabsensi.png" 
      alt="tombol riwayat" 
      class="absolute top-[403px] left-[38px] w-[172px] h-[158px] cursor-pointer"
      @click="goRiwayatAbsensi"
    />

    <div class="absolute top-[71px] left-[26px] w-[334px] h-[95px] rounded-[30px] bg-[rgba(249,249,249,0.85)]"></div>

    <div class="absolute top-[95px] left-[122px] flex flex-col items-start">
      <div class="text-[#0088FF] text-[17px]">Raissa Henardianti Hanifa</div>
      <p class="text-gray-700 text-[13px] mt-[-2px] w-[241px]">Info Akun, Ubah Data, Logout</p>
    </div>

    <img src="/images/defaultprofile.png" alt="tombol isi absensi" class="absolute top-[90px] left-[49px] w-[55px] h-[55px]" />

    <img src="/images/UJ-LOGO.png" alt="UJ Logo" class="absolute top-[549px] left-[284px] w-[71px] h-[66px]" />
  </div>
</template>

<script setup lang="ts">
import { useRouter } from 'vue-router'

const router = useRouter()

const goPengajuanCuti = () => {
  router.push('/pengajuancuti')
}

const goIsiAbsensi = () => {
  router.push('/isiabsensi')
}

const goRiwayatAbsensi = () => {
  router.push('/riwayatabsensi')
}
</script>