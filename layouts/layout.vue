<template>
    <section class="layout">
        <Header :is-info-page="isInfoPage" />
        <div class="content">
            <nuxt />
        </div>
    </section>
</template>

<script>
import Header from '~/components/Header.vue'

    export default {
        components: {
            Header
        }, 
        computed: {
            isInfoPage() {
                return this.$nuxt._route.name === "info" && true
            }
        },
        transition (to, from) {
            if (!from) { return 'slide-left' }
            return +to.query.page < +from.query.page ? 'slide-right' : 'slide-left'
        },
    }
</script>

<style>
.page-enter-active,
.page-leave-active {
  transition: all 1s;
}
.page-enter,
.page-leave-to {
    transition: all .5s;
    opacity: 0;
    transform: translate(-500px, 0);
}
</style>

