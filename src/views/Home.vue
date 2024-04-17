<template>
    <div class="home">
        <h1>Login con oauth</h1>
        <div v-if="!$auth.loading">
            <button v-if="!$auth.isAuthenticated" @click="login">Log in</button>
            <button v-if="$auth.isAuthenticated" @click="logout">Log out</button>
        </div>

    </div>
</template>

<script>
export default {
    name: "home",

    methods: {
        login() {
            this.$auth.loginWithRedirect();
        },
        logout() {
            this.$auth.logout({
                logoutParams: {
                    returnTo: window.location.origin,
                },
            });
        },
    },
};
</script>