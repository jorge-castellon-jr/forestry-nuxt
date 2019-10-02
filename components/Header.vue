<template>
    <header class="header">
        <nav class="nav">
            <div>
                <NuxtLink to="/">
                    <h1>{{ header.title }}</h1>
                </NuxtLink>
                <p>{{ header.description }}</p>
            </div>
            <div>
                <h1>
                    <NuxtLink :to="infoRoute">{{ isInfoPage ? "close" : "info" }}</NuxtLink>
                </h1>
            </div>
        </nav>
    </header>
</template>

<script>
    import configJSON from '~/content/data/config.json'

    export default {
        data () {
            return {
                header: configJSON,
            }
        },
        props: {
                isInfoPage: {
                    type: Boolean,
                    required: false
            }
        }, 
        computed: {
            infoRoute() {
                return this.isInfoPage ? "/" : "/info"
            }
        }
    }
</script>
