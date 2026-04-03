<template>
  <footer
    v-if="$nav.currentLayout !== 'cover' && $nav.currentLayout !== 'end'"
    class="absolute bottom-0 left-0 right-0 flex items-center justify-between px-8 py-2"
    style="border-top: 1px solid rgba(0,0,0,0.06); z-index: 10;"
  >
    <span style="font-size: 0.65em; color: #B8B2AA; letter-spacing: 0.08em;">
      LVMH Tech Hackathon — Integration / MuleSoft
    </span>
    <span style="font-size: 0.65em; color: #B8B2AA;">
      {{ $nav.currentPage }} / {{ $nav.total }}
    </span>
  </footer>
</template>
