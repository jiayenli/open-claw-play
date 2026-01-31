<template>
  <div class="min-h-screen bg-gradient-to-br from-purple-500 via-pink-500 to-red-500 flex items-center justify-center p-4">
    <div class="bg-white rounded-2xl shadow-2xl p-8 max-w-md w-full">
      <div class="text-center mb-8">
        <h1 class="text-4xl font-bold text-transparent bg-clip-text bg-gradient-to-r from-purple-600 to-pink-600 mb-2">
          😂 笑話生成器
        </h1>
        <p class="text-gray-500">點擊按鈕獲得隨機笑話！</p>
      </div>

      <div class="bg-gradient-to-r from-purple-50 to-pink-50 rounded-xl p-6 mb-6 min-h-24 flex items-center">
        <p class="text-gray-800 text-lg leading-relaxed font-medium">
          {{ currentJoke }}
        </p>
      </div>

      <div class="flex gap-3 mb-4">
        <button
          @click="getRandomJoke"
          :disabled="loading"
          class="flex-1 bg-gradient-to-r from-purple-600 to-pink-600 text-white font-bold py-3 px-4 rounded-lg hover:shadow-lg transform hover:scale-105 transition-all duration-200 disabled:opacity-50 disabled:cursor-not-allowed"
        >
          {{ loading ? '載入中...' : '🎲 獲取笑話' }}
        </button>
      </div>

      <div class="flex gap-2">
        <button
          @click="copyToClipboard"
          class="flex-1 bg-gray-100 text-gray-700 font-semibold py-2 px-4 rounded-lg hover:bg-gray-200 transition-colors duration-200 flex items-center justify-center gap-2"
        >
          📋 複製
        </button>
        <button
          @click="shareJoke"
          class="flex-1 bg-blue-100 text-blue-700 font-semibold py-2 px-4 rounded-lg hover:bg-blue-200 transition-colors duration-200 flex items-center justify-center gap-2"
        >
          📤 分享
        </button>
      </div>

      <div class="mt-6 text-center text-sm text-gray-500">
        <p>✨ 已載入笑話: {{ jokesLoaded }}</p>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const jokes = ref([
  "為什麼科學家不信任原子？因為它們會編造一切！",
  "你聽說過那個害怕負數的數學家嗎？他會不惜一切代價避免它們！",
  "稻草人為什麼贏得了獎項？因為他在田裡表現傑出！",
  "假麵條叫什麼？一個騙局！",
  "為什麼雞蛋不講笑話？因為它們會把彼此逗笑！",
  "大海對沙灘說了什麼？沒什麼，它只是揮了揮手！",
  "為什麼咖啡報警？因為它被搶劫了！",
  "瑞士最好的是什麼？我不知道，但他們的旗幟是個大加號！",
  "骷髏頭為什麼互相不打架？因為它們沒有膽量！",
  "沒有牙齒的熊叫什麼？軟糖熊！",
  "自行車為什麼倒下了？因為它太累了！",
  "什麼是橙色的，聽起來像鸚鵡？一根胡蘿蔔！",
  "為什麼我們在農場裡永遠不會洩露秘密？因為馬鈴薯有眼睛，玉米有耳朵！",
  "三只腳的食蟻獸叫什麼？一個食蟻獸！",
  "雞為什麼過馬路？為了到達另一邊！",
  "電腦最喜歡的零食是什麼？微晶片！",
  "為什麼數學書看起來很悲傷？因為它有太多問題！",
  "穿著背心的鱷魚叫什麼？調查員！",
  "為什麼你永遠看不到大象躲在樹裡？因為它們藏得很好！",
  "一堵牆對另一堵牆說了什麼？我會在角落里見你！"
])

const currentJoke = ref("點擊按鈕獲得隨機笑話！🎉")
const loading = ref(false)
const jokesLoaded = ref(0)

const getRandomJoke = () => {
  loading.value = true
  setTimeout(() => {
    const randomIndex = Math.floor(Math.random() * jokes.value.length)
    currentJoke.value = jokes.value[randomIndex]
    jokesLoaded.value++
    loading.value = false
  }, 400)
}

const copyToClipboard = () => {
  navigator.clipboard.writeText(currentJoke.value).then(() => {
    alert('笑話已複製到剪貼板！📋')
  })
}

const shareJoke = () => {
  if (navigator.share) {
    navigator.share({
      title: '看看這個笑話！',
      text: currentJoke.value
    })
  } else {
    alert('分享功能不可用，請嘗試複製！')
  }
}
</script>
