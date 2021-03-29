
<template>
    <div class="card">
        <div class="card-header">Profile</div>
        <div class="media" style="padding:5px;">
            <div class="media-left media-top">
                <img :src="src" :alt="name" class="media-object" style="width:60px;padding:5px;">
            </div>
            <div class="media-body">
                <h4 class="media-heading">{{ name }}</h4>
                <p>Lorem ipsum...</p>
            </div>
        </div>
    </div>
</template>
<script>
    export default {

        data() {
            return {
                name: '',
                src: ''
            }
        },

        mounted() {
            axios.get('/api/users')
                .then(response => {
                this.name = response.data.name;
                this.src = response.data.src;
            });
        }

    }
</script>