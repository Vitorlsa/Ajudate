<template>
  <div class="LandingPageLogo"  @click="startApp" >
    <img max-height="756" max-width="536" src="../assets/LogoCompleto.png" alt="LogoAjudate" />
  </div>
</template>

<script>
export default {
    name: "LandingPage",
    data() {
        return {
            isClicked: false,
        }
    },
    methods: {
        startApp(){
            this.isClicked = true
            this.$emit('startApp', this.isClicked)
        }
    }
}
</script>

<style scoped>
    .LandingPageLogo {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100%;
        width: 100%;
    }

</style>