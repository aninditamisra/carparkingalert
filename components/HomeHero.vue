<template>
    <v-container fluid fill-height class="home-hero" style="max-height: 100vh;">
        <v-layout justify-center align-center column pa-5>
            <div class="display-1 font-weight-black white--text text-xs-center">Welcome to Parking Notification</div>
            <v-btn color="success" to="/menu">Parking Availability Status</v-btn>
            <div class="display-1 font-weight-black white--text text-xs-center">Sign In / Join to View Analytics</div>
                <v-btn color="success" to="/sign-in">Sign In</v-btn>
                <v-btn color="info" to="/join">Join</v-btn>
        </v-layout>
    </v-container>
</template>

<script>
export default {
    name: 'HomeHero'
};
</script>

<style scoped>
.home-hero { background: url('https://cloud.funda.nl/valentina_media/097/489/858_1440x960.jpg'); 
             background-size: cover; 
             width: 100%; 
             height: 100%; }
</style>
