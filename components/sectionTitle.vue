<template lang="pug">
  section
    div(class="Contents")
      div(class="sectionTitleArea" ref="sectionTitleArea")
        h2(class="sectionTitle" ref="sectionTitle") {{ secTitle }}
        span(class="underLine" ref="underLine")
        div(class="backcircleFill" ref="backcircleFill")
        div(class="backcircleStripes" ref="backcircleStripes")
      slot
</template>

<script>
export default {
  props: ['secTitle'],
  data() {
    return {
    }
  },
  
}
</script>