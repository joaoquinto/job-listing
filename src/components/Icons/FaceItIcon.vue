<script setup>
defineProps({ width: { type: Number, default: 88 }, height: { type: Number, default: 88 } })
</script>

<template>
  <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" :width :height>
    <defs>
      <linearGradient id="a" x1="50%" x2="50%" y1="3.455%" y2="100%">
        <stop offset="0%" stop-color="#D961C3" />
        <stop offset="100%" stop-color="#6858FF" />
      </linearGradient>
      <filter
        id="c"
        width="139.8%"
        height="139.8%"
        x="-19.9%"
        y="-19.9%"
        filterUnits="objectBoundingBox"
      >
        <feGaussianBlur in="SourceAlpha" result="shadowBlurInner1" stdDeviation="17.5" />
        <feOffset in="shadowBlurInner1" result="shadowOffsetInner1" />
        <feComposite
          in="shadowOffsetInner1"
          in2="SourceAlpha"
          k2="-1"
          k3="1"
          operator="arithmetic"
          result="shadowInnerInner1"
        />
        <feColorMatrix
          in="shadowInnerInner1"
          values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0.0452633304 0"
        />
      </filter>
      <circle id="b" cx="44" cy="44" r="44" />
    </defs>
    <g fill="none" fill-rule="evenodd">
      <use fill="url(#a)" xlink:href="#b" />
      <use fill="#000" filter="url(#c)" xlink:href="#b" />
      <path
        fill="#FFF"
        d="M41.5 30C50.613 30 58 37.387 58 46.5S50.613 63 41.5 63 25 55.613 25 46.5 32.387 30 41.5 30zm0 7.333a9.167 9.167 0 100 18.334 9.167 9.167 0 000-18.334zM59.5 25a3.5 3.5 0 110 7 3.5 3.5 0 010-7z"
      />
    </g>
  </svg>
</template>

<style scoped lang="scss"></style>
