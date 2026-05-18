<script setup>
import { ref, onMounted } from 'vue'
import FaqAccordion from './components/FaqAccordion.vue'

// Images
import logoLight from './images-fylo/logo-light-mode.svg'
import logoDark from './images-fylo/logo-dark-mode.svg'
import bgCurvyLight from './images-fylo/bg-curvy-light-mode.svg'
import bgCurvyDark from './images-fylo/bg-curvy-dark-mode.svg'
import introImg from './images-fylo/illustration-intro.png'
import productiveImg from './images-fylo/illustration-stay-productive.png'

// Icons
import iconAccess from './images-fylo/icon-access-anywhere.svg'
import iconSecurity from './images-fylo/icon-security.svg'
import iconCollab from './images-fylo/icon-collaboration.svg'
import iconAnyFile from './images-fylo/icon-any-file.svg'
import iconArrow from './images-fylo/icon-arrow.svg'

// Profiles
import profile1 from './images-fylo/profile-1.jpg'
import profile2 from './images-fylo/profile-2.jpg'
import profile3 from './images-fylo/profile-3.jpg'
import bgQuotes from './images-fylo/bg-quotes.png'

// Social Icons
import iconFacebook from './images-fylo/facebook.svg'
import iconTwitter from './images-fylo/twitter.svg'
import iconInstagram from './images-fylo/instagram.svg'

const isDarkMode = ref(true)

const toggleTheme = () => {
  isDarkMode.value = !isDarkMode.value
  if (isDarkMode.value) {
    document.documentElement.classList.add('dark')
  } else {
    document.documentElement.classList.remove('dark')
  }
}

onMounted(() => {
  document.documentElement.classList.add('dark') // Default is dark mode
})
</script>

<template>
  <div class="min-h-screen relative overflow-hidden transition-colors duration-300">
    
    <!-- Header Area (bg-alt for hero section context) -->
    <div class="bg-fylo-bg-alt">
      <header class="container mx-auto px-6 md:px-16 py-8 md:py-16 flex justify-between items-center">
        <img :src="isDarkMode ? logoDark : logoLight" alt="Fylo Logo" class="h-6 md:h-12" />
        
        <nav class="flex items-center gap-4 md:gap-10 font-heading text-xs md:text-base">
          <a href="#" class="hover:text-fylo-cyan transition-colors">Features</a>
          <a href="#" class="hover:text-fylo-cyan transition-colors">Team</a>
          <a href="#" class="hover:text-fylo-cyan transition-colors">Sign In</a>
          
          <button 
            @click="toggleTheme" 
            :aria-label="isDarkMode ? 'Switch to Light Mode' : 'Switch to Dark Mode'"
            class="p-2 rounded-full hover:text-fylo-cyan transition-all"
          >
            <svg v-if="isDarkMode" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-5 h-5"><path stroke-linecap="round" stroke-linejoin="round" d="M12 3v2.25m6.364.386l-1.591 1.591M21 12h-2.25m-.386 6.364l-1.591-1.591M12 18.75V21m-4.773-4.227l-1.591 1.591M5.25 12H3m4.227-4.773L5.636 5.636M15.75 12a3.75 3.75 0 11-7.5 0 3.75 3.75 0 017.5 0z" /></svg>
            <svg v-else xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-5 h-5"><path stroke-linecap="round" stroke-linejoin="round" d="M21.752 15.002A9.718 9.718 0 0118 15.75c-5.385 0-9.75-4.365-9.75-9.75 0-1.33.266-2.597.748-3.752A9.753 9.753 0 003 11.25C3 16.635 7.365 21 12.75 21a9.753 9.753 0 009.002-5.998z" /></svg>
          </button>
        </nav>
      </header>

      <!-- Hero Section -->
      <section class="relative text-center px-6 pt-10 pb-4 md:pb-12 z-10">
        <div class="container mx-auto flex flex-col items-center">
          <img :src="introImg" alt="Illustration Intro" class="mb-10 max-w-full md:max-w-2xl" />
          <h1 class="text-3xl md:text-5xl font-bold leading-tight max-w-3xl font-heading mb-6">
            All your files in one secure location, accessible anywhere.
          </h1>
          <p class="md:text-lg max-w-2xl text-fylo-text-muted mb-8 font-body">
            Fylo stores all your most important files in one secure location. Access them wherever you need, share and collaborate with friends, family, and co-workers.
          </p>
          <button class="btn-primary w-full md:w-auto px-20 py-4 rounded-full font-bold text-white transition-all text-sm md:text-base">
            Get Started
          </button>
        </div>
      </section>

      <!-- Background Curvy Image positioned right below hero -->
      <div class="w-full">
        <img :src="isDarkMode ? bgCurvyDark : bgCurvyLight" alt="" class="w-full block" />
      </div>
    </div>

    <!-- Main Content -->
    <main class="bg-fylo-bg flex-1 flex flex-col items-center pb-40 px-6">
      <div class="container mx-auto max-w-6xl">
        
        <!-- Features Grid -->
        <section class="grid grid-cols-1 md:grid-cols-2 gap-y-20 gap-x-32 max-w-5xl mx-auto mt-24">
          <div class="flex flex-col items-center text-center">
            <img :src="iconAccess" alt="Access anywhere" class="h-20 mb-8" />
            <h2 class="text-xl font-bold font-heading mb-3">Access your files from anywhere</h2>
            <p class="text-fylo-text-muted text-sm md:text-base">The ability to use a smartphone, tablet, or computer to access your account means your files follow you everywhere.</p>
          </div>
          <!-- Security -->
          <div class="flex flex-col items-center text-center">
            <img :src="iconSecurity" alt="Security" class="h-20 mb-8" />
            <h2 class="text-xl font-bold font-heading mb-3">Security you can trust</h2>
            <p class="text-fylo-text-muted text-sm md:text-base">2-factor authentication and user-controlled encryption are just a couple of the security features we allow to help secure your files.</p>
          </div>
          <!-- Collaboration -->
          <div class="flex flex-col items-center text-center">
            <img :src="iconCollab" alt="Collaboration" class="h-20 mb-8" />
            <h2 class="text-xl font-bold font-heading mb-3">Real-time collaboration</h2>
            <p class="text-fylo-text-muted text-sm md:text-base">Securely share files and folders with friends, family and colleagues for live collaboration. No email attachments required.</p>
          </div>
          <!-- Any file -->
          <div class="flex flex-col items-center text-center">
            <img :src="iconAnyFile" alt="Any file" class="h-20 mb-8" />
            <h2 class="text-xl font-bold font-heading mb-3">Store any type of file</h2>
            <p class="text-fylo-text-muted text-sm md:text-base">Whether you're sharing holidays photos or work documents, Fylo has you covered allowing for all file types to be securely stored and shared.</p>
          </div>
        </section>

        <!-- Stay Productive -->
        <section class="flex flex-col md:flex-row items-center gap-12 mt-40">
          <div class="md:w-1/2">
            <img :src="productiveImg" alt="Stay productive" class="w-full" />
          </div>
          <div class="md:w-1/2 text-left md:pl-10 mt-12 md:mt-0">
            <h2 class="text-3xl md:text-[2.5rem] font-bold font-heading mb-6 md:max-w-md leading-tight">Stay productive,<br/>wherever you are</h2>
            <p class="text-fylo-text-muted mb-4 text-sm md:text-base">Never let location be an issue when accessing your files. Fylo has you covered for all of your file storage needs.</p>
            <p class="text-fylo-text-muted mb-6 text-sm md:text-base">Securely share files and folders with friends, family and colleagues for live collaboration. No email attachments required.</p>
            <a href="#" class="inline-flex items-center gap-2 text-fylo-cyan border-b border-fylo-cyan pb-1 hover:text-white hover:border-white transition-colors">
              See how Fylo works
              <img :src="iconArrow" alt="" class="w-4" />
            </a>
          </div>
        </section>

        <!-- FAQ -->
        <section class="w-full pt-32">
          <div class="text-center mb-12">
            <h2 class="text-2xl md:text-3xl font-bold font-heading mb-4">Frequently Asked Questions</h2>
            <p class="text-fylo-text-muted max-w-xl mx-auto">Here are some of our FAQs. If you have any other questions you'd like answered please feel free to email us.</p>
          </div>
          <FaqAccordion />
        </section>

        <!-- Testimonials -->
        <section class="mt-40 relative px-2 md:px-0">
          <img :src="bgQuotes" alt="" class="absolute -top-10 -left-2 md:-left-3 w-12 md:w-16 z-0" />
          
          <div class="grid grid-cols-1 md:grid-cols-3 gap-10 relative z-10">
            <!-- Card 1 -->
            <div class="bg-fylo-surface p-10 rounded-lg shadow-lg">
              <p class="text-sm md:text-[15px] mb-6 text-fylo-text leading-relaxed tracking-wide">Fylo has improved our team productivity by an order of magnitude. Since making the switch our team has become a well-oiled collaboration machine.</p>
              <div class="flex items-center gap-4">
                <img :src="profile1" alt="Satish Patel" class="w-10 h-10 rounded-full" />
                <div>
                  <h3 class="font-bold text-sm font-heading tracking-wide">Satish Patel</h3>
                  <p class="text-xs text-fylo-text-muted">Founder & CEO, Huddle</p>
                </div>
              </div>
            </div>
            <!-- Card 2 -->
            <div class="bg-fylo-surface p-10 rounded-lg shadow-lg">
              <p class="text-sm md:text-[15px] mb-6 text-fylo-text leading-relaxed tracking-wide">Fylo has improved our team productivity by an order of magnitude. Since making the switch our team has become a well-oiled collaboration machine.</p>
              <div class="flex items-center gap-4">
                <img :src="profile2" alt="Bruce McKenzie" class="w-10 h-10 rounded-full" />
                <div>
                  <h3 class="font-bold text-sm font-heading tracking-wide">Bruce McKenzie</h3>
                  <p class="text-xs text-fylo-text-muted">Founder & CEO, Huddle</p>
                </div>
              </div>
            </div>
            <!-- Card 3 -->
            <div class="bg-fylo-surface p-10 rounded-lg shadow-lg">
              <p class="text-sm md:text-[15px] mb-6 text-fylo-text leading-relaxed tracking-wide">Fylo has improved our team productivity by an order of magnitude. Since making the switch our team has become a well-oiled collaboration machine.</p>
              <div class="flex items-center gap-4">
                <img :src="profile3" alt="Iva Boyd" class="w-10 h-10 rounded-full" />
                <div>
                  <h3 class="font-bold text-sm font-heading tracking-wide">Iva Boyd</h3>
                  <p class="text-xs text-fylo-text-muted">Founder & CEO, Huddle</p>
                </div>
              </div>
            </div>
          </div>
        </section>

      </div>
    </main>

    <!-- Footer Area (includes Early Access overlapping) -->
    <div class="relative bg-fylo-footer pt-64 pb-24 mt-32">
      
      <!-- Early Access Form -->
      <div class="absolute left-1/2 -translate-x-1/2 -top-40 w-full max-w-4xl px-6">
        <div class="bg-fylo-surface text-center p-10 md:py-12 md:px-20 rounded-lg shadow-2xl">
          <h2 class="text-2xl md:text-3xl font-bold font-heading mb-6">Get early access today</h2>
          <p class="text-fylo-text-muted mb-10 max-w-2xl mx-auto md:text-[15px]">It only takes a minute to sign up and our free starter tier is extremely generous. If you have any questions, our support team would be happy to help you.</p>
          <form @submit.prevent class="flex flex-col md:flex-row gap-6 max-w-3xl mx-auto">
            <input type="email" placeholder="email@example.com" class="flex-1 px-8 py-4 rounded-full text-gray-900 placeholder-gray-400 bg-white outline-none focus:ring-2 focus:ring-fylo-cyan shadow-sm" required />
            <button type="submit" class="btn-primary w-full md:w-auto px-8 py-4 rounded-full font-bold text-white transition-all whitespace-nowrap">
              Get Started For Free
            </button>
          </form>
        </div>
      </div>

      <!-- Footer Content -->
      <footer class="container mx-auto max-w-7xl px-6 md:px-12 mt-10">
        <img :src="logoLight" alt="Fylo Logo" class="h-10 mb-10" v-if="!isDarkMode" />
        <img :src="logoDark" alt="Fylo Logo" class="h-10 mb-10" v-else />

        <div class="flex flex-col md:flex-row gap-12 md:gap-20 text-sm text-fylo-text-muted">
          <!-- Location -->
          <div class="md:w-1/3 flex items-start gap-4">
            <img src="./images-fylo/icon-location.svg" alt="" class="mt-1 w-4" />
            <p class="leading-relaxed">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua</p>
          </div>

          <!-- Contact -->
          <div class="md:w-1/6 flex flex-col gap-4">
            <div class="flex items-center gap-4">
              <img src="./images-fylo/icon-phone.svg" alt="" class="w-4" />
              <p>+1-543-123-4567</p>
            </div>
            <div class="flex items-center gap-4">
              <img src="./images-fylo/icon-email.svg" alt="" class="w-4" />
              <p>example@fylo.com</p>
            </div>
          </div>

          <!-- Links 1 -->
          <div class="md:w-1/6 flex flex-col gap-4">
            <a href="#" class="hover:font-bold hover:text-fylo-text transition-all">About Us</a>
            <a href="#" class="hover:font-bold hover:text-fylo-text transition-all">Jobs</a>
            <a href="#" class="hover:font-bold hover:text-fylo-text transition-all">Press</a>
            <a href="#" class="hover:font-bold hover:text-fylo-text transition-all">Blog</a>
          </div>

          <!-- Links 2 -->
          <div class="md:w-1/6 flex flex-col gap-4">
            <a href="#" class="hover:font-bold hover:text-fylo-text transition-all">Contact Us</a>
            <a href="#" class="hover:font-bold hover:text-fylo-text transition-all">Terms</a>
            <a href="#" class="hover:font-bold hover:text-fylo-text transition-all">Privacy</a>
          </div>

          <!-- Socials -->
          <div class="md:w-1/6 flex justify-center md:justify-start gap-4 h-fit">
            <a href="#" class="w-8 h-8 rounded-full border border-fylo-text-muted flex items-center justify-center hover:border-fylo-cyan hover:text-fylo-cyan transition-all">
               <span class="sr-only">Facebook</span>
               <i class="fab fa-facebook-f text-xs"></i>
               <svg class="w-3 h-3 fill-current" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 320 512"><path d="M279.14 288l14.22-92.66h-88.91v-60.13c0-25.35 12.42-50.06 52.24-50.06h40.42V6.26S260.43 0 225.36 0c-73.22 0-121.08 44.38-121.08 124.72v70.62H22.89V288h81.39v224h100.17V288z"/></svg>
            </a>
            <a href="#" class="w-8 h-8 rounded-full border border-fylo-text-muted flex items-center justify-center hover:border-fylo-cyan hover:text-fylo-cyan transition-all">
               <span class="sr-only">Twitter</span>
               <svg class="w-3 h-3 fill-current" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512"><path d="M459.37 151.716c.325 4.548.325 9.097.325 13.645 0 138.72-105.583 298.558-298.558 298.558-59.452 0-114.68-17.219-161.137-47.106 8.447.974 16.568 1.299 25.34 1.299 49.055 0 94.213-16.568 130.274-44.832-46.132-.975-84.792-31.188-98.112-72.772 6.498.974 12.995 1.624 19.818 1.624 9.421 0 18.843-1.3 27.614-3.573-48.081-9.747-84.143-51.98-84.143-102.985v-1.299c13.969 7.797 30.214 12.67 47.431 13.319-28.264-18.843-46.781-51.005-46.781-87.391 0-19.492 5.197-37.36 14.294-52.954 51.655 63.675 129.3 105.258 216.365 109.807-1.624-7.797-2.599-15.918-2.599-24.04 0-57.828 46.782-104.934 104.934-104.934 30.213 0 57.502 12.67 76.67 33.137 23.715-4.548 46.456-13.32 66.599-25.34-7.798 24.366-24.366 44.833-46.132 57.827 21.117-2.273 41.584-8.122 60.426-16.243-14.292 20.791-32.161 39.308-52.628 54.253z"/></svg>
            </a>
            <a href="#" class="w-8 h-8 rounded-full border border-fylo-text-muted flex items-center justify-center hover:border-fylo-cyan hover:text-fylo-cyan transition-all">
               <span class="sr-only">Instagram</span>
               <svg class="w-3 h-3 fill-current" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"><path d="M224.1 141c-63.6 0-114.9 51.3-114.9 114.9s51.3 114.9 114.9 114.9S339 319.5 339 255.9 287.7 141 224.1 141zm0 189.6c-41.1 0-74.7-33.5-74.7-74.7s33.5-74.7 74.7-74.7 74.7 33.5 74.7 74.7-33.6 74.7-74.7 74.7zm146.4-194.3c0 14.9-12 26.8-26.8 26.8-14.9 0-26.8-12-26.8-26.8s12-26.8 26.8-26.8 26.8 12.2 26.8 26.8zm76.1 27.2c-1.7-35.9-9.9-67.7-36.2-93.9-26.2-26.2-58-34.4-93.9-36.2-37-2.1-147.9-2.1-184.9 0-35.8 1.7-67.6 9.9-93.9 36.1s-34.4 58-36.2 93.9c-2.1 37-2.1 147.9 0 184.9 1.7 35.9 9.9 67.7 36.2 93.9s58 34.4 93.9 36.2c37 2.1 147.9 2.1 184.9 0 35.9-1.7 67.7-9.9 93.9-36.2 26.2-26.2 34.4-58 36.2-93.9 2.1-37 2.1-147.8 0-184.8zM398.8 388c-7.8 19.6-22.9 34.7-42.6 42.6-29.5 11.7-99.5 9-132.1 9s-102.7 2.6-132.1-9c-19.6-7.8-34.7-22.9-42.6-42.6-11.7-29.5-9-99.5-9-132.1s-2.6-102.7 9-132.1c7.8-19.6 22.9-34.7 42.6-42.6 29.5-11.7 99.5-9 132.1-9s102.7-2.6 132.1 9c19.6 7.8 34.7 22.9 42.6 42.6 11.7 29.5 9 99.5 9 132.1s2.7 102.7-9 132.1z"/></svg>
            </a>
          </div>
        </div>
      </footer>
    </div>
  </div>
</template>