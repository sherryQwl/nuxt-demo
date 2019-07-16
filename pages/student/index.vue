<template>
    <div class="student">
        <headerTab></headerTab>
        <h3>这是学生列表页</h3>
        <ul>
            <li v-for="item in studentList" :key="item.id">
                <nuxt-link :to="`student/${item.id}`">{{item.name}}</nuxt-link>
            </li>
        </ul>
    </div>
</template>

<script>
import headerTab from "~/layouts/headerTab";
    export default{
        data() {
            return {
                studentList:[
                    {name:'Jack1',id:1},
                    {name:'Jack2',id:2},
                    {name:'Jack3',id:3}
                ]
            }
        },
        components: {
            headerTab
        }
    }
</script>