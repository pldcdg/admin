<template>
<q-layout view="lHh Lpr lFf">
    <q-header class="text-black q-pb-md border-bottom p-ma-sm">
        <q-toolbar class="q-mt-sm">
            <q-btn flat dense round icon="menu" aria-label="Menu" @click="leftDrawerOpen = !leftDrawerOpen" />

            <q-toolbar-title class="text-center text-h7">
                Kollab
            </q-toolbar-title>

            <q-btn flat dense round icon="account_circle" class="text-grey" />
            <q-btn flat round icon="notifications_none">
                <q-badge color="orange" floating>1</q-badge>
            </q-btn>
            <q-btn flat dense round icon="help_outline" />

        </q-toolbar>
        <q-toolbar-title class="text-h5">
            {{page}}
            <q-btn flat dense round icon="help" class="text-grey text-caption text-weight-thin" />
        </q-toolbar-title>
    </q-header>

    <q-drawer v-model="leftDrawerOpen" show-if-above bordered content-class="">
        <q-list>
            <q-item-label header class="text-grey-4">

            </q-item-label>
            <EssentialLink v-for="link in essentialLinks" :key="link.title" v-bind="link" />
        </q-list>
    </q-drawer>

    <q-page-container>
        <router-view />
    </q-page-container>
</q-layout>
</template>

<script>
import EssentialLink from 'components/EssentialLink.vue'

const linksData = [{
    title: 'Analytics',
    caption: '',
    icon: 'insert_chart',
    link: '/analytics'
}, {
    title: 'Logout',
    caption: '',
    icon: 'exit_to_app',
    link: '/login'
}];

export default {
    name: 'MainLayout',
    components: {
        EssentialLink
    },
    data() {
        return {
            leftDrawerOpen: false,
            essentialLinks: linksData,
            page: "Analytics"
        }
    },
    mounted() {
        if (this.$router.currentRoute.path == '/analytics') {
            this.page = "Analytics"
        }
    },
}
</script>
