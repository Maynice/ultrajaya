<template>
  <!-- scroll entire page -->
  <div class="w-[393px] h-screen mx-auto overflow-y-auto overflow-x-hidden font-sfpro scrollbar-hide">
    
    <!-- INNER CONTENT -->
    <div class="relative w-[393px] min-h-[1200px]">

      <!-- BACKGROUND -->
      <div class="absolute inset-0 w-[393px] h-full">
        <img
          src="/images/backgrounddull.png"
          class="w-full h-full object-cover z-0"
        />
      </div>

      <!-- HEADER  -->
      <img
        src="/images/headerriwayatabsensi.png"
        class="absolute top-[64px] left-[30px] w-[331px] h-[106px] z-10"
      />

      <!-- TOP SECTION -->
      <div class="absolute w-[352.59px] h-[286.76px] left-[30.7px] top-[57.6px] z-20">

        <!-- LEFT CARD -->
      <div
  class="absolute top-[136px] left-[2px] w-[150px] h-[150px] rounded-[30px]"
  style="background-color: rgba(255, 255, 255, 0.85);"
      ></div>
        <div class="absolute top-[193px] left-[40px] w-[74px] h-[49px]
                    flex items-center justify-center
                    text-[#28cb34] text-[40px] font-bold">
          {{ totalClockIns }}
        </div>

        <div class="absolute top-[150px] left-[27px] w-[100px] h-[41px]
                    flex items-center justify-center text-center
                    text-[#1b1b1b] text-[17px] font-bold">
          Total Hari <br /> Masuk Kerja
        </div>

        <div class="absolute top-[246px] left-[42px] w-[69px] h-[20px]
                    flex items-center justify-center
                    text-[#1b1b1b] text-[17px] font-light">
          tahun ini
        </div>

        <!-- RIGHT CARD -->
        <div
  class="absolute top-[136px] left-[180px] w-[150px] h-[150px] rounded-[30px]"
  style="background-color: rgba(255, 255, 255, 0.85);"
      ></div>
        <div class="absolute top-[193px] left-[244px] w-[26px] h-[49px]
                    flex items-center justify-center
                    text-[#d3635d] text-[40px] font-bold">
          {{ declinedStatuses }}
        </div>

        <div class="absolute top-[150px] left-[215px] w-[85px] h-[41px]
                    flex items-center justify-center text-center
                    text-[#1b1b1b] text-[17px] font-bold">
          Penolakan <br /> Absensi
        </div>

        <div class="absolute top-[246px] left-[223px] w-[69px] h-[20px]
                    flex items-center justify-center
                    text-[#1b1b1b] text-[17px] font-light">
          tahun ini
        </div>

        <!-- GREETING -->
        <div class="absolute top-[25px] left-[27px] w-[133px] h-[37px]
                    flex items-center justify-center
                    text-white text-[30px] font-bold">
          Hi, {{ userName }}
        </div>

        <div class="absolute top-[68px] left-[26px] w-[268px] h-[20px]
                    flex items-center justify-center
                    text-white text-[17px] font-light">
          Berikut adalah riwayat absensimu
        </div>
      </div>

      <!-- RIWAYAT ABSENSI GLASS -->
      <div class="absolute top-[382px] left-[32px] w-[329px] h-[500px] z-20">

        <!-- Glass background with gradient border effect -->
        <div class="absolute inset-0 w-full h-full rounded-[30px] backdrop-blur-xl bg-white/30 shadow-2xl border border-white/50"></div>

        <!-- Scrollable entries container - INTERNAL SCROLL -->
        <div class="absolute inset-0 z-10">
          <div
            class="w-full h-full
                   px-[25px] py-[30px]
                   overflow-y-auto overscroll-contain scrollbar-hide"
          >
            <div class="flex flex-col gap-[30px]">
              <div
                v-for="(entry, index) in entries"
                :key="index"
                class="flex items-center justify-between"
              >
                <!-- Entry label -->
                <div
                  class="w-[132px] h-[57px]
                         flex items-center justify-center
                         text-black text-[20px] font-normal"
                >
                  {{ entry.label }}
                </div>

                <!-- Status badge -->
                <div
                  class="w-[113px] h-[48px] rounded-[12px]
                         flex items-center justify-center"
                  :class="statusStyle(entry.status).bg"
                >
                  <span class="text-white text-[20px] font-bold">
                    {{ statusStyle(entry.status).text }}
                  </span>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const userName = ref('User');
const totalClockIns = ref(42);
const declinedStatuses = ref(3);
const entries = ref([
  { label: '1/12/12', status: 'approved' },
  { label: '4/13/12', status: 'approved' },
  { label: '3/14/12', status: 'declined' },
  { label: '7/15/12', status: 'approved' },
  { label: '5/16/12', status: 'approved' },
  { label: '3/19/12', status: 'approved' },
  { label: '12/20/12', status: 'declined' },
  { label: '11/21/12', status: 'approved' },
  { label: '2/22/12', status: 'approved' },
  { label: '5/23/12', status: 'approved' },
]);

const statusStyle = (status) => {
  if (status === 'approved') {
    return {
      bg: 'bg-[#28cb34]',
      text: 'Approved'
    };
  } else {
    return {
      bg: 'bg-[#d3635d]',
      text: 'Declined'
    };
  }
};
</script>

<style scoped>
.font-sfpro {
  font-family: 'SF Pro', system-ui, sans-serif;
}

/* Hide scrollbar but keep functionality */
.scrollbar-hide::-webkit-scrollbar {
  display: none;
}
.scrollbar-hide {
  -ms-overflow-style: none;
  scrollbar-width: none;
}
</style>