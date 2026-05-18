<script setup>
import { ref } from 'vue'

const faqs = ref([
  {
    id: 1,
    question: 'What is Bookmark?',
    answer: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce tincidunt justo eget ultricies fringilla. Phasellus blandit ipsum quis quam ornare mattis.',
    isOpen: false
  },
  {
    id: 2,
    question: 'How can I request a new browser?',
    answer: 'Vivamus luctus eros aliquet convallis ultricies. Mauris augue massa, ultricies non ligula. Suspendisse imperdiet. Vivamus luctus eros aliquet convallis ultricies.',
    isOpen: false
  },
  {
    id: 3,
    question: 'Is there a mobile app?',
    answer: 'Sed consectetur quam id neque fermentum accumsan. Praesent luctus vestibulum dolor, ut condimentum urna vulputate eget. Cras in ligula quis est pharetra mattis sit amet pharetra purus.',
    isOpen: false
  },
  {
    id: 4,
    question: 'What about other Chromium browsers?',
    answer: 'Integer condimentum ipsum id imperdiet finibus. Vivamus in placerat mi, at euismod dui. Aliquam vitae neque eget nisl gravida pellentesque non ut velit.',
    isOpen: false
  }
])

const toggleFaq = (index) => {
  faqs.value[index].isOpen = !faqs.value[index].isOpen
}
</script>

<template>
  <div class="w-full max-w-2xl mx-auto flex flex-col">
    <div 
      v-for="(faq, index) in faqs" :key="faq.id"
      class="border-b border-fylo-border/50 transition-all duration-300"
    >
      <button 
        @click="toggleFaq(index)"
        :aria-expanded="faq.isOpen"
        :aria-controls="'faq-answer-' + faq.id"
        class="w-full py-5 flex justify-between items-center focus:outline-none group"
      >
        <span class="font-heading text-sm md:text-base text-fylo-text group-hover:text-fylo-cyan transition-colors text-left">{{ faq.question }}</span>
        
        <svg 
          class="w-4 h-4 text-fylo-cyan transition-transform duration-300"
          :class="{ 'rotate-180 text-fylo-error': faq.isOpen }"
          xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="3" stroke="currentColor"
        >
          <path stroke-linecap="round" stroke-linejoin="round" d="M19.5 8.25l-7.5 7.5-7.5-7.5" />
        </svg>
      </button>

      <div 
        v-show="faq.isOpen" 
        :id="'faq-answer-' + faq.id"
        class="pb-6 text-fylo-text-muted text-sm md:text-base leading-relaxed text-left"
      >
        {{ faq.answer }}
      </div>
    </div>
  </div>
</template>