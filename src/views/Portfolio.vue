<template function>
  <div id="portfolio">
    <h2 class="text-monospace page-head">Portfolio</h2>
    <div class="info">N N の制作物の解説です！</div>
    <div class="d-flex flex-wrap justify-content-around mx-lg-5 my-4">
      <div v-for="( product, i) in products" :key="i" class="d-flex flex-column align-items-center">
        <b-card
          border-variant="secondary"
          header-text-variant="white"
          header-bg-variant="dark"
          header-class="card-header"
          v-bind="product"
          style="max-width: 50em;"
          class="my-4 text-center">
            <b-row no-gutters>
              <b-col md="6" class="mx-3">
                <b-card-img :src="product.src" style="max-width: 27.6rem;" class="rounded-1 my-4 fade"></b-card-img>
              </b-col>
              <b-col>
                <b-card-text class="m-3 text-left" style="white-space: pre-line;">
                  {{ product.text }}
                </b-card-text>
              </b-col>
            </b-row>
            <div class="d-flex justify-content-center my-4">
              <b-button pill :href="product.href" size="lg" class="text-monospace button-link px-4">{{ product.link }}</b-button>
            </div>
        </b-card>
      </div>
    </div>
    <Footer/>
  </div>
</template>

<style lang="scss" scoped>
.button-link {
  background-color: #f7be16;
  border:  none;
  transition: .4s;

  &:hover {
    background-color: #7a4d1d;
  }
}

</style>

<script>
// @ is an alias to /src
import Footer from '@/components/Footer.vue'

export default {
  name: 'Portfolio',
  components: {
    Footer
  },
  el: "#portofolio",
  data() {
    return {
      products: [
        { header: '今ご覧のポートフォリオサイト',
            'sub-title':'制作環境：Vue.js',
            src: require('@/assets/myportfolio.jpg'),
            text:
              'フロントエンド技術の幅を広げるために、Vue.jsの環境構築とテスト開発を兼ねて2週間ほどで制作。Vue Routerを用いてSPA形式にしています。デザインはBootstrapをベースにSCSSでカスタム。画面遷移の心地よさを特に意識して調整しました。\n\n【FW】\nVue2.0/BootstrapVue\n【利用スキル補足】\nNode.js/npm/GitHub',
            href: '/',
            link: '→ Top'
        },
        { header: 'レガシー＋スクラッチなサイト',
            'sub-title':'制作環境：HTML/SCSS/JavaScript',
            src: require('@/assets/cytal2.jpg'),
            text:
              'フロントエンド知識の基礎整理のために3週間ほどで制作。デザインは既存の他サイトを参考にしています。あえてCMSやJSFWを使わずに、HTML,SCSS,JSとコンパクトなライブラリのみでコーディング。保守性、再利用性の高い構成を意識しました。\n\n【ライブラリ】\nSwiper/TweenMax/Pace.js\n【利用スキル補足】\nwebpack',
            href: 'https://portfolio-n2.netlify.app/',
            link: '→ Link'
        }
      ]
    }
  }
}
</script>
