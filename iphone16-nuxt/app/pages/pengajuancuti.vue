<script setup lang="ts">
import { ref, computed } from 'vue'

import { useRouter } from 'vue-router'
const router = useRouter()
const handlePengajuanCuti = () => {
  router.push('/homepage')
}

/* =========================
   DUMMY BACKEND DATA
   ========================= */
const backendSupervisors = ref([
  'Supervisor 1',
  'Supervisor 2',
])

/* =========================
   CONSTANTS
   ========================= */
const BASE_SUPERVISORS = 3
const ROW_HEIGHT = 28
const BASE_WHITE_HEIGHT = 91
const BASE_GLASS_HEIGHT = 252
const GLASS_TOP = 98
const GAP_BELOW_GLASS = 36
const FORM_IMAGE_HEIGHT = 400 // estimate for form image

/* =========================
   COMPUTED SIZES
   ========================= */
const extraRows = computed(() =>
  Math.max(0, backendSupervisors.value.length - BASE_SUPERVISORS)
)

const whiteBoxHeight = computed(() =>
  BASE_WHITE_HEIGHT + extraRows.value * ROW_HEIGHT
)

const glassHeight = computed(() =>
  BASE_GLASS_HEIGHT + extraRows.value * ROW_HEIGHT
)

/* Image below glass position */
const belowGlassTop = computed(() =>
  GLASS_TOP + glassHeight.value + GAP_BELOW_GLASS
)

/* Total container height */
const containerHeight = computed(() =>
  Math.max(1169, belowGlassTop.value + FORM_IMAGE_HEIGHT + 50)
)

/* Form positions relative to glass container */
const formBaseTop = computed(() => 0 + belowGlassTop.value + 55)

const showDatePicker = ref(false)
const selectedDates = ref<string[]>([])

const addDate = (event: Event) => {
  const target = event.target as HTMLInputElement
  const date = target.value
  if (date && !selectedDates.value.includes(date)) {
    selectedDates.value.push(date)
    selectedDates.value.sort()
  }
  target.value = ''
}

const removeDate = (date: string) => {
  selectedDates.value = selectedDates.value.filter(d => d !== date)
}

const formatDate = (dateStr: string) => {
  const date = new Date(dateStr)
  return date.toLocaleDateString('id-ID', { day: 'numeric', month: 'short', year: 'numeric' })
}

const confirmDates = () => {
  showDatePicker.value = false
  // You can add logic here to display selected dates in the input field
}
</script>

<template>
  <div class="relative w-[393px] min-h-[1169px] mx-auto font-sfpro">

    <img
      src="/images/backgroundlong.png"
      class="absolute top-0 left-0 w-[393px] h-full object-cover object-top"
    />

    <img
      src="/images/headerpengajuancuti.png"
      class="absolute top-[55.6px] left-[27px] w-[340px] h-[168px] z-10"
    />

    <!-- Text content -->
    <div class="absolute top-[55.6px] left-[29px] z-20 w-[336px]">
      <div class="absolute top-[19px] left-[25px] text-white text-[30px] font-bold whitespace-nowrap">
        Hi, User
      </div>

      <div class="absolute top-[58px] left-[25px] text-white text-[19px] font-light whitespace-nowrap">
        Gunakan sisa cuti dengan bijak!
      </div>

      <!-- Glass container -->
      <div
        class="absolute left-0 w-[336px] rounded-[30px]
               backdrop-blur-xl bg-white/30 shadow-2xl border border-white/50
               overflow-hidden"
        :style="{ top: GLASS_TOP + 'px', height: glassHeight + 'px' }"
      >
        <div class="absolute top-[19px] left-[20px] w-[101px] h-[103px] rounded-[13px] bg-[rgba(249,249,249,0.85)]" />
        <div class="absolute top-[19px] left-[138px] w-[172px] h-[46px] rounded-[13px] bg-[rgba(249,249,249,0.85)]" />
        <div class="absolute top-[76px] left-[138px] w-[172px] h-[46px] rounded-[13px] bg-[rgba(249,249,249,0.85)]" />

        <div class="absolute top-[26px] left-[40px] text-[17px]">Sisa Cuti</div>
        <div class="absolute top-[28px] left-[155px] text-[17px]">Digunakan</div>
        <div class="absolute top-[85px] left-[155px] text-[17px]">Total</div>

        <div class="absolute top-[42px] left-[46px] text-[40px] font-bold">12</div>
        <div class="absolute top-[92px] left-[56px] text-[15px]">Hari</div>

        <div class="absolute top-[21px] left-[275px] text-[20px] font-bold">5</div>
        <div class="absolute top-[45px] left-[272px] text-[10px]">Hari</div>

        <div class="absolute top-[78px] left-[270px] text-[20px] font-bold">17</div>
        <div class="absolute top-[103px] left-[272px] text-[10px]">Hari</div>

        <div
          class="absolute left-[20px] w-[290px] rounded-[13px]
                 bg-[rgba(249,249,249,0.85)] backdrop-blur-[2px]"
          :style="{ top: '137px', height: whiteBoxHeight + 'px' }"
        />

        <div class="absolute top-[144px] left-[39px] text-[17px] font-bold">
          Hirarki <br /> Level <br /> Approval
        </div>

        <div
          v-for="(sup, index) in backendSupervisors"
          :key="sup"
          class="absolute left-[155px] text-[17px]"
          :style="{ top: 143 + index * ROW_HEIGHT + 'px' }"
        >
          {{ sup }}
        </div>
      </div>
    </div>

    <!-- Images OUTSIDE the z-20 container so they're not clipped -->
    <img
      src="/images/headerpengajuancutiform.png"
      class="absolute left-[29px] w-[336px] h-[109px] block z-20"
      :style="{ top: (55.6 + belowGlassTop) + 'px' }"
    />
    <img
      src="/images/penagjuancutiglass.png"
      class="absolute left-[29px] w-[336px] block z-20"
      :style="{ top: (55.6 + belowGlassTop + 49) + 'px' }"
    />

    <!-- Form elements with higher z-index and dynamic positioning -->
<div class="absolute z-50" :style="{ top: (formBaseTop + 67) + 'px', left: '58px' }">
  <label class="block text-gray-800 text-[17px] font-light mb-2">Periode</label>
  <input
    type="text"
    placeholder="Pilih tanggal cuti"
    readonly
    class="w-[278px] h-[41px] rounded-[11px] bg-stone-50/50 backdrop-blur-sm px-3 text-[12px] font-thin text-gray-800 border border-white/30 cursor-pointer"
    @click="showDatePicker = true"
  />
</div>

<div class="absolute z-50" :style="{ top: (formBaseTop + 147) + 'px', left: '58px' }">
  <label class="block text-gray-800 text-[17px] font-light mb-2">Jenis Adjustment</label>
  <select
    class="w-[278px] h-[41px] rounded-[11px] bg-stone-50/50 backdrop-blur-sm px-3 text-[12px] font-thin text-gray-800 border border-white/30"
  >
    <option value="" disabled selected>Pilih jenis adjustment</option>
    <option value="sakit">Cuti Sakit</option>
    <option value="liburan">Cuti Liburan</option>
    <option value="emergency">Cuti Emergency</option>
  </select>
</div>

<div class="absolute z-50" :style="{ top: (formBaseTop + 227) + 'px', left: '58px' }">
  <label class="block text-gray-800 text-[17px] font-light mb-2">Keterangan</label>
  <textarea
    placeholder="Masukkan keterangan disini"
    class="w-[278px] h-[81px] rounded-[11px] bg-stone-50/50 backdrop-blur-sm px-3 py-2 text-[12px] font-thin text-gray-800 border border-white/30 resize-none"
  ></textarea>
</div>

<!-- iOS-style Date Picker Modal -->
<div 
  v-if="showDatePicker"
  class="fixed inset-0 z-[100] flex items-end justify-center bg-black/30"
  @click="showDatePicker = false"
>
  <div 
    class="w-full max-w-[393px] bg-[#f2f2f7] rounded-t-[20px] pb-8"
    @click.stop
  >
    <!-- Header -->
    <div class="flex items-center justify-between px-4 py-3 border-b border-gray-300">
      <button 
        @click="showDatePicker = false"
        class="text-[17px] text-[#007AFF] font-normal"
      >
        Cancel
      </button>
      <span class="text-[17px] font-semibold text-gray-800">Pilih Tanggal</span>
      <button 
        @click="confirmDates"
        class="text-[17px] text-[#007AFF] font-semibold"
      >
        Done
      </button>
    </div>
    
    <!-- Selected Dates Display -->
    <div class="relative px-4 py-3 bg-white">

  <!-- Invisible date input (NO layout participation) -->
  <input
    type="date"
    @change="addDate"
    class="absolute top-3 right-4
           w-[28px] h-[28px]
           opacity-0
           z-20
           cursor-pointer"
  />

  <!-- Visible calendar icon -->
  <div
    class="absolute top-3 right-4
           w-[28px] h-[28px]
           flex items-center justify-center
           z-10
           pointer-events-none"
  >
    <svg
      xmlns="http://www.w3.org/2000/svg"
      class="w-5 h-5 text-gray-700"
      fill="none"
      viewBox="0 0 24 24"
      stroke="currentColor"
    >
      <path
        stroke-linecap="round"
        stroke-linejoin="round"
        stroke-width="1.5"
        d="M8 7V3M16 7V3M3 11h18M5 21h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v12a2 2 0 002 2z"
      />
    </svg>
  </div>

  <!-- Selected dates -->
  <div v-if="selectedDates.length === 0" class="text-[15px] text-gray-500">
    Belum ada tanggal dipilih
  </div>

  <div v-else class="flex flex-wrap gap-2 pr-10">
    <div 
      v-for="date in selectedDates" 
      :key="date"
      class="inline-flex items-center gap-1 px-3 py-1 bg-[#007AFF] text-white rounded-full text-[14px]"
    >
      {{ formatDate(date) }}
      <button @click="removeDate(date)" class="ml-1 text-white">×</button>
    </div>
  </div>

</div>

    
    <!-- Calendar -->
    <div class="px-4 py-4 bg-white hidden">
      <input
        type="date"
        @change="addDate"
        class="w-full h-[44px] rounded-[10px] bg-[#f2f2f7] px-3 text-[17px] text-gray-800 border-none"
      />
    </div>
  </div>
</div>

    <button 
      @click="handlePengajuanCuti"
      class="absolute z-50 w-[278px] h-[40px] bg-white rounded-[11px] flex items-center justify-center text-[#0088FF] font-normal text-[17px] leading-[20px] font-sans"
      :style="{ top: (formBaseTop + 360) + 'px', left: '57px' }"
    >
      Ajukan Cuti
    </button>
  </div>
</template>

<style scoped>
.font-sfpro {
  font-family: 'SF Pro', system-ui, sans-serif;
}
</style>