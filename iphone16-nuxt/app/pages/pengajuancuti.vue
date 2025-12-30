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
const FORM_IMAGE_HEIGHT = 400

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

const belowGlassTop = computed(() =>
  GLASS_TOP + glassHeight.value + GAP_BELOW_GLASS
)

const containerHeight = computed(() =>
  Math.max(1169, belowGlassTop.value + FORM_IMAGE_HEIGHT + 50)
)

const formBaseTop = computed(() =>
  belowGlassTop.value + 55
)

/* =========================
   DATE PICKER
   ========================= */
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
  return date.toLocaleDateString('id-ID', {
    day: 'numeric',
    month: 'short',
    year: 'numeric',
  })
}

const confirmDates = () => {
  showDatePicker.value = false
}
</script>

<template>
  <div
    class="relative w-[393px] mx-auto font-sfpro overflow-hidden"
    :style="{ minHeight: containerHeight + 'px' }"
  >
    <!-- BACKGROUND -->
    <img
      src="/images/test3longg.png"
      class="absolute inset-0 w-[393px] h-[1196px]"
    />

    <!-- HEADER IMAGE -->
    <img
      src="/images/headerpengajuancuti.png"
      class="absolute top-[55.6px] left-[27px] w-[340px] h-[168px] z-10 opacity-85"
    />

    <!-- HEADER TEXT -->
    <div class="absolute top-[55.6px] left-[29px] z-20 w-[336px]">
      <div class="absolute top-[19px] left-[25px] text-white text-[30px] font-bold">
        Hi, User
      </div>
      <div class="absolute top-[58px] left-[25px] text-white text-[19px] font-light">
        Gunakan sisa cuti dengan bijak!
      </div>

      <!-- TOP GLASS CARD -->
      <div
        class="absolute left-[0px] w-[336px] rounded-[15px]
             overflow-hidden
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
             after:pointer-events-none"
        :style="{ top: GLASS_TOP + 'px', height: glassHeight + 'px' }"
      >
        <div class="absolute top-[19px] left-[20px] w-[101px] h-[103px] rounded-[13px] bg-white/85" />
        <div class="absolute top-[19px] left-[138px] w-[172px] h-[46px] rounded-[13px] bg-white/85" />
        <div class="absolute top-[76px] left-[138px] w-[172px] h-[46px] rounded-[13px] bg-white/85" />

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
          class="absolute left-[20px] w-[290px] rounded-[13px] bg-white/85"
          :style="{ top: '137px', height: whiteBoxHeight + 'px' }"
        />

        <div class="absolute top-[144px] left-[39px] text-[17px] font-bold">
          Hirarki<br />Level<br />Approval
        </div>

        <div
          v-for="(sup, index) in backendSupervisors"
          :key="index"
          class="absolute left-[155px] text-[17px]"
          :style="{ top: 143 + index * ROW_HEIGHT + 'px' }"
        >
          {{ sup }}
        </div>
      </div>
    </div>

    <!--  FORM GLASS -->
    <div
      class="absolute left-[29px] w-[332px] rounded-[15px]
             overflow-hidden
             backdrop-blur-[12px] backdrop-saturate-125
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
             z-20"
      :style="{ top: (55.6 + belowGlassTop + 49) + 'px', height: '370px' }"
    />

    <!-- FORM -->

    <img
      src="/images/headerpengajuancutiform.png"
      class="absolute left-[25px] w-[340px] h-[109px] block z-10"
      :style="{ top: (55.6 + belowGlassTop) + 'px' }"
    />

    <div class="absolute z-50" :style="{ top: (formBaseTop + 67) + 'px', left: '58px' }">
      <label class="block text-gray-800 text-[17px] font-light mb-2">Periode</label>
      <input
        type="text"
        readonly
        placeholder="Pilih tanggal cuti"
        class="w-[278px] h-[41px] rounded-[11px]
               bg-stone-50/50 backdrop-blur-sm
               px-3 text-[12px] text-gray-800
               border border-white/30 cursor-pointer z-20"
        @click="showDatePicker = true"
      />
    </div>

    <div class="absolute z-50" :style="{ top: (formBaseTop + 147) + 'px', left: '58px' }">
      <label class="block text-gray-800 text-[17px] font-light mb-2">Jenis Adjustment</label>
      <select
        class="w-[278px] h-[41px] rounded-[11px]
               bg-stone-50/50 backdrop-blur-sm
               px-3 text-[12px] text-gray-800
               border border-white/30"
      >
        <option disabled selected>Pilih jenis adjustment</option>
        <option>Cuti Sakit</option>
        <option>Cuti Liburan</option>
        <option>Cuti Emergency</option>
      </select>
    </div>

    <div class="absolute z-50" :style="{ top: (formBaseTop + 227) + 'px', left: '58px' }">
      <label class="block text-gray-800 text-[17px] font-light mb-2">Keterangan</label>
      <textarea
        class="w-[278px] h-[81px] rounded-[11px]
               bg-stone-50/50 backdrop-blur-sm
               px-3 py-2 text-[12px]
               border border-white/30 resize-none"
      />
    </div>

    <button
      class="absolute z-50 w-[278px] h-[40px]
             bg-white rounded-[11px]
             text-[#0088FF] text-[17px]"
      :style="{ top: (formBaseTop + 360) + 'px', left: '57px' }"
      @click="handlePengajuanCuti"
    >
      Ajukan Cuti
    </button>

    <!-- DATE PICKER -->
    <div
      v-if="showDatePicker"
      class="fixed inset-0 z-[100] flex items-end justify-center bg-black/30"
      @click="showDatePicker = false"
    >
      <div class="w-full max-w-[393px] bg-[#f2f2f7] rounded-t-[20px]" @click.stop>
        <div class="flex justify-between px-4 py-3 border-b">
          <button @click="showDatePicker = false" class="text-[#007AFF]">Cancel</button>
          <button @click="confirmDates" class="text-[#007AFF] font-semibold">Done</button>
        </div>

        <div class="relative px-4 py-4 bg-white">
          <!-- DATE INPUT -->
          <input
            type="date"
            @change="addDate"
            class="absolute top-4 right-4 w-[28px] h-[28px] opacity-0 z-20 cursor-pointer"
          />

          <!-- DARK ICON (FIXED) -->
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="absolute top-4 right-4 w-5 h-5 text-gray-700 pointer-events-none"
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

          <div v-if="selectedDates.length === 0" class="text-gray-500">
            Belum ada tanggal dipilih
          </div>

          <div v-else class="flex flex-wrap gap-2">
            <span
              v-for="date in selectedDates"
              :key="date"
              class="px-3 py-1 bg-[#007AFF] text-white rounded-full"
            >
              {{ formatDate(date) }}
            </span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.font-sfpro {
  font-family: 'SF Pro', system-ui, sans-serif;
}
</style>
