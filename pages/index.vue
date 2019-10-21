<template>
  <div>
    <div class="con-type-example">
      <vs-navbar :type="type" v-model="activeItem" class="nabarx">

        <div slot="title">
          <vs-navbar-title>
            Type {{type}}
          </vs-navbar-title>
        </div>

        <vs-navbar-item index="0" active>
          <a href="#">Home</a>
        </vs-navbar-item>
        <vs-navbar-item index="1">
          <a href="#">News</a>
        </vs-navbar-item>
        <vs-navbar-item index="2">
          <a href="#">Update</a>
        </vs-navbar-item>
      </vs-navbar>
    </div>
    <div class="container">
      <div>
        <logo />
        
        <h1 class="title">
          VueSax
        </h1>
        <h2 class="subtitle">
          Nuxt.js + VueSax
        </h2>
        <vs-progress indeterminate color="primary"></vs-progress>
        <vs-row vs-type="flex" vs-align="center" vs-justify="space-around">
          <vs-col vs-w="1"></vs-col>
          <vs-col vs-w="5">
            <vs-button color="primary" type="flat" size="large" icon="cast" @click="openLoading('https://nuxtjs.org/')">
              Nuxt.js Documentation
            </vs-button>
          </vs-col>
          <vs-col vs-w="5">
            <vs-button color="danger" type="gradient" size="large" icon="favorite" :icon-after="true" @click="openLoading('https://github.com/nuxt/nuxt.js')">
              Nuxt.js GitHub
            </vs-button>
          </vs-col>
          <vs-col vs-w="1"></vs-col>
        </vs-row>
        <vs-progress indeterminate color="success"></vs-progress>
        <vs-row vs-type="flex" vs-align="center" vs-justify="space-around">
          <vs-col vs-w="1"></vs-col>
          <vs-col vs-w="5">
            <vs-button color="success" type="filled" size="large" icon="emoji_emotions" @click="openLoading('https://lusaxweb.github.io/vuesax/development/#quick-start-cdn')">
              VueSax Documentation
            </vs-button>
          </vs-col>
          <vs-col vs-w="5">
            <vs-button color="warning" type="border" size="large" icon="adb" :icon-after="true" @click="openLoading('https://github.com/lusaxweb/vuesax')">
              VueSax GitHub
            </vs-button>
          </vs-col>
          <vs-col vs-w="1"></vs-col>
        </vs-row>
        <vs-progress indeterminate color="danger"></vs-progress>
      </div>
    </div>
    <div 
      style="
        margin: 0 auto;
        width: 60%;
        margin-top: -150px;
        margin-bottom: 150px;
      ">
      <vs-collapse accordion >
        <vs-collapse-item>
          <div slot="header">
            Collapse item
          </div>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Quisque rhoncus eros tortor, non fringilla lectus cursus et. Fusce vel nisi ante. Aliquam sit amet lectus pharetra, luctus mi sed, aliquet felis. Mauris a tortor viverra, ornare tellus in, consectetur leo.
          <br><br>
          Etiam nec nunc nec nisl luctus tincidunt efficitur vitae elit. Vestibulum iaculis nibh commodo neque ultrices lobortis. Cras magna massa, pretium vitae mattis varius, pharetra nec massa. Aliquam ac ex enim. Quisque consequat dui libero, vel blandit lorem porttitor sit amet. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia Curae; Nullam sed lobortis nisl, quis eleifend metus.
        </vs-collapse-item>
        <vs-collapse-item>
          <div slot="header">
            Collapse item 2
          </div>
          Nunc auctor et leo vitae suscipit. Nullam aliquet purus scelerisque enim hendrerit tristique. Maecenas tincidunt dui arcu, a aliquet nisl venenatis vitae. Praesent mauris ligula, porta at maximus ac, rutrum vitae sapien. Donec a sapien id erat dapibus dignissim sodales in est. Donec gravida dapibus sapien at sollicitudin. Maecenas iaculis quam ex,
          <br><br>
          eu aliquam erat sagittis eget. Suspendisse mollis felis nec ipsum vehicula, at posuere libero viverra. Nam hendrerit dapibus eleifend. Aliquam elit nulla, tincidunt pellentesque enim mollis, consectetur placerat enim. Integer condimentum tristique ante et ullamcorper. Mauris placerat pretium ex. Nam aliquam sed tortor sit amet
          <br><br>
          efficitur. Mauris quis faucibus nulla. Pellentesque egestas non ipsum vel maximus.
        </vs-collapse-item>
        <vs-collapse-item >
          <div slot="header">
            Collapse item 3
          </div>
          Suspendisse aliquet condimentum diam, sed aliquam nisl dapibus et. Aliquam euismod ullamcorper dolor eu
        </vs-collapse-item>
        <vs-collapse-item>
          <div slot="header">
            Collapse item 4
          </div>
          Suspendisse aliquet condimentum diam, sed aliquam nisl dapibus et. Aliquam euismod ullamcorper dolor eu imperdiet. Nullam eget odio at magna gravida suscipit sed vestibulum odio. Maecenas porta elit vel lectus molestie, eget aliquam enim feugiat. Vivamus nec faucibus nisl. Nunc venenatis tempus finibus.
        </vs-collapse-item>
      </vs-collapse>
    </div>
  </div>
</template>

<script>
import Logo from '~/components/Logo.vue'

export default {
  components: {
    Logo
  },
  data:()=>({
    activeItem: 0,
    type: 'gradient',
    types:[
      'default',
      'point',
      'radius',
      'corners',
      'border',
      'sound',
      'material',
    ],
  }),
  methods:{
    openLoading(link){
      this.$vs.loading({
        type: this.typeLoading,
        background:'rgb(255, 255, 255)',
        color:'rgb(0, 0, 255)',
      })
      setTimeout( ()=> {
        window.location.href = link 
      }, 1000);
    }
  },
  computed:{
    typeLoading(){
      return this.types[Math.floor(Math.random() * 7)]
    }
  }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
