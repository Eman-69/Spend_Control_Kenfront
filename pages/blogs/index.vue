<template>
    <div class="container">
        <v-container fluid class="mt-16">
            <v-row>
               <v-col xl="4" lg="4" md="4" sm="12" cols="12" v-for="(each) in blogs" :key="each.id" class="my-10">
                    <v-card fluid max-width="400" max-height="800" class="mx-auto text-white blog-card">
                        <v-img style="border-bottom:solid 1px rgba( 255, 255, 255, 1)" class="mb-2" height="300" :src="each.src" cover></v-img>
                        <v-card-title class="text-center">{{ each.title }}</v-card-title>
                        <v-card-subtitle class="text-center mb-2">{{ each.date }}</v-card-subtitle>
                        <v-divider class="text-white mx-auto" style="border-width: 2px;" width="50%"></v-divider>
                        <v-card-text class="px-8 mb-4">
                            <div style="font-weight: 300;">{{ each.content.substring(0, 150) }}...</div>
                        </v-card-text>
                        <v-card-actions class="mb-4">
                            <NuxtLink :to="`blogs/${each.id}`" class="mx-auto text-white">
                                <v-btn variant="outlined">
                                    <span style="font-weight: 300;">Learn More</span>
                                </v-btn>
                            </NuxtLink>
                        </v-card-actions>
                    </v-card>
                </v-col>
        </v-row>
    </v-container>
    </div>
</template>

<script setup>
let blogs = [
    {
        id: 'azure-machine-learning',
        title: "Azure Machine Learning Services",
        date: "August 26, 2019",
        content: "Lorem ipsum dolor, sit amet consectetur adipisicing elit. Quisquam, aspernatur blanditiis dolor porro debitis amet? Maiores, obcaecati quia. Voluptatem, debitis. Lorem ipsum dolor sit amet consectetur adipisicing elit. Temporibus quas adipisci inventore dolores, ipsam asperiores sequi nesciunt cupiditate corrupti dolore tenetur fuga expedita nam fugiat labore consequatur error alias sit. Cupiditate, cumque dolores? Provident quibusdam, quas sapiente magni quisquam tempore sequi ex impedit minus dolores nostrum mollitia beatae dolorum possimus?",
        src: "https://cdn.vuetifyjs.com/images/cards/docks.jpg",
    },
    {
        id: 'analytics-climate-change',
        title: "Analytics and a Coming Climate",
        date: "August 21, 2019",
        content: "Quisquam, aspernatur blanditiis dolor porro debitis amet? Maiores, obcaecati quia. Voluptatem, debitis. Lorem ipsum dolor sit amet consectetur adipisicing elit. Temporibus quas adipisci inventore dolores, ipsam asperiores sequi nesciunt cupiditate corrupti dolore tenetur fuga expedita nam fugiat labore consequatur error alias sit. Cupiditate, cumque dolores? Provident quibusdam, quas sapiente magni quisquam tempore sequi ex impedit minus dolores nostrum mollitia beatae dolorum possimus?",
        src: "https://cdn.vuetifyjs.com/docs/images/cards/purple-flowers.jpg",
    },
    {
        id: 'data-science-and-a-tree',
        title: "Data Science and a Tree",
        date: "August 14, 2019",
        content: "Aspernatur blanditiis dolor porro debitis amet? Maiores, obcaecati quia. Voluptatem, debitis. Lorem ipsum dolor sit amet consectetur adipisicing elit. Temporibus quas adipisci inventore dolores, ipsam asperiores sequi nesciunt cupiditate corrupti dolore tenetur fuga expedita nam fugiat labore consequatur error alias sit. Cupiditate, cumque dolores? Provident quibusdam, quas sapiente magni quisquam tempore sequi ex impedit minus dolores nostrum mollitia beatae dolorum possimus?",
        src: "https://cdn.vuetifyjs.com/images/cards/sunshine.jpg",
    },
];
</script>

<style scoped>
.container {
  overflow-y: scroll;
  height: 100vh;
  scroll-behavior: smooth;
}
.container > * {
  height: auto;
}

.blog-card{
background: rgba( 155, 155, 155, 0.15 );
box-shadow: 0 8px 10px 0 rgba( 31, 38, 135, 0.37 );
backdrop-filter: blur( 0.5px );
-webkit-backdrop-filter: blur( 0.5px );
border-radius: 20px;
border: 1px solid rgba( 255, 255, 255, 1);
}

</style>

