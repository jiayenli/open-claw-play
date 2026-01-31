<template>
  <div class="min-h-screen bg-gradient-to-br from-purple-500 via-pink-500 to-red-500 flex items-center justify-center p-4">
    <div class="bg-white rounded-2xl shadow-2xl p-8 max-w-md w-full">
      <div class="text-center mb-8">
        <h1 class="text-4xl font-bold text-transparent bg-clip-text bg-gradient-to-r from-purple-600 to-pink-600 mb-2">
          😂 Joke Generator
        </h1>
        <p class="text-gray-500">Get a random joke to brighten your day!</p>
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
          {{ loading ? 'Loading...' : '🎲 Get New Joke' }}
        </button>
      </div>

      <div class="flex gap-2">
        <button
          @click="copyToClipboard"
          class="flex-1 bg-gray-100 text-gray-700 font-semibold py-2 px-4 rounded-lg hover:bg-gray-200 transition-colors duration-200 flex items-center justify-center gap-2"
        >
          📋 Copy
        </button>
        <button
          @click="shareJoke"
          class="flex-1 bg-blue-100 text-blue-700 font-semibold py-2 px-4 rounded-lg hover:bg-blue-200 transition-colors duration-200 flex items-center justify-center gap-2"
        >
          📤 Share
        </button>
      </div>

      <div class="mt-6 text-center text-sm text-gray-500">
        <p>✨ Jokes loaded: {{ jokesLoaded }}</p>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const jokes = ref([
  "Why don't scientists trust atoms? Because they make up everything!",
  "Did you hear about the mathematician who's afraid of negative numbers? He'll stop at nothing to avoid them!",
  "Why did the scarecrow win an award? He was outstanding in his field!",
  "What do you call a fake noodle? An impasta!",
  "Why don't eggs tell jokes? They'd crack each other up!",
  "What did the ocean say to the beach? Nothing, it just waved!",
  "Why did the coffee file a police report? It got mugged!",
  "What's the best thing about Switzerland? I don't know, but their flag is a big plus!",
  "Why don't skeletons fight each other? They don't have the guts!",
  "What do you call a bear with no teeth? A gummy bear!",
  "Why did the bicycle fall over? Because it was two-tired!",
  "What's orange and sounds like a parrot? A carrot!",
  "Why don't we ever tell secrets on a farm? Because the potatoes have eyes and the corn has ears!",
  "What do you call a three-footed aardvark? A aardvark!",
  "Why did the chicken cross the road? To get to the other side!",
  "What's a computer's favorite snack? Microchips!",
  "Why did the math book look sad? Because it had too many problems!",
  "What do you call an alligator in a vest? An investigator!",
  "Why don't you ever see elephants hiding in trees? Because they're so good at it!",
  "What did one wall say to the other wall? I'll meet you at the corner!"
])

const currentJoke = ref("Click the button to get a random joke! 🎉")
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
    alert('Joke copied to clipboard! 📋')
  })
}

const shareJoke = () => {
  if (navigator.share) {
    navigator.share({
      title: 'Check out this joke!',
      text: currentJoke.value
    })
  } else {
    alert('Share feature not available. Try copying instead!')
  }
}
</script>
