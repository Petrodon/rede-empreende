<template>
    <v-app>
        <v-container>
            <Menu/>
            <Post/>
        </v-container>
    </v-app>
</template>

<script>
import Menu from '@/components/Menu.vue'
import Post from '@/components/Post'
import { mapGetters } from "vuex"

export default {
    components: {
        Post,
        Menu
    },
    computed: {
        ...mapGetters(["getIsLogged"])
    },
    created: function() {
        if (!this.getIsLogged) {
            return this.$router.push("/");
        }
    },
}
</script>
