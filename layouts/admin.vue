<template>
    <v-app>
        <v-layout row wrap>
            <v-navigation-drawer permanent expand-on-hover>
                <v-list>
                    <v-list-item class="px-2">
                        <v-list-item-avatar>
                            <v-img src="https://randomuser.me/api/portraits/women/85.jpg"></v-img>
                        </v-list-item-avatar>
                    </v-list-item>
    
                    <v-list-item link>
                        <v-list-item-content>
                            <v-list-item-title class="text-h6">
                                Admin
                            </v-list-item-title>
                        </v-list-item-content>
                    </v-list-item>
                </v-list>
                <v-divider>
                </v-divider>

                <v-list nav dense>
                    <v-list-item link>
                        <v-list-item-icon>
                            <v-icon>mdi-account-multiple</v-icon>
                        </v-list-item-icon>
                        <v-list-item-title>Student</v-list-item-title>
                    </v-list-item>
                    <v-list-item link>
                        <v-list-item-icon>
                            <v-icon>mdi-account-multiple</v-icon>
                        </v-list-item-icon>
                        <v-list-item-title>Teacher</v-list-item-title>
                    </v-list-item>
                    <v-list-item link>
                        <v-list-item-icon>
                            <v-icon>mdi-folder</v-icon>
                        </v-list-item-icon>
                        <v-list-item-title>Shared with me</v-list-item-title>
                    </v-list-item>
                    <v-list-item link>
                        <v-list-item-icon>
                            <v-icon>mdi-star</v-icon>
                        </v-list-item-icon>
                        <v-list-item-title>Starred</v-list-item-title>
                    </v-list-item>
                </v-list>
            </v-navigation-drawer>
            <v-main style="height: 500px;">
                <v-card-text class="pa-12">
                    <nuxt/>
                </v-card-text>
            </v-main>
        </v-layout>
    </v-app>
</template>
<script>
export default {
    //
}
</script>