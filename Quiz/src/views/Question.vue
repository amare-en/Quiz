<script>
    import quizes from "../data/quizes.json";
    import {useRoute, useRouter} from "vue-router";
    import {RouterView} from "vue-router"
    const Route=useRoute();
    const Router=useRouter();
    //const quizId=parseInt(route.params.id);
const quiz = quizes.find(q=>q.id === parseInt(Route.params.id));
</script>
<template>
    <div>
    <h1>questions</h1>
    <p>{{quiz.questions}}</p>
    <RouterView/>
    </div>
</template>