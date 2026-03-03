<script setup>
import AnimeCard from '@/components/AnimeCard.vue'
import { ref } from 'vue'

const loading = ref(false)
const error = ref('')

const spin = () => {
  if (error.value.length > 0) error.value = ''
  else error.value = 'Something wrong'
}
</script>

<template>
  <main
    class="min-h-screen bg-[radial-gradient(circle_at_15%_20%,#334155,transparent_40%),radial-gradient(circle_at_85%_80%,#1e293b,transparent_40%)] p-6"
  >
    <div class="mx-auto max-w-7xl">
      <header class="mb-8">
        <p class="text-sx font-semibold tracking-[0.3em] text-cyan-300 uppercase">Project #4</p>
        <h1 class="- mt-2 text-4xl font-black text-white sm:text-5xl">Anime Roulette Watchlist</h1>
        <p class="mt-2 max-w-3xl text-slate-300 sm:text-base">
          Spin the wheel, request a random anime from Jikan with VueUse useFech, and learn how REST
          APIs signal rate limiting with HTTP 429.
        </p>
      </header>

      <div class="grid gap-6 lg:grid-cols-[1.2fr_0.8fr]">
        <section class="space-y-5">
          <div
            class="rounded-3xl border border-slate-700/70 bg-slate-900/60 p-5 shadow-2xl shadow-slate-900/30 backdrop-blur-sm"
          >
            <div class="flex flex-col gap-3 sm:flex-row sm:items-center sm:justify-between">
              <div>
                <h2 class="text-xl font-bold text-white">Roulette</h2>
                <p class="text-sm text-slate-300">
                  Pull the lever for your next random anime recommendation!
                </p>
              </div>
              <button
                type="button"
                class="cursor-pointer rounded-full border border-cyan-300/70 bg-cyan-400/20 px-6 py-3 text-base font-black tracking-wide text-cyan-100 hover:bg-cyan-400/30"
                @click="spin"
              >
                Spin
              </button>
            </div>
          </div>
          <AnimeCard
            :loading="loading"
            :error="error"
          />
        </section>
      </div>
    </div>
  </main>
</template>
