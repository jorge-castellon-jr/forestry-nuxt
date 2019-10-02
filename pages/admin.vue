
<template>
    <div>
        <div id="app"></div>
        <script id="admin-config-script" type="text/javascript">
            var env = {
                siteId: "tznupki6g-l7ca",
                local: false
            };
        </script>
    </div>
</template>

<script>
export default {
    head () {
        return {
            link: [
                { rel: 'stylesheet', href: 'https://local.forestry.io/main.css' },
                { rel: 'stylesheet', href: 'https://fonts.googleapis.com/css?family=Open+Sans' },
            ],
            script: [
                { src: 'https://local.forestry.io/forestry.min.js', async: true, defer: true, body: true }
            ]
        }
    }
}
</script>