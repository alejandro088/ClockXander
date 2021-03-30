<template>
    <v-app>
        <v-navigation-drawer dark v-model="drawer" app permanent>
            <v-toolbar>
                <v-app-bar-nav-icon
                    @click="$root.$emit('drawer')"
                ></v-app-bar-nav-icon>
                <v-toolbar-title class="mx-3">
                    <div class="logo">
                        <h3>ClockXander</h3>
                    </div>
                </v-toolbar-title>
            </v-toolbar>

            <v-list dense rounded>
                <v-list-item
                    v-for="item in items"
                    :key="item.title"
                    :href="item.route"
                >
                    <v-list-item-icon>
                        <v-icon>{{ item.icon }}</v-icon>
                    </v-list-item-icon>

                    <v-list-item-content>
                        <v-list-item-title>{{ item.title }}</v-list-item-title>
                    </v-list-item-content>
                </v-list-item>
            </v-list>
        </v-navigation-drawer>
        <v-app-bar app dark>
            <v-spacer></v-spacer>

            <v-btn
                href="https://github.com/vuetifyjs/vuetify/releases/latest"
                target="_blank"
                text
            >
                <span class="mr-2">Latest Release</span>
                <v-icon>mdi-open-in-new</v-icon>
            </v-btn>
        </v-app-bar>

        <v-main>
            <HelloWorld />
        </v-main>
    </v-app>
</template>

<script>
import HelloWorld from './components/HelloWorld';

export default {
    name: 'App',

    components: {
        HelloWorld
    },

    data: () => ({
        drawer: true,
        items: [
            {
                title: 'Resume',
                icon: 'mdi-view-dashboard',
                route: '/dashboard'
            },
            {
                title: 'TodoList',
                icon: 'mdi-format-list-checks',
                route: '/todolist'
            },
            {
                title: 'Clocks',
                icon: 'mdi-clock-time-four-outline',
                route: '/clocks'
            },
            {
                title: 'Alarms',
                icon: 'mdi-alarm-multiple',
                route: '/alarms'
            },
            {
                title: 'Time Tracker',
                icon: 'mdi-timetable',
                route: '/trackers'
            }
        ]
    })
};
</script>
