<script setup>
defineProps({ width: { type: Number, default: 88 }, height: { type: Number, default: 88 } })
</script>

<template>
  <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" :width :height>
    <defs>
      <filter
        id="b"
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
      <circle id="a" cx="44" cy="44" r="44" />
    </defs>
    <g fill="none" fill-rule="evenodd">
      <use fill="#1A7373" xlink:href="#a" />
      <use fill="#000" filter="url(#b)" xlink:href="#a" />
      <path
        fill="#FFF"
        d="M37 29l-.001 2.727H37c1.79 0 3.49.383 5.024 1.072A14.96 14.96 0 0037 44c0 4.454 1.94 8.454 5.023 11.201A12.228 12.228 0 0137 56.273c-6.778 0-12.272-5.494-12.273-12.272L22 44c0 8.284 6.716 15 15 15 2.732 0 5.293-.73 7.5-2.006A14.939 14.939 0 0052 59c8.284 0 15-6.716 15-15 0-8.284-6.716-15-15-15-2.732 0-5.294.73-7.5 2.007A14.928 14.928 0 0037 29zm15 2.727c6.778 0 12.273 5.495 12.273 12.273S58.778 56.273 52 56.273c-1.79 0-3.49-.383-5.024-1.072A14.96 14.96 0 0052 44c0-4.454-1.94-8.454-5.023-11.201A12.228 12.228 0 0152 31.727zm-7.5 2.558l.018.014A12.252 12.252 0 0149.273 44c0 3.954-1.87 7.471-4.774 9.716A12.256 12.256 0 0139.727 44c0-3.954 1.87-7.47 4.773-9.715z"
      />
    </g>
  </svg>
</template>

<style scoped lang="scss"></style>
