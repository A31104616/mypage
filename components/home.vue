<template>
  <svg 
    :width="size" 
    :height="size" 
    viewBox="0 0 24 24" 
    :fill="color"
    xmlns="http://www.w3.org/2000/svg"
  >
    <path d="M12 2L2 9V22H9V15H15V22H22V9L12 2ZM20 20H17V13H7V20H4V10L12 4.5L20 10V20Z"/>
  </svg>
</template>

<script>
export default {
  name: 'HomeIcon',
  props: {
    size: {
      type: [Number, String],
      default: 24
    },
    color: {
      type: String,
      default: 'currentColor'
    }
  }
}
</script>