<template>
  <div id="top">
    <div class="page-head">
      <container class="top-content d-lg-flex flex-row justify-content-center" >
          <div>
            <b-img center class="mt-5 fade" v-bind="selfImage" rounded="circle"></b-img>
          </div>
        <div class="greet d-flex flex-column justify-content-center mt-4 mt-lg-5 ml-lg-5">
          <div>
            <div class="typing-text anim-typewriter mx-auto mb-5 ml-lg-3 text-monospace" >Hello World!</div>
            <div class="info d-flex flex-column align-items-lg-start mx-3">
              <div>ご覧いただきありがとうございます！</div>
              <div>こちらはコーディング大好きな開発者、</div>
              <div>N N のポートフォリオサイトです！</div>
            </div>
          </div>
        </div>
      </container>
    </div>
    <Footer class="mt-5"/>
  </div>
</template>

<style scoped>
.typing-text {
    position: relative;
    max-width: 14.5rem;
    border-right: 2px solid rgba(0,0,0,.75);
    font-size: 2rem;
    line-height: 2.8rem;
    white-space: nowrap;
    overflow: hidden;
}

/*animation settings*/
.anim-typewriter{
  animation: typewriter 1.5s steps(12) 2.5s 1 normal both,
 blinkTextCursor 900ms steps(44) infinite normal;
}
/*typewriter animation*/
@keyframes typewriter{
  from{width: 0;}
  to{width: 14.5rem;}
}
/*cursol animation*/
@keyframes blinkTextCursor{
  from{border-right-color: rgba(0,0,0,.75);}
  to{border-right-color: transparent;}
}
</style>

<script>
import Footer from '@/components/Footer.vue'

export default {
  name: 'Top',
  components: {
    Footer
  },
  el: '#top',
  data() {
    return {
      selfImage: {
        src: require('@/assets/sakura.jpg'),
        width: 250,
        height: 250
      }
    }
  }
}
</script>
