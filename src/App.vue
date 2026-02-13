<template>
  <div
    class="min-h-screen bg-gradient-to-br from-[#FFF0F3] via-[#FFD6E0] to-[#FFF0F3] flex flex-col items-center justify-center p-4 font-serif overflow-hidden relative"
  >
    <div class="absolute inset-0 pointer-events-none overflow-hidden">
      <div
        v-for="n in 25"
        :key="n"
        class="absolute animate-float-varied"
        :style="{
          left: Math.random() * 150 + '%',
          top: '110%',
          animationDelay: Math.random() * 10 + 's',
          fontSize: Math.random() * 20 + 20 + 'px',
        }"
      >
        {{
          [
            "💖",
            "✨",
            "🤷🏻‍♂️",
            "🌸",
            "🤍",
            "🤷🏻‍♀️",
            "🎀",
            "☺️",
            "💛",
            "🙆🏻‍♂️",
            "🙆🏻‍♀️",
            "🌷",
            "🌼",
          ][n % 13]
        }}
      </div>
    </div>

    <div
      class="bg-white/90 backdrop-blur-sm rounded-[3rem] shadow-2xl w-full max-w-sm flex flex-col items-center p-8 relative border-4 border-white z-10"
    >
      <span
        class="text-[10px] text-center tracking-[0.2em] uppercase font-bold text-pink-400 mb-2"
      >
        My appreciation for you <span>:'P</span>
      </span>
      <h1
        class="text-3xl font-black text-gray-800 mb-6 text-center leading-tight"
      >
        Horrible Person 👀
      </h1>

      <div
        class="relative w-full h-80 mb-8 rounded-[2.5rem] overflow-hidden border-2 border-pink-50 shadow-inner bg-pink-50 flex items-center justify-center"
      >
        <transition name="fade" mode="out-in">
          <img
            v-if="!loadingMessage"
            :src="tulip"
            alt="Valentine Bouquet"
            class="w-full h-full object-cover z-10 scale-120"
          />
          <div
            v-else
            class="flex flex-col items-center justify-center space-y-4 z-20 p-6 text-center"
          >
            <div class="relative">
              <div
                class="animate-ping absolute inset-0 rounded-full bg-pink-300 opacity-75"
              ></div>
              <div class="relative animate-bounce text-4xl">?</div>
            </div>
            <p
              class="text-pink-400 uppercase tracking-[0.2em] text-[10px] font-bold mt-4"
            >
              Preparing...
            </p>
          </div>
        </transition>
      </div>

      <p
        class="text-[11px] text-pink-400 font-bold uppercase tracking-[0.2em] mb-6 animate-pulse"
      >
        <!-- Touch to unwrap 💌 -->
      </p>

      <div class="w-full relative">
        <div
          class="absolute inset-0 bg-pink-200 rounded-2xl shadow-inner translate-y-1"
        ></div>
        <button
          @click="startReveal"
          :disabled="loadingMessage"
          class="relative w-full bg-gradient-to-r from-pink-500 to-rose-600 text-white font-bold py-4 px-8 rounded-2xl transition-all shadow-lg uppercase tracking-widest text-sm outline-none"
          :class="
            loadingMessage
              ? 'translate-y-1 shadow-none opacity-80'
              : 'active:translate-y-1 active:shadow-none hover:scale-[1.02]'
          "
        >
          {{ loadingMessage ? "Opening..." : "Open This" }}
        </button>
      </div>
      <br />
      <p class="text-[15px] text-center font-semibold text-pink-400 mb-2">
        Made you this cuz am too broke to send a real bouquet
        <br />
        😭😭😭
      </p>
    </div>

    <transition name="pop-card">
      <div
        v-if="showNote"
        class="fixed inset-0 z-50 flex items-center justify-center p-6 bg-pink-200/40 backdrop-blur-xl"
      >
        <div
          class="bg-white w-full max-w-xs p-4 rounded-[2.5rem] shadow-[0_20px_50px_rgba(0,0,0,0.15)] border-t-8 border-pink-400 relative text-center"
        >
          <div class="w-full h-42 mb-4">
            <svg viewBox="0 0 200 160" class="w-full h-full drop-shadow-lg">
              <defs>
                <linearGradient
                  id="tulipGrad"
                  x1="0%"
                  y1="0%"
                  x2="0%"
                  y2="100%"
                >
                  <stop offset="0%" style="stop-color: #fb7185" />
                  <stop offset="100%" style="stop-color: #e11d48" />
                </linearGradient>
              </defs>

              <g stroke="#A7F3D0" stroke-width="2.5" stroke-linecap="round">
                <path d="M100 150 L100 60" />
                <path d="M100 150 L60 100" />
                <path d="M100 150 L140 100" />
                <path d="M100 150 L75 75" />
                <path d="M100 150 L125 75" />
                <path d="M100 150 L100 95" />
              </g>

              <g transform="translate(100, 50)">
                <circle r="18" fill="white" />
                <circle r="7" fill="#FACC15" />
              </g>
              <g transform="translate(60, 100) scale(0.7)">
                <circle r="18" fill="white" />
                <circle r="7" fill="#FACC15" />
              </g>
              <g transform="translate(140, 100) scale(0.7)">
                <circle r="18" fill="white" />
                <circle r="7" fill="#FACC15" />
              </g>

              <g transform="translate(75, 75) scale(0.8)">
                <path
                  d="M-10 -15 Q-10 10 0 15 Q10 10 10 -15 L5 -5 L0 -20 L-5 -5 Z"
                  fill="url(#tulipGrad)"
                />
              </g>
              <g transform="translate(125, 75) scale(0.8)">
                <path
                  d="M-10 -15 Q-10 10 0 15 Q10 10 10 -15 L5 -5 L0 -20 L-5 -5 Z"
                  fill="url(#tulipGrad)"
                />
                s
              </g>
              <g transform="translate(100, 95) scale(0.7)">
                <path
                  d="M-10 -15 Q-10 10 0 15 Q10 10 10 -15 L5 -5 L0 -20 L-5 -5 Z"
                  fill="#FB7185"
                />
              </g>
            </svg>
          </div>

          <div x-data="{ showCard: false }">
            <p class="text-gray-700 leading-relaxed italic text-base mb-8">
              Bright and Cheerful like
              <span class="text-yellow-500 font-bold">Daisy</span>
              <br />
              Tender and Hopeful like
              <span class="text-rose-500 font-bold">Tulip</span>
              <br />
              <span>------</span>
              <br />
              Thank you for being here for me, <br />
              You change me and push me this far, Urs support mean everythings
              to me,
              <br />
              You made my everydays more softer and calmer!
              <br />
              Thanks you for make me smile like an idiot everydays 😂
              <br />
              THANKS YOU FOR BEING HERE! ALWAYS!
            </p>

            <div class="flex flex-col gap-3">
              <button
                @click="resetView"
                class="w-full bg-pink-100 hover:bg-pink-200 text-pink-600 py-3 rounded-2xl text-sm font-bold transition-all active:scale-95"
              >
                Close
              </button>

              <button
                @click="showAnotherCard = true"
                class="w-full bg-yellow-100 hover:bg-yellow-200 text-yellow-700 py-3 rounded-2xl text-sm font-bold transition-all active:scale-95"
              >
                Click here for more!
              </button>
            </div>

            <transition name="fade">
              <div
                v-if="showAnotherCard"
                class="fixed inset-0 bg-black/60 backdrop-blur-md flex items-center justify-center z-[60]"
                @click="showAnotherCard = false"
              >
                <transition name="pop-card">
                  <div class="relative max-w-[90%] max-h-[80%]" @click.stop>
                    <img
                      :src="monkey"
                      alt="popup"
                      class="rounded-3xl shadow-2xl border-4 border-white object-cover"
                    />
                    <button
                      @click="showAnotherCard = false"
                      class="absolute -top-4 -right-4 bg-white rounded-full p-2 shadow-lg text-gray-800"
                    >
                      ✕
                    </button>
                    <div
                      class="text-white leading-relaxed italic text-base mb-8 p-2"
                    >
                      <span>
                        <p>
                          THANKS YOU FOR
                          <span class="text-pink-600 font-bold">TALKING, </span>
                          <span class="text-pink-600 font-bold">TEXTING, </span>
                          <span class="text-pink-600 font-bold">GAMING </span>
                          WITH THIS BORING GUY!
                          <br />
                          LOVE YOU...
                        </p>
                      </span>
                    </div>
                  </div>
                </transition>
              </div>
            </transition>
          </div>
        </div>
      </div>
    </transition>
    <br />
    <p class="text-sm text-gray-600">
      &copy; <span class="font-semibold text-gray-800">Kimchheng Ung</span>.
    </p>
  </div>
</template>

<script setup>
import { ref } from "vue";
import flower from "/src/assets/tulip.png";
import monkey from "/src/assets/monkey.jpg";
import pig from "/src/assets/pig.png";
import daisy from "/src/assets/flower.jpg";
import tulip from "/src/assets/flower1.jpg";

const showNote = ref(false);
const loadingMessage = ref(false);
const showAnotherCard = ref(false); // We will use this consistently

const startReveal = () => {
  loadingMessage.value = true;
  setTimeout(() => {
    showNote.value = true;
  }, 3500);
};

const resetView = () => {
  showNote.value = false;
  loadingMessage.value = false;
  showAnotherCard.value = false; // Reset the image too
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Playfair+Display:wght@900&family=Inter:wght@700&display=swap");

h1 {
  font-family: "Playfair Display", serif;
}

@keyframes float-varied {
  0% {
    transform: translateY(0) rotate(0deg);
  }
  100% {
    transform: translateY(-120vh) rotate(360deg);
    opacity: 0;
  }
}
.animate-float-varied {
  animation: float-varied 10s linear infinite;
}

/* Transitions */
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.8s ease;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

.pop-card-enter-active {
  animation: card-in 0.7s cubic-bezier(0.175, 0.885, 0.32, 1.275);
}
.pop-card-leave-active {
  transition: all 0.3s ease-in;
  opacity: 0;
  transform: scale(0.8);
}

@keyframes card-in {
  0% {
    transform: scale(0) rotate(-15deg);
    opacity: 0;
  }
  100% {
    transform: scale(1) rotate(0deg);
    opacity: 1;
  }
}

button {
  -webkit-tap-highlight-color: transparent;
}
</style>
