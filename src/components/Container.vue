<template>
    <div id="container">
        <div class="container">
            <img class="img-avatar" src="https://avatars.githubusercontent.com/u/78513587?v=4"
                alt="Avatar de DeveloperCanver">
            <h3>Proyectos</h3>
            <hr>
            <loading v-if="load" />
            <div class="cards" v-for="project in projects" :key="project.id">
                <!-- name la vareiable que se envia a Card -->
                <Card 
                :name="project.name" 
                :description="project.description" 
                :author="project.owner.login"
                :url="project.html_url"
                :homepage="project.homepage"
                 />
                <!-- datos enviando a la clase de cards -->
            </div>
        </div>
    </div>

</template>

<script>
    import Card from './Card.vue'
    import Loading from './Loading.vue';

    export default {
        data() {
            return {
                projects: null,
                load: false,
                imgAvatar: String,
            }
        },
        components: {//componentes es para traer mas .vue o contenidos y enviar mas variables
            Card,
            Loading,
        },
        mounted() {
            this.getProjects();
        },
        methods: {
            async getProjects() {
                this.load = true; //verdadeo para icon loadin
                const res = await fetch("https://api.github.com/users/developerCanver/repos");
                const data = await res.json();

                //1. tenermos la informacion de la api apra la pasamos data() -> projects
                this.load = false; // cando haya cargado se desaparesca ´por false
                this.projects = data;
                // console.log(this.projects[0]);
                // console.log(this.projects[0].owner.avatar_url);
                // this.projects[0].owner.avatar_url=imgAvatar;

            },
        },
    };
</script>


<style scoped>
    .cards {
        display: flex;
        flex-wrap: wrap;
        justify-content: center;

    }

    .container {

        border: solid 1px #eee;
        box-shadow: 1px 1px 4px #333;
        text-align: center;

    }

    .img-avatar {
        width: 150px;
        border-radius: 150px;
        height: 150px;
        box-shadow: 1px 1px 4px #333;
    }
</style>