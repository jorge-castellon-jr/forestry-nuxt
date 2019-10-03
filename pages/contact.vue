<template>
        <section class="info_blurb">
            <ul>
                <li>
                    <p>
                        <a>Location: {{ data.address }}</a>
                    </p>
                </li>
                <li v-if="data.phone_">
                    <p>
                        <a :href="`tel:${data.phone}`">Phone: {{ data.phone }}</a>
                    </p>
                </li>
                <li v-if="data.email_">
                    <p>
                        <a :href="`mailto:${data.email}`">Email: {{ data.email }}</a>
                    </p>
                </li>
            </ul>
        </section>
</template>

<script>
    export default {
        layout: 'layout',
        computed: {
            isInfoPage() {
                return this.$nuxt._route.name === "contact" && true
            }
        },
        async asyncData() {
            try {
                const data = await import(`~/content/data/contact.json`);
                return {
                data
                }
            } catch(err) {
                return false
            }
        },
    }
</script>

