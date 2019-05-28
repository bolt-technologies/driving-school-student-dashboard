<template>
    <div>
        <v-toolbar flat app class="white">

            <v-toolbar-side-icon class="red--text lighten-1 hidden-md-and-up" @click.stop="drawer = !drawer"></v-toolbar-side-icon>

            <v-toolbar-title class="text-uppercase red--text text--darken-1">
                <span class="font-weight-light">Recup</span>
                <span class="font-weight-bold">Mespoints</span>
            </v-toolbar-title>

            <v-spacer></v-spacer>

            <v-btn flat color="red darken-1">
                <span>Sign Out</span>
                <v-icon right >exit_to_app</v-icon>
            </v-btn>
        </v-toolbar>

        <v-navigation-drawer
                v-model="drawer"
                :mini-variant="mini"
                class="primary"
                dark
                app>

            <v-list >
                <v-list-tile v-if="mini" @click.stop="mini = !mini">
                    <v-list-tile-action>
                        <v-icon>chevron_right</v-icon>
                    </v-list-tile-action>
                </v-list-tile>

                <v-list-tile avatar tag="div" >
                    <v-list-tile-avatar>
                        <img src="https://randomuser.me/api/portraits/men/85.jpg">
                    </v-list-tile-avatar>

                    <v-list-tile-content>
                        <v-list-tile-title>John Leider</v-list-tile-title>
                    </v-list-tile-content>

                    <v-list-tile-action>
                        <v-btn icon @click.stop="mini = !mini">
                            <v-icon>chevron_left</v-icon>
                        </v-btn>
                    </v-list-tile-action>
                </v-list-tile>
            </v-list>

            <v-list class="pt-0" dense>
                <v-divider light></v-divider>

                <v-list-tile
                        v-for="item in items"
                        :key="item.title"
                        @click=""
                        router :to="item.route"
                        active-class="primary lighten-1"
                >
                    <v-list-tile-action>
                        <v-icon class="text--white">{{ item.icon }}</v-icon>
                    </v-list-tile-action>

                    <v-list-tile-content>
                        <v-list-tile-title>{{ item.title }}</v-list-tile-title>
                    </v-list-tile-content>
                </v-list-tile>
            </v-list>
        </v-navigation-drawer>

    </div>
</template>

<script>
    export default {
        name: "Navbar",
        data() {
            return {
                drawer: true,
                items: [
                    { title: 'Profil', icon: 'account_box', route: '/profile'},
                    { title: 'Tableau de bord', icon: 'dashboard', route: '/dashboard' },
                    { title: 'Courses', icon: 'lock', route: '/courses' },
                ],
                mini: true,
                right: null
            }
        }

    }
</script>

<style scoped>

</style>
