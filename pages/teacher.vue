<template>
    <div class="teacher">
        <headerTab></headerTab>
        <h3>这是老师列表页</h3>
        <ul>
            <li v-for="item in teacherList" :key="item.id">
                <nuxt-link :to="`/teacher/${item.id}`">{{item.name}}</nuxt-link>
            </li>
        </ul>
        <nuxt-child></nuxt-child>
    </div>
</template>

<script>
import headerTab from "~/layouts/headerTab";

    export default{
        data() {
            return {
                teacherList:[
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