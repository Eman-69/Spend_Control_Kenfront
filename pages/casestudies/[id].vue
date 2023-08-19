<template>
    <div class="container">
        <v-container style="margin-top: 11%;">
            <v-row>
                <v-col><v-img style="border-radius: 20px;" :src="currentCase.src" cover></v-img></v-col>
            </v-row>
            <v-row class="justify-center">
                <h1 class="mb-0"> {{ currentCase.Name }}</h1>
            </v-row>
            <v-row class="justify-center">
                <h4 class="mb-0"> {{ currentCase.Domain }}</h4>
            </v-row>
            <v-row class="justify-center">
                <h4 class="mb-7"> {{ currentCase.Year }}</h4>
            </v-row>
            <v-row>
                <v-col>
                    <h3>Description:</h3>
                    <p class="mb-5"> {{ currentCase.Description }}</p>
                </v-col>
            </v-row>
            <v-row>
                <v-col>
                    <h3>Problem:</h3>
                    <p class="mb-5"> {{ currentCase.Problem }}</p>
                </v-col>
            </v-row>
            <v-row>
                <v-col>
                    <h3>Steps:</h3>
                    <p class="mb-5"> {{ currentCase.Step }}</p>
                </v-col>
            </v-row>
            <v-row>
                <v-col>
                    <h3>Outcome:</h3>
                    <p class="mb-5"> {{ currentCase.Outcome }}</p>
                </v-col>
            </v-row>
        </v-container>
        <div id="footer" class="mt-16">
            <Footer />
        </div>

    </div>
</template>

<script setup>
var currentUrl = window.location.pathname;
currentUrl = currentUrl.replace("/casestudies/", "")

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
let currentCase
for (var i = 0; i < casestudies.length; i++) {
    if (casestudies[i].id == currentUrl) {
        currentCase = casestudies[i];
    }
}

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

h4 {
    color: rgba(255, 255, 255, 0.60);
}

h3 {
    color: white;
}

@media only screen and (max-width:951px) {
    h3 {
        text-align: center;
    }
}
</style>

