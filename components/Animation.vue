<template>
  <div class="animecontainer">
      <img class="img" v-for="item in animeImg" :key="item.id" :id="item.id" :src="item.href" :alt="item.id"/>
  </div>
</template>

<style scoped>

.animecontainer{
  height: 100vh;
  display: grid;
  justify-items: center;
  align-items: center;
  grid-template-rows: 10vh;
  scroll-behavior: smooth;
}
.animecontainer > .img{
  display: none;
  position: relative;
  top: 50vh;
  left: 25vw;
  grid-row-start: 1;
  grid-column-start: 1;
}

@media only screen and (orientation: portrait){
.animecontainer > .img{
  position: absolute;
 width: 100vw;
 left: 0vh;
 bottom: -10vh;
}
}

</style>
<script setup lang="ts">
let animeImg=ref([
  {id:"h1",href:"/images/1.svg"},
  {id:"h2",href:"/images/2.svg"},
  {id:"h3",href:"/images/3.svg"},
  {id:"h4",href:"/images/4.svg"},
  {id:"h5",href:"/images/5.svg"},
  {id:"h6",href:"/images/6.svg"},
  {id:"h7",href:"/images/7.svg"},
  {id:"h8",href:"/images/8.svg"},
  {id:"h9",href:"/images/9.svg"},
  {id:"h10",href:"/images/10.svg"},
  {id:"h11",href:"/images/11.svg"},
  {id:"h12",href:"/images/12.svg"},
  {id:"h13",href:"/images/13.svg"},
  {id:"h14",href:"/images/14.svg"},
  {id:"h15",href:"/images/15.svg"},
  {id:"h16",href:"/images/16.svg"},
  {id:"h17",href:"/images/17.svg"},
  {id:"h18",href:"/images/18.svg"},
  {id:"h19",href:"/images/19.svg"},
  {id:"h20",href:"/images/20.svg"},
  {id:"h21",href:"/images/21.svg"},
  {id:"h22",href:"/images/22.svg"},
  {id:"h23",href:"/images/23.svg"},
  {id:"h24",href:"/images/24.svg"},
  {id:"h25",href:"/images/25.svg"},
  {id:"h26",href:"/images/26.svg"},
  {id:"h27",href:"/images/27.svg"},
  {id:"h28",href:"/images/28.svg"},
  {id:"h29",href:"/images/29.svg"},
  {id:"h30",href:"/images/30.svg"},
  {id:"h31",href:"/images/31.svg"},
  {id:"h32",href:"/images/32.svg"},
  {id:"h33",href:"/images/33.svg"},
  {id:"h34",href:"/images/34.svg"},
  {id:"h35",href:"/images/35.svg"},
  {id:"h36",href:"/images/36.svg"},
  {id:"h37",href:"/images/37.svg"},
  {id:"h38",href:"/images/38.svg"},
  {id:"h39",href:"/images/39.svg"},
  {id:"h40",href:"/images/40.svg"},
  {id:"h41",href:"/images/41.svg"},
  {id:"h42",href:"/images/42.svg"},
  {id:"h43",href:"/images/43.svg"},
  {id:"h44",href:"/images/44.svg"},
  {id:"h45",href:"/images/45.svg"},
  {id:"h46",href:"/images/46.svg"},
  {id:"h47",href:"/images/47.svg"},
  {id:"h48",href:"/images/48.svg"},
  {id:"h49",href:"/images/49.svg"},
  {id:"h50",href:"/images/50.svg"},
  {id:"h51",href:"/images/51.svg"},
  {id:"h52",href:"/images/52.svg"},
  {id:"h53",href:"/images/53.svg"},
  {id:"h54",href:"/images/54.svg"},
  {id:"h55",href:"/images/55.svg"},
  {id:"h56",href:"/images/56.svg"},
  {id:"h57",href:"/images/57.svg"},
  {id:"h58",href:"/images/58.svg"},
  {id:"h59",href:"/images/59.svg"},
  {id:"h60",href:"/images/60.svg"},
  {id:"h61",href:"/images/61.svg"},
  {id:"h62",href:"/images/62.svg"},
  {id:"h63",href:"/images/63.svg"},

]);
onMounted(() => {
    let h1=document.getElementById("h1");
    h1.style="display:block";
})
let curr=ref(0);
let props = defineProps({
scrollPer: {
  type: Number,
  required: true,
},
});
const { $anime } = useNuxtApp();
let i=ref(0);
let j=ref(0);

let temp=ref(null);
let t=ref(null);
watch(props, (val, oldVal) => {
  console.log(props.scrollPer);
  for(j=1;j<=63;j++)
  {
    temp=`h`+(j);
    t=document.getElementById(temp); 
    if(t.style.display=="block")
      console.log("nigga"+j);
  }
  t.style="display:none";
//   ellipsetl.seek(ellipsetl.duration * (props.scrollPer / 100));
if(props.scrollPer<=1)
{
    let h1=document.getElementById("h1");
    h1.style="display:block";
}
if(props.scrollPer>1&&props.scrollPer<=20)
{
//   let h1=document.getElementById("h1");
//   h1.style="display:none";
  // let next1=document.getElementById("h1");
  // let next2=document.getElementById("h11");
  // let next3=document.getElementById("h13");
  // next1.style="display:none";
  // next2.style="display:none";
  // next3.style="display:none";
  t.style="display:none";
  curr=Math.round(((props.scrollPer)/20)*11);
  for(i=1;i<=63;i++)
  {
  console.log(curr,i);
      temp=`h`+(i);
      t=document.getElementById(temp);   
      t.style="display:none";
      if(i==curr)
      {
          t.style="display:block";
          continue;
      }
      else
      {
        t.style="display:none";
      }

  }
}
else if(props.scrollPer>20&&props.scrollPer<=40)
{  

  let next1=document.getElementById("h11");
  next1.style="display:none";
  t.style="display:none";
  curr=Math.round(((props.scrollPer)/40)*26);
  for(i=1;i<=63;i++)
  {
  console.log(curr,i);
      temp=`h`+(i);
      t=document.getElementById(temp);   
      t.style="display:none";
      if(i==curr)
      {
          t.style="display:block";
          continue;
      }
      else
      {
        t.style="display:none";
      }

  }
}
else if(props.scrollPer>40&&props.scrollPer<=61)
{ 
  let next1=document.getElementById("h11");
  let next2=document.getElementById("h13");
  let next3=document.getElementById("h26");
  next1.style="display:none";
  next2.style="display:none";
  next3.style="display:none"; 
  t.style="display:none";
  curr=Math.round(((props.scrollPer)/61)*39);
  for(i=1;i<=63;i++)
  {
  console.log(curr,i);
      temp=`h`+(i);
      t=document.getElementById(temp);   
      t.style="display:none";
      if(i==curr)
      {
          t.style="display:block";
          continue;
      }
      else
      {
        t.style="display:none";
      }

  }
}
else if(props.scrollPer>61&&props.scrollPer<=100)
{  

  let next1=document.getElementById("h39");
  next1.style="display:none";
  t.style="display:none";
  curr=Math.round(((props.scrollPer)/100)*63);
  for(i=1;i<=63;i++)
  {
  console.log(curr,i);
      temp=`h`+(i);
      t=document.getElementById(temp);   
      t.style="display:none";
      if(i==curr)
      {
          t.style="display:block";
          continue;
      }
      else
      {
        t.style="display:none";
      }

  }
}
else{
  
  t.style="display:none"; 
}
});
</script>

