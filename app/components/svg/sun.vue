<script setup lang="ts">
interface Props {
  color?: string
  strokeWidth?: number
}

withDefaults(defineProps<Props>(), {
  color: 'accent',
  strokeWidth: 4
})
</script>

<template>
  <svg width="349" height="353" viewBox="0 0 349 353" fill="none" xmlns="http://www.w3.org/2000/svg">
    <path d="M123.5 2.00037C140.5 30.5004 146.5 72.5004 146.5 72.5004" :stroke="`var(--${color})`" :stroke-width="strokeWidth" stroke-linecap="round"/>
    <path d="M226.5 94.0004C236.667 83.5004 262.4 60.4004 284 52.0004" :stroke="`var(--${color})`" :stroke-width="strokeWidth" stroke-linecap="round"/>
    <path d="M264 199C274 196.2 318.5 192 346.5 199" :stroke="`var(--${color})`" :stroke-width="strokeWidth" stroke-linecap="round"/>
    <path d="M220 282C220.8 302.4 236.667 343.167 243 350.5" :stroke="`var(--${color})`" :stroke-width="strokeWidth" stroke-linecap="round"/>
    <path d="M123.5 274.5C110.866 278.509 79.5735 318.841 72.5127 332.511" :stroke="`var(--${color})`" :stroke-width="strokeWidth" stroke-linecap="round"/>
    <path d="M85.5 211.414C66.3 209.414 13.5 232.667 2 238.5" :stroke="`var(--${color})`" :stroke-width="strokeWidth" stroke-linecap="round"/>
    <path d="M85.5 135C82.1667 131.834 48.5 122 30 116.5" :stroke="`var(--${color})`" :stroke-width="strokeWidth" stroke-linecap="round"/>
    <path d="M179 87.5004C171.178 88.966 164.084 91.2142 157.683 94.1221M157.683 94.1221C112.392 114.699 101.84 168.31 113.958 211.414C120.859 235.959 154.328 283.913 201.801 259.5C249.275 235.087 240.303 184.042 230.958 162.219C223.281 144.291 194.919 100.402 157.683 94.1221ZM157.683 94.1221C149.592 92.7575 141.082 93.1687 132.274 96.0079" :stroke="`var(--${color})`" :stroke-width="strokeWidth" stroke-linecap="round"/>
  </svg>
</template>

<style scoped lang="scss">
svg {
  overflow: visible;
}
</style>