<script setup lang="ts">
interface Props {
  hovered?: boolean
  strokeWidth?: number
  color?: string
}

withDefaults(defineProps<Props>(), {
  strokeWidth: 10,
  color: 'accent'
})

import type {SvgSignature} from "#components";

const signatureSvg = ref<SVGSVGElement | null>(null)
const paths = ref<NodeListOf<SVGPathElement>>()
const pathLengths = ref<number[]>([])

onMounted(() => {
  if (!signatureSvg.value) return
  const foundPaths = signatureSvg.value.querySelectorAll("path")

  foundPaths.forEach((path) => {
    pathLengths.value.push(path.getTotalLength())
  })
})
</script>

<template>
  <svg ref="signatureSvg" :class="{'animate': hovered}" id="signature-svg" width="1036" height="822" viewBox="0 0 1036 822" fill="none" xmlns="http://www.w3.org/2000/svg">
    <path :style="{ 'stroke-dasharray': pathLengths[0] ?? 0, 'stroke-dashoffset': pathLengths[0] ?? 0 }" d="M196.31 346.149C175.31 460.149 206.31 553.649 213.81 570.149C221.31 586.649 223.81 601.649 186.311 581.149" :stroke="`var(--${color})`" :stroke-width="strokeWidth" stroke-linecap="round"/>
    <path :style="{ 'stroke-dasharray': pathLengths[1] ?? 0, 'stroke-dashoffset': pathLengths[1] ?? 0 }" d="M27.8103 424.149C-26.6897 278.649 15.3103 213.149 166.31 264.149C317.31 315.149 421.089 390.819 295.811 463.149C233.5 499.124 134.5 534 88.9995 545C42.827 556.163 47.3105 547.149 96.8105 561.649" :stroke="`var(--${color})`" :stroke-width="strokeWidth" stroke-linecap="round"/>
    <path :style="{ 'stroke-dasharray': pathLengths[2] ?? 0, 'stroke-dashoffset': pathLengths[2] ?? 0 }" d="M309.811 523.149C247.811 527.149 260.811 571.149 273.811 595.149C286.811 619.149 319.811 618.149 341.811 599.149C381.444 564.919 359.811 515.149 333.811 511.649C307.811 508.149 292.811 537.149 313.311 552.149C333.811 567.149 373.903 545.814 392.811 538.149C411.311 530.649 437.811 515.149 450.311 530.649C462.811 546.149 432.811 599.149 463.311 599.149" :stroke="`var(--${color})`" :stroke-width="strokeWidth" stroke-linecap="round"/>
    <path :style="{ 'stroke-dasharray': pathLengths[3] ?? 0, 'stroke-dashoffset': pathLengths[3] ?? 0 }" d="M473.811 319.649C501.811 406.649 516.311 503.649 526.311 562.649C536.311 621.649 496.086 635.026 514.311 562.649C531.811 493.149 567.311 472.149 595.311 463.149" :stroke="`var(--${color})`" :stroke-width="strokeWidth" stroke-linecap="round"/>
    <path :style="{ 'stroke-dasharray': pathLengths[4] ?? 0, 'stroke-dashoffset': pathLengths[4] ?? 0 }" d="M608.309 497.501C663.81 472.5 683.309 401.592 683.309 367.5C683.309 320.501 668.809 312.501 654.809 377.001C640.809 441.501 634.81 518.5 616.81 600C599.757 677.212 600.31 696 588.81 748.5C570.739 831 527.809 850.001 553.809 741.501C574.609 654.701 648.809 567.001 683.309 534.001" :stroke="`var(--${color})`" :stroke-width="strokeWidth" stroke-linecap="round"/>
    <path :style="{ 'stroke-dasharray': pathLengths[5] ?? 0, 'stroke-dashoffset': pathLengths[5] ?? 0 }" d="M721.968 538.593C698.386 555.692 701.935 596.136 730.435 605.231C767.288 616.992 785.502 589.344 787.586 555.111C789.348 526.164 764.52 506.127 735.903 515.405C704.089 525.72 713.145 560.097 726.468 563.413" :stroke="`var(--${color})`" :stroke-width="strokeWidth" stroke-linecap="round"/>
    <path :style="{ 'stroke-dasharray': pathLengths[6] ?? 0, 'stroke-dashoffset': pathLengths[6] ?? 0 }" d="M813 520.23C866.5 475.73 868 430.73 868 409.73C868 388.73 863 368.23 848.5 397.73C834 427.23 772 656.23 874.5 599.73" :stroke="`var(--${color})`" :stroke-width="strokeWidth" stroke-linecap="round"/>
    <path :style="{ 'stroke-dasharray': pathLengths[7] ?? 0, 'stroke-dashoffset': pathLengths[7] ?? 0 }" d="M900.42 569.493C909.083 572.024 905.809 590.693 903.089 599.711" :stroke="`var(--${color})`" :stroke-width="strokeWidth" stroke-linecap="round"/>
    <path :style="{ 'stroke-dasharray': pathLengths[8] ?? 0, 'stroke-dashoffset': pathLengths[8] ?? 0 }" d="M895.647 491.56C876.652 490.904 891.938 503.117 908.497 510.876" :stroke="`var(--${color})`" :stroke-width="strokeWidth" stroke-linecap="round"/>
    <path :style="{ 'stroke-dasharray': pathLengths[9] ?? 0, 'stroke-dashoffset': pathLengths[9] ?? 0 }" d="M938.048 552.11C934.508 592.27 967.346 610.638 995.671 604.178C1024 597.718 1035.62 577.692 1028 549.947C1020.38 522.202 1000.88 509.557 972.393 518.735C943.903 527.913 933.419 556.193 949.639 568.638" :stroke="`var(--${color})`" :stroke-width="strokeWidth" stroke-linecap="round"/>
    <path :style="{ 'stroke-dasharray': pathLengths[10] ?? 0, 'stroke-dashoffset': pathLengths[10] ?? 0 }" d="M506 118C519.5 133 505 257.5 541.5 168.5C556.623 131.625 563.198 142 567 165.5C571.691 194.5 581.5 205 591.5 165.5C602.892 120.5 617.5 126.5 629.5 156.5C633.522 166.555 643.5 178.5 654.5 168.5" :stroke="`var(--${color})`" :stroke-width="strokeWidth" stroke-linecap="round"/>
    <path :style="{ 'stroke-dasharray': pathLengths[11] ?? 0, 'stroke-dashoffset': pathLengths[11] ?? 0 }" d="M678 118.149C681 165.649 709 204.649 729.5 172.149C750 139.649 758.5 80.6487 735.5 147.649C717.1 201.249 689.5 268.982 678 296.149" :stroke="`var(--${color})`" :stroke-width="strokeWidth" stroke-linecap="round"/>
    <path :style="{ 'stroke-dasharray': pathLengths[12] ?? 0, 'stroke-dashoffset': pathLengths[12] ?? 0 }" d="M618.619 13.0005C458.119 43.0005 360.619 216.5 489.619 255C618.619 293.5 791.619 256 810.119 134.5C828.619 13.0005 552.119 32.0005 479.119 106.5C406.119 181 419.619 278 567.619 280C715.619 282 792.053 212 791.619 145.5C791.272 92.3005 717.474 29.6672 680.619 5.00049" :stroke="`var(--${color})`" :stroke-width="strokeWidth" stroke-linecap="round"/>
  </svg>
</template>

<style scoped lang="scss">
#signature-svg {
  transform: rotate(-10deg);
  &.animate path {
    &:nth-child(1) {
      animation: dash .2s linear forwards;
    }
    &:nth-child(2) {
      animation: dash .4s linear forwards;
      animation-delay: .25s;
    }
    &:nth-child(3) {
      animation: dash .4s cubic-bezier(.17,.67,.83,.67) forwards;
      animation-delay: .7s;
    }
    &:nth-child(4) {
      animation: dash .3s linear forwards;
      animation-delay: 1.15s;
    }
    &:nth-child(5) {
      animation: dash .5s linear forwards;
      animation-delay: 1.5s;
    }
    &:nth-child(6) {
      animation: dash .3s linear forwards;
      animation-delay: 2.1s;
    }
    &:nth-child(7) {
      animation: dash .3s linear forwards;
      animation-delay: 2.45s;
    }
    &:nth-child(8) {
      animation: dash .1s ease-in forwards;
      animation-delay: 2.85s;
    }
    &:nth-child(9) {
      animation: dash .1s ease-in forwards;
      animation-delay: 3.0s;
    }
    &:nth-child(10) {
      animation: dash .3s linear forwards;
      animation-delay: 3.15s;
    }
    &:nth-child(11) {
      animation: dash .4s linear forwards;
      animation-delay: 3.55s;
    }
    &:nth-child(12) {
      animation: dash .2s linear forwards;
      animation-delay: 4.0s;
    }
    &:nth-child(13) {
      animation: dash .8s linear forwards;
      animation-delay: 4.25s;
    }
  }
}

@keyframes dash {
  to {
    stroke-dashoffset: 0;
  }
}
</style>