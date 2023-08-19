<template>
    <div class="container">
        <v-container style="margin-top: 11%;">
            <v-row>
                <v-col xl="12" lg="12" md="12" sm="12" cols="12">
                    <v-img :src="currentBlog.src" cover style="border-radius: 20px;"></v-img>
                </v-col>
            </v-row>
            <v-row>
                <v-col xl="12" lg="12" md="12" sm="12" cols="12">
                    <h1 class="mb-5"> {{ currentBlog.title }}</h1>
                    <p class="mb-5"> {{ currentBlog.content.description }}</p>
                    <ul style="list-style-type: circle;">
                        <li style="
                              margin-left: 10px;
                              list-style-type: circle; 
                              font-weight: 300;
                              color: rgba(255, 255, 255, 0.60); " v-for="(n, k) in currentBlog.content.steps" :key="k">
                            {{ k + 1 }}. <span style="color: rgba(255, 255, 255, 0.60);" v-html="n"></span>
                        </li>
                    </ul>
                    <h3>- {{ currentBlog.date }}</h3>
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
currentUrl = currentUrl.replace("/blogs/", "")
let blogs = [
    {
        id: 'azure-machine-learning',
        title: "Azure Machine Learning Services",
        date: "August 26, 2019",
        content: {
            description: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Tenetur minus atque aut qui mollitia tempora corporis autem adipisci? Hic voluptatum consequatur necessitatibus saepe nam accusantium illo sed sunt explicabo ut ea qui, veritatis ipsa blanditiis quibusdam laborum sit nesciunt. Nihil debitis corporis ad id dignissimos commodi recusandae iste nam minima.",
            steps: ["Develop machine learning training scripts in Python.", "Create and configure a compute target.", "Create and configure a compute target.", "Query the experiment for logged metrics from the current and past runs. If the metrics don’t indicate a desired outcome, loop back to step 1 and iterate on your scripts.", "After a satisfactory run is found, register the persisted model in the model registry.", "Develop a scoring script.", "Create an image and register it in the image registry.", "Deploy the image as a web service in Azure."]
        },
        src: "https://cdn.vuetifyjs.com/images/cards/docks.jpg",
    },
    {
        id: 'analytics-climate-change',
        title: "Analytics and a Coming Climate",
        date: "August 21, 2019",
        content: {
            description: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Fugiat voluptatum, minima saepe ratione harum assumenda, provident et ea cumque ut error enim tenetur, corporis dolorem vero temporibus sint in quos impedit inventore voluptates alias? Eum enim consectetur, dolorum maiores iusto, consequatur aliquid commodi dolore eos totam, optio obcaecati? Esse laboriosam ipsa sunt modi vitae delectus, consectetur omnis, perspiciatis officia et quos velit consequuntur, itaque dolor! Sunt, nulla? Qui aut molestias est sit id, ratione assumenda? Consequuntur doloremque perferendis recusandae? Laudantium error, fuga maxime voluptatibus illum asperiores hic eum dicta ipsam. Suscipit corrupti culpa et neque consectetur. Doloremque minima facilis molestiae delectus? Nostrum, possimus! Tempore quidem explicabo, laborum ullam ad quae. Vitae ex nemo ducimus dicta iure provident dolorem sint soluta molestias dolore adipisci, rem natus delectus, dolor praesentium non aliquam perspiciatis vel at a. Quisquam reprehenderit, quod qui quasi nihil quas sunt ullam recusandae, totam iure impedit cumque quo quae accusantium eos veritatis ipsum nemo debitis a! Earum consequuntur maxime nostrum fugit dignissimos, odit possimus tempora velit dolorum illum accusantium necessitatibus doloremque quaerat assumenda sint cupiditate sequi provident molestiae dolor quod rem unde? Fuga nemo aspernatur porro ut enim maxime modi perspiciatis quam fugiat suscipit inventore deleniti vitae, libero corrupti reiciendis veniam iusto eligendi itaque officiis voluptate. Non sequi rem id, ab maiores dolores distinctio cupiditate nemo recusandae praesentium perferendis nobis, nesciunt dolorem cum tenetur beatae deleniti! Ex aspernatur accusamus odit quod beatae? Provident voluptatem molestias aliquam animi. Ullam aspernatur commodi nulla numquam sed asperiores accusantium velit quas veniam, doloremque excepturi eum cupiditate, optio eius aperiam deserunt accusamus saepe. Assumenda odio illo unde consectetur nisi expedita dicta, commodi non repellendus magnam blanditiis, in dolore nostrum totam, tempore ex aliquam aspernatur rerum? Asperiores, perspiciatis reiciendis! Consequuntur perferendis non, ipsum repellendus ab, architecto, perspiciatis ullam facilis natus distinctio deserunt repudiandae magni odio?",
            steps: ["Lorem ipsum, dolor sit amet consectetur adipisicing elit. Vitae, quisquam?", " Quis ducimus, magnam aliquid quasi possimus beatae facilis delectus vitae tempore neque!", "laboriosam explicabo aliquid at ipsum vel quam temporibus provident numquam soluta adipisci officia voluptas earum?"]
        },
        src: "https://cdn.vuetifyjs.com/docs/images/cards/purple-flowers.jpg",
    },
    {
        id: 'data-science-and-a-tree',
        title: "Data Science and a Tree",
        date: "August 14, 2019",
        content: {
            description: "Lorem ipsum dolor sit amet consectetur, adipisicing elit. Magnam enim natus qui, quasi debitis soluta magni voluptatibus nulla dicta maiores iusto et? Nisi ratione, officia assumenda dicta deserunt voluptatibus quasi illo. Molestias quod aspernatur cupiditate.",
            steps: ["Lorem ipsum, dolor sit amet consectetur adipisicing elit. Vitae, quisquam?", " Quis ducimus, magnam aliquid quasi possimus beatae facilis delectus vitae tempore neque!", "laboriosam explicabo aliquid at ipsum vel quam temporibus provident numquam soluta adipisci officia voluptas earum?"],
        },
        src: "https://cdn.vuetifyjs.com/images/cards/sunshine.jpg",
    },
];
let currentBlog
for (var i = 0; i < blogs.length; i++) {
    if (blogs[i].id == currentUrl) {
        currentBlog = blogs[i];
    }
}

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

h3{
    color: white;
    text-align: right;
}
</style>

