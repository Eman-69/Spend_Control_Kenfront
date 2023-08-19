<template>
    <div class="container">
            <v-container fluid class="mt-16">
                <v-row>
                    <v-col xl="4" lg="4" md="4" sm="12" cols="12" v-for="(each) in casestudies" :key="each.id" class="my-10">
                        <v-card max-width="400" max-height="800" class="mx-auto text-white casestudy-card" >
                            <v-img style="border-bottom:solid 1px rgba( 255, 255, 255, 1)" class="mb-2" height="300" :src="each.src" cover></v-img>
                            <v-card-title class="text-center">{{ each.Name }}</v-card-title>
                            <v-card-subtitle class="text-center">{{ each.Domain }}</v-card-subtitle>
                            <v-card-subtitle class="text-center mb-2">-{{ each.Year }}</v-card-subtitle>
                            <v-divider class="text-white mx-auto" style="border-width: 2px;" width="50%"></v-divider>
                            <v-card-text class="px-8 mb-4">
                                <div style="font-weight: 300;">{{ each.Description.substring(0, 150) }}...</div>
                            </v-card-text>
                            <v-card-actions>
                                <NuxtLink :to="`casestudies/${each.id}`" class="mx-auto text-white">
                                    <v-btn variant="outlined" class="mb-4">
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
let casestudies = [
    {
        Name: "Rathna Constructions",
        id: "rathna-constructions",
        Description:
            "Lorem ipsum dolor sit amet consectetur. Donec nisl ut integer diam. Massa ultricies penatibus id tristique ut pharetra enim dolor venenatis.",
        Problem:
            "Lorem ipsum dolor sit amet consectetur. Amet mus scelerisque id lacus egestas. Phasellus augue nulla tristique facilisis in amet porta ipsum. Senectus mattis ultrices nisi nec adipiscing volutpat quam eu. Scelerisque nisi vulputate elit pulvinar at diam tellus. Ac proin sapien interdum adipiscing morbi nibh risus nullam. Velit metus tortor enim quisque egestas ullamcorper bibendum morbi ut. Sed vestibulum tristique nulla sit. Lectus ullamcorper non mi tempor risus faucibus elit. Eu consequat leo egestas neque dui condimentum ultrices.",
        Step: "Lorem ipsum dolor sit amet consectetur. Amet mus scelerisque id lacus egestas. Phasellus augue nulla tristique facilisis in amet porta ipsum. Senectus mattis ultrices nisi nec adipiscing volutpat quam eu. Scelerisque nisi vulputate elit pulvinar at diam tellus. Ac proin sapien interdum adipiscing morbi nibh risus nullam. Velit metus tortor enim quisque egestas ullamcorper bibendum morbi ut. Sed vestibulum tristique nulla sit. Lectus ullamcorper non mi tempor risus faucibus elit. Eu consequat leo egestas neque dui condimentum ultrices.",
        Outcome:
            "Lorem ipsum dolor sit amet consectetur. Amet mus scelerisque id lacus egestas. Phasellus augue nulla tristique facilisis in amet porta ipsum. Senectus mattis ultrices nisi nec adipiscing volutpat quam eu. Scelerisque nisi vulputate elit pulvinar at diam tellus. Ac proin sapien interdum adipiscing morbi nibh risus nullam. Velit metus tortor enim quisque egestas ullamcorper bibendum morbi ut. Sed vestibulum tristique nulla sit. Lectus ullamcorper non mi tempor risus faucibus elit. Eu consequat leo egestas neque dui condimentum ultrices.",
        Year: "2022",
        Domain: "Website Development",
        src: "https://cdn.vuetifyjs.com/images/cards/docks.jpg",
    },
    {
        Name: "Cine Galaxy",
        id: "cine-galaxy",
        Description:
            "Lorem ipsum dolor sit amet consectetur. Donec nisl ut integer diam. Massa ultricies penatibus id tristique ut pharetra enim dolor venenatis.",
        Problem:
            "Lorem ipsum dolor sit amet consectetur. Amet mus scelerisque id lacus egestas. Phasellus augue nulla tristique facilisis in amet porta ipsum. Senectus mattis ultrices nisi nec adipiscing volutpat quam eu. Scelerisque nisi vulputate elit pulvinar at diam tellus. Ac proin sapien interdum adipiscing morbi nibh risus nullam. Velit metus tortor enim quisque egestas ullamcorper bibendum morbi ut. Sed vestibulum tristique nulla sit. Lectus ullamcorper non mi tempor risus faucibus elit. Eu consequat leo egestas neque dui condimentum ultrices.",
        Step: "Lorem ipsum dolor sit amet consectetur. Amet mus scelerisque id lacus egestas. Phasellus augue nulla tristique facilisis in amet porta ipsum. Senectus mattis ultrices nisi nec adipiscing volutpat quam eu. Scelerisque nisi vulputate elit pulvinar at diam tellus. Ac proin sapien interdum adipiscing morbi nibh risus nullam. Velit metus tortor enim quisque egestas ullamcorper bibendum morbi ut. Sed vestibulum tristique nulla sit. Lectus ullamcorper non mi tempor risus faucibus elit. Eu consequat leo egestas neque dui condimentum ultrices.",
        Outcome:
            "Lorem ipsum dolor sit amet consectetur. Amet mus scelerisque id lacus egestas. Phasellus augue nulla tristique facilisis in amet porta ipsum. Senectus mattis ultrices nisi nec adipiscing volutpat quam eu. Scelerisque nisi vulputate elit pulvinar at diam tellus. Ac proin sapien interdum adipiscing morbi nibh risus nullam. Velit metus tortor enim quisque egestas ullamcorper bibendum morbi ut. Sed vestibulum tristique nulla sit. Lectus ullamcorper non mi tempor risus faucibus elit. Eu consequat leo egestas neque dui condimentum ultrices.",
        Year: "2022",
        Domain: "Website Development",
        src: "https://picsum.photos/500/300?image=232",
    },
];
</script>

<style scoped>
.container {
    overflow-y: scroll;
    height: 100vh;
    scroll-behavior: smooth;
}

.container>* {
    height: auto;
}
.casestudy-card{
    background: rgba( 155, 155, 155, 0.15 );
box-shadow: 0 8px 10px 0 rgba( 31, 38, 135, 0.37 );
backdrop-filter: blur( 0.5px );
-webkit-backdrop-filter: blur( 0.5px );
border-radius: 20px;
border: 1px solid rgba( 255, 255, 255, 1);
}
</style>

