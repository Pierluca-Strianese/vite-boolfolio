<script>
import axios from "axios";

export default {
    data() {
        return {
            arrProjects: [],
        };
    },
    created() {
        axios
            .get("http://127.0.0.1:8000/api/project")
            .then((response) => (this.arrProjects = response.data.data));
    },
};

</script>

<template>
    <h2> questi sono i progetti</h2>
    <ul>
        <li v-for="project in arrProjects" :key="project.id">
            {{ project.title }}
        </li>
    </ul>
</template>

<style lang="scss" scoped>
@import "bootstrap/scss/bootstrap";
</style>
