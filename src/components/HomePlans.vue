<template>
    <v-container grid-list-lg>
        <v-layout align-center justify-center row fill-height class="parking-plats">
            <v-flex xs12 sm12 md4>
                <v-card>
                    <v-responsive>
                        <v-img src="https://3oekw43riutk1mnux5hvlj11-wpengine.netdna-ssl.com/wp-content/uploads/2017/12/parking-lot-accident.jpeg" height="500px">
                            <v-container fill-height fluid>
                                <v-layout fill-height>
                                    <v-flex xs12 align-end flexbox>
                                        <span class="headline black--text"></span>
                                        <div class="display-1 font-weight-black white--text text-xs-center">Available Spots</div>
                                        <div class="display-4 font-weight-black white--text text-xs-center">{{counter}}</div>
                                     </v-flex>
                                </v-layout>
                            </v-container>
                        </v-img>
                    </v-responsive>
                    
                        <v-btn outline block color="green" @click="dashboardview">View Analytics</v-btn>
                     
                </v-card>
            </v-flex>

          </v-layout>
    </v-container>
</template>

<script>
    export default {
        name: 'HomePlans',
        data() {
            return {
                total_count: {
                    score: 75
                },
                spots_taken: {
                    score: 11
                },
                counter: 0
            }
        },

        computed: {
            isAuthenticated() {
                return this.$store.getters.isAuthenticated;
            }
        },
        watch: {

        },
        methods: {
            logout() {
                this.$store.dispatch('userSignOut');
            },
            dashboardview() {
                if (this.$store.getters.isAuthenticated == true)
                    this.$router.replace('/about')
                else
                    this.$router.replace('/')
            },
            availability() {
                var available_spot = 0;
                available_spot = (this.total_count.score - this.spots_taken.score);
                //console.log(available_spot);
                this.counter = available_spot;
            }
        },
        beforeMount() {
            this.availability();
        }
    };
</script>

<style scoped>

    a {
        color: white;
        text-decoration: none;

    }
</style>

