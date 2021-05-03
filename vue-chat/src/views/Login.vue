<template>
    <div class="login">
        <b-jumbotron header="Chat App com Vue"
                     lead="Usando SendBird & Bootstrap-Vue"
                     bg-variant="Info"
                     text-variant="white">
        <p>For me information visit website</p>      
        <b-btn target="_blank" href="https://sendbird.com/docs/chat/v3/javascript/getting-started/about-chat-sdk">More Info</b-btn>           
        </b-jumbotron>
        <b-container>
            <b-row>
                <b-col lg="4" md="3"></b-col>
                <b-col lg="4" md="6">
                    <LoginForm />
                </b-col>
                <b-col lg="4" md="3"></b-col>
            </b-row>
        </b-container>
    </div>
</template>


<script>
    import LoginForm from '../components/LoginForm.vue';

    export default {
        name: 'login',
        components: {
            LoginForm,
        },
    };
</script>
