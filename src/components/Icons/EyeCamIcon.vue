<script setup>
defineProps({ width: { type: Number, default: 88 }, height: { type: Number, default: 88 } })
</script>

<template>
  <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" :width :height>
    <defs>
      <linearGradient id="a" x1="50%" x2="50%" y1="0%" y2="98.044%">
        <stop offset="0%" stop-color="#43E2DF" />
        <stop offset="100%" stop-color="#156A8D" />
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
        fill-rule="nonzero"
        d="M14 48.628V39.39h5.093v1.275h-3.61v2.315h3.61V44.3h-3.61v2.984h3.61v1.344H14zm11.038 0V44.4l-3.074-5.01h1.559l1.914 3.136a10.556 10.556 0 01.38.738c.058-.147.12-.286.184-.416s.132-.25.202-.36l1.964-3.098h1.483l-3.141 5.01v4.227h-1.471zm7.883 0V39.39h5.093v1.275h-3.61v2.315h3.61V44.3h-3.61v2.984h3.61v1.344H32.92zm16.398-6.99a4.557 4.557 0 00-1.33-.815 4.05 4.05 0 00-1.475-.27c-.997 0-1.808.323-2.434.97-.625.648-.938 1.488-.938 2.518 0 .997.304 1.82.913 2.467.609.648 1.377.971 2.303.971a4.15 4.15 0 001.543-.29 4.881 4.881 0 001.406-.877v1.697c-.4.29-.833.507-1.303.65a5.22 5.22 0 01-1.527.215 5.274 5.274 0 01-1.936-.347 4.488 4.488 0 01-1.561-1.022 4.548 4.548 0 01-1.025-1.562 5.123 5.123 0 01-.359-1.915c0-.677.12-1.313.359-1.908a4.606 4.606 0 011.037-1.568 4.569 4.569 0 011.559-1.031 5.09 5.09 0 011.901-.35c.536 0 1.047.078 1.533.236.487.158.958.396 1.415.716l-.08 1.514zM55.364 45h2.543l-.935-2.107a8.313 8.313 0 01-.168-.464 10.78 10.78 0 01-.175-.584 8.549 8.549 0 01-.33 1.048L55.364 45zm4.102 3.628l-1.035-2.379h-3.616l-1.06 2.379h-1.558l4.42-9.603 4.413 9.603h-1.564zm12.147-4.562a7.916 7.916 0 01-.081-.593c-.034-.269-.063-.492-.088-.669-.037.21-.09.421-.159.631-.068.21-.154.425-.258.644L68.639 49l-2.387-5.022a7.173 7.173 0 01-.449-1.174c-.004.194-.02.397-.047.61a6.586 6.586 0 01-.121.665l-.979 4.549h-1.365L65.448 39l2.693 5.83c.041.092.105.246.19.46.085.215.188.48.308.795.088-.265.225-.601.412-1.01.05-.109.087-.193.112-.252L71.793 39 74 48.628h-1.378l-1.01-4.562z"
      />
    </g>
  </svg>
</template>

<style scoped lang="scss"></style>
