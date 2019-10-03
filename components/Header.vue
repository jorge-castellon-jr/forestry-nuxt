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
                <nuxt-link v-for="page in pages" :key="page" :to="`/pages${page.link}`">{{ page.title }}</nuxt-link>
            </div>
            <div>
                <h1>
                    <NuxtLink to="/info">info</NuxtLink>
                </h1>
                <h1>
                    <NuxtLink to="/contact">contact</NuxtLink>
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
                pages: [
                    { title: 'Test', link: '/test' }
                ]
            }
        }
    }
</script>
