<template>
  <div class="row footer">
    <div class="container">
      <div class="row">
        <div class="community-area-lg-md-sm row hidden-xs">
          <div class="col-lg-2 col-md-2 col-sm-2 col-lg-offset-1 col-md-offset-1 col-sm-offset-1">
            <p class="p-footer-col-name">{{ $t('footer.community') }}</p>
            <div>
              <a class="community-area-lg-md-sm-a-24" target="_blank" href="https://t.me/nknorg">
                <span><i class="fa fa-send" aria-hidden="true"></i></span>
                <span class="community-area-lg-md-sm-name">{{ $t('footer.telegram') }}</span>
              </a>
            </div>
            <div>
              <a class="community-area-lg-md-sm-a-24" target="_blank" href="https://twitter.com/NKN_ORG">
                <span><i class="fa fa-twitter" aria-hidden="true"></i></span>
                <span class="community-area-lg-md-sm-name">{{ $t('footer.twitter') }}</span>
              </a>
            </div>
            <div>
              <a class="community-area-lg-md-sm-a-24" target="_blank" href="https://www.reddit.com/r/nknblockchain">
                <span><i class="fa fa-reddit-alien" aria-hidden="true"></i></span>
                <span class="community-area-lg-md-sm-name">{{ $t('footer.reddit') }}</span>
              </a>
            </div>
          </div>
          <div class="col-lg-2 col-md-2 col-sm-2">
            <p class="p-footer-col-name">{{ $t('footer.resource') }}</p>
            <div>
              <a class="community-area-lg-md-sm-a-24" target="_blank" href="https://github.com/nknorg">
                <span><i class="fa fa-github" aria-hidden="true"></i></span>
                <span class="community-area-lg-md-sm-name">{{ $t('footer.gitHub') }}</span>
              </a>
            </div>
            <div>
              <a v-if="$i18n.locale === 'en'" class="community-area-lg-md-sm-a-24" target="_blank" :href="urlList.introductionEn">
                <span><i class="fa fa-file" aria-hidden="true"></i></span>
                <span class="community-area-lg-md-sm-name">{{ $t('footer.introduction') }}</span>
              </a>
              <a v-if="$i18n.locale === 'zh'" class="community-area-lg-md-sm-a-24" target="_blank" :href="urlList.introductionCn">
                <span><i class="fa fa-file" aria-hidden="true"></i></span>
                <span class="community-area-lg-md-sm-name">{{ $t('footer.introduction') }}</span>
              </a>
            </div>
            <div>
              <a class="community-area-lg-md-sm-a-24" target="_blank" :href="urlList.whitePaper">
                <span><i class="fa fa-file" aria-hidden="true"></i></span>
                <span class="community-area-lg-md-sm-name">{{ $t('footer.whitepaper') }}</span>
              </a>
            </div>
          </div>
          <div class="col-lg-2 col-md-2 col-sm-2">
            <p class="p-footer-col-name">{{ $t('footer.focus.name') }}</p>
            <div>
              <a class="community-area-lg-md-sm-a-24" href="mailto:join@nkn.org">
                <span><i class="fa fa-envelope" aria-hidden="true"></i></span>
                <span class="community-area-lg-md-sm-name">{{ $t('footer.focus.joinUs') }}</span>
              </a>
            </div>
            <div>
              <a class="community-area-lg-md-sm-a-24" target="_blank" href="https://www.reddit.com/r/nknblockchain">
                <span><i class="fa fa-newspaper-o" aria-hidden="true"></i></span>
                <span class="community-area-lg-md-sm-name">{{ $t('footer.focus.news') }}</span>
              </a>
            </div>
            <div>
              <a  v-if="$i18n.locale === 'en'" class="community-area-lg-md-sm-a-24" target="_blank" href="https://medium.com/nknetwork">
                <span><i class="fa fa-medium" aria-hidden="true"></i></span>
                <span class="community-area-lg-md-sm-name">{{ $t('footer.focus.blog') }}</span>
              </a>
              <a v-if="$i18n.locale === 'zh'" class="community-area-lg-md-sm-a-24" v-on:mouseenter="enableIcon" v-on:mouseleave="disabledIcon">
                <span><i class="fa fa-wechat" aria-hidden="true"></i></span>
                <span class="community-area-lg-md-sm-name">{{ $t('footer.wechat') }}</span>
                <img v-show="iconShow[0]" class="img-qrcode" src="./../assets/footer/QRcode.png" style="position: absolute; left: 50px;">
              </a>
            </div>
          </div>

          <div class="col-lg-5 col-md-5 col-sm-5">
            <p>{{ $t('footer.contact.content') }}</p>
            <div>
              <a class="email-address" href="mailto:contact@nkn.org">
                <span><i class="fa fa-envelope" aria-hidden="true"></i></span>
                <span class="community-area-lg-md-sm-name">{{ $t('footer.contact.email') }}</span>
              </a>
            </div>
            <div v-show="emailSubscribeShow[0]" class="form-group div-input-email">
              <div class="input-group">
                <input v-model="emailAddress" type="text" class="form-control input-email" :placeholder="$t('footer.subscribe.placeholder')">
                <span class="input-group-btn btn-email">
                  <button @click="subscribeEmail" class="btn btn-default btn-email" type="button">{{ $t('footer.subscribe.btnName') }}</button>
                </span>
              </div>
            </div>
            <div v-show="!emailSubscribeShow[0]" class="success-style">{{ $t('footer.subscribe.success') }}</div>
            <div class="txt-nkn-events">
              <p>{{ $t('footer.subscribe.noMiss') }}</p>
            </div>
          </div>
        </div>

        <div class="community-area-xs row hidden-lg hidden-md hidden-sm visible-xs-12">
          <a href="mailto:contact@nkn.org"><i class="fa fa-envelope-o" aria-hidden="true"></i></a>
          <a target="_blank" href="https://t.me/nknorg"><i class="fa fa-send" aria-hidden="true"></i></a>
          <a target="_blank" href="https://github.com/nknorg"><i class="fa fa-github" aria-hidden="true"></i></a>
          <a target="_blank" href="https://www.reddit.com/r/nknblockchain"><i class="fa fa-reddit-alien" aria-hidden="true"></i></a>

          <div>
            <a v-if="$i18n.locale === 'en'" class="btn a-footer-introduction" target="_blank" :href="urlList.introductionEn"><i class="fa fa-file-pdf-o" aria-hidden="true"></i> {{ $t('footer.introduction') }}</a>
            <a v-if="$i18n.locale === 'zh'" class="btn a-footer-introduction" target="_blank" :href="urlList.introductionCn"><i class="fa fa-file-pdf-o" aria-hidden="true"></i> {{ $t('footer.introduction') }}</a>
          </div>
          <div>
            <a class="btn a-footer-white-paper" target="_blank" :href="urlList.whitePaper"><i class="fa fa-file-pdf-o" aria-hidden="true"></i> {{ $t('footer.whitepaper') }}</a>
          </div>
        </div>

        <div class="row row-footer-further hidden-lg hidden-md hidden-sm visible-xs-12">
          <p>{{ $t('footer.contact.content') }}</p>
          <a class="email-address-xs" href="mailto:contact@nkn.org">{{ $t('footer.contact.email') }}</a>

          <div v-show="emailSubscribeXsShow[0]" class="div-input-email">
            <input v-model="emailAddressXs" type="text" class="input-email-xs" :placeholder="$t('footer.subscribe.placeholder')">
            <button @click="subscribeXsEmail" class="btn btn-default btn-email-xs" type="button">{{ $t('footer.subscribe.btnName') }}</button>
          </div>
          <div v-show="!emailSubscribeXsShow[0]" class="success-style-xs">{{ $t('footer.subscribe.success') }}</div>
          <div class="txt-nkn-events">
            <p>{{ $t('footer.subscribe.noMiss') }}</p>
          </div>
        </div>

        <!--<img class="img-texture" src="./../assets/footer/texture.png" alt="">-->

        <div class="copyright">{{ $t('copyRight') }}</div>
      </div>
    </div>
  </div>
</template>

<script>
	export default {
    name: "the-footer",
    data() {
      return {
        email: '',
        content: '',
        disabledVal: false,
        completed: false,
        urlList: {
          introductionEn: process.env.DOC_URL + 'NKN_Introduction_en.pdf',
          introductionCn: process.env.DOC_URL + 'NKN_Introduction_cn.pdf',
          whitePaper: process.env.DOC_URL + 'NKN_Whitepaper.pdf'
        },
        iconShow: [false],
        emailAddress: '',
        emailSubscribeShow: [true],
        emailAddressXs: '',
        emailSubscribeXsShow: [true]
      }
    },
    created() {
      // this.getConfig()
    },
    methods: {
      scrollTop() {
        $(window).scrollTop(0)
      },
      getConfig() {
        return this.axios.get(process.env.CONFIG_URL + 'config.json').then(response => {
          this.urlList.introductionEn = response.data.introduction_en
          this.urlList.introductionCn = response.data.introduction_cn
          this.urlList.whitePaper = response.data.whitepaper
        }).catch(error => {
          this.urlList.introductionEn = this.$config.introduction_en
          this.urlList.introductionCn = this.$config.introduction_cn
          this.urlList.whitePaper = this.$config.whitepaper
        })
      },
      enableIcon() {
        this.$set(this.iconShow, 0, true);
      },
      disabledIcon() {
        this.$set(this.iconShow, 0, false);
      },
      subscribeEmail() {
        if(this.emailAddress !== '') {
          let formData = {address: this.emailAddress}
          return this.axios.post(process.env.API_URL + 'email/new', formData).then(response => {
            if(response.data.code === 1000) {
              this.$set(this.emailSubscribeShow, 0, false);
            }
          }).catch(error => {
            console.log(error)
          })
        }
      },
      subscribeXsEmail() {
        if(this.emailAddressXs !== '') {
          let formData = {address: this.emailAddressXs}
          return this.axios.post(process.env.API_URL + 'email/new', formData).then(response => {
            if(response.data.code === 1000) {
              this.$set(this.emailSubscribeXsShow, 0, false);
            }
          }).catch(error => {
            console.log(error)
          })
        }
      }
    }
  }
</script>

<style scoped>
  /*****************************/
  /* 以下是提交邮箱、联系方式等 */
  /*****************************/
  .footer {
    position: relative;
    color: white;
    text-align: center;
    background-color: #253A7E;
    padding: 80px 0 155px 0;
  }

  .community-area-lg-md-sm {
    text-align: left;
  }
  .community-area-lg-md-sm > div > p {
    font-size: 18px;
  }
  .community-area-lg-md-sm > div > div {
    margin-top: 20px;
  }
  .p-footer-col-name {
    margin-bottom: 50px;
  }

  .community-area-lg-md-sm-a-24 {
    color: white;
    text-decoration: none;
  }
  .community-area-lg-md-sm-a-24:hover {
    color: #37bfef;
  }
  .community-area-lg-md-sm-a-24 {
    font-size: 24px;
  }
  .community-area-lg-md-sm-name {
    font-size: 18px;
    font-weight: 100;
    position: absolute;
    line-height:35px;
    left: 60px;
  }

  .community-area-xs {
    text-align: center;
    font-size: 28px;
    margin-bottom: 35px;
  }
  .community-area-xs > a {
    color: white;
    margin: 0 15px;
  }

  .email-address,
  .email-address-xs {
    margin-top: 32px;
    font-size: 24px;
    color: #58b4e2;
  }
  .email-address:hover {
    color: #69DAFF;
  }

  .copyright {
    position: absolute;
    color: white;
    bottom: 0;
    left: 0;
    right: 0;
    height: 54px;
    line-height: 54px;
    font-size: 14px;
    font-weight: 100;
    background-color: #182962;
  }

  .row-footer-further {
    margin-top: 70px;
  }

  .a-footer-introduction {
    margin-top: 30px;
  }
  .a-footer-white-paper {
    margin-top: 10px;
  }
  .a-footer-introduction,
  .a-footer-white-paper {
    width: 240px;
    height: 32px;
    line-height: 32px;
    border: 1px solid white;
    font-size: 16px;
    font-weight: 100;
    color: white;
    padding: 0;
  }

  .div-input-email {
    margin-top: 35px !important;
  }
  .input-email,
  .input-email-xs {
    height: 57px;
    width: 256px;
    font-size: 18px;
  }
  .input-email-xs {
    padding: 0 8px;
    height: 48px;
    border-radius: 4px;
    margin-left: auto;
    margin-right: auto;
    width: 80%;
    color: black;
  }
  .btn-email,
  .btn-email-xs {
    height: 57px;
    width: 131px;
    background-color: #37bfef;
    border-top-right-radius: 4px;
    border-bottom-right-radius: 4px;
    color: white;
    font-size: 16px;
    font-weight: 200;
    text-transform: none;
  }
  .btn-email:hover,
  .btn-email-xs:hover {
    background-color: #69DAFF;
  }
  .btn-email-xs {
    height: 48px;
    border-radius: 4px;
    margin: 5px auto;
    width: 80%;
  }

  .success-style,
  .success-style-xs {
    font-size: 18px;
    color: green;
  }
  .success-style-xs {
    margin: 30px 15px;
  }

  .txt-nkn-events {
    font-size: 18px;
    color: #8ea1c6;
  }
  .img-qrcode {
    width: 120px;
  }
  .img-wechat-logo {
    margin-left: 40px;
    width: 34px;
  }
  .span-wechat-name {
    font-size: 21px;
    font-weight: 100;
    position: absolute;
    margin: auto;
    left: 215px;
    right: 0;
    top: 87px;
    bottom: 0;
    width: 50px;
  }
  .img-texture {
    width: 100%;
    height: 100%;
    margin-top: 80px;
  }

  /*input placeholder字体颜色*/
  input::-webkit-input-placeholder, textarea::-webkit-input-placeholder {color: #e4e4e4;}
  input:-moz-placeholder, textarea:-moz-placeholder {color:#e4e4e4;}
  input::-moz-placeholder, textarea::-moz-placeholder {color:#e4e4e4;}
  input:-ms-input-placeholder, textarea:-ms-input-placeholder {color:#e4e4e4;}
</style>
