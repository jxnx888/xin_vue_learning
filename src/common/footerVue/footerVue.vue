<template>
  <div class="footer_wrapper">
    <footer class="common_footer">
      <el-row>
        <el-col :span="24">
          <div class="social_wrapper clearfix">
            <div class="each_social">
              <a class="wechat-btn" title="WeChat:Xin Ning">
                <div class="icon i_wechat"></div>
                <img src="/image/footer/wechat_xin.jpg" alt="">
              </a>
            </div>
            <div class="each_social">
              <a href="https://www.linkedin.com/in/xin-ning-28818b115/" class="linkedin-btn" target="_blank"  title="LinkedIn:Xin Ning">
                <div class="icon i_linkedin"></div>
              </a>
            </div>
            <div class="each_social">
              <a href="https://www.facebook.com/jxnx888" class="facebook-btn" target="_blank" title="Facebook:Xin Ning">
                <div class="icon i_facebook"></div>
              </a>
            </div>
            <div class="each_social">
              <a href="https://github.com/jxnx888" class="github-btn" target="_blank" title="Github:Xin Ning">
                <div class="icon i_github"></div>
              </a>
            </div>
          </div>
        </el-col>
        <el-col :span="24" class="sitemap">
          <!-- <div class="download_file"><a href="/file/XinNing-Resume-CN.pdf" download="/file/XinNing-Resume-CN.pdf"><i class="el-icon-printer"></i>{{$t('footer.resume')}}</a></div>-->
          <!--          <div class="download_file" v-if="currentLang==='en_us'"><a download=""><i class="el-icon-printer"></i>{{$t('footer.coverletter')}}</a></div>-->
          <div class="sitemap_wrapper clearfix">
            <div class="each_map"><a :href="resumeLink" download="/file/XinNing-Resume-CN.pdf"><i
                class="el-icon-printer"></i>{{ $t('footer.resume') }}</a></div>
            <div class="each_map">
              <router-link to="/" class="each_link">{{ $t('nav.home') }}</router-link>
            </div>
            <div class="each_map">
              <router-link to="/skills" class="each_link">{{ $t('nav.skills') }}</router-link>
            </div>
            <div class="each_map">
              <router-link to="/projects" class="each_link">{{ $t('nav.Projects') }}</router-link>
            </div>
            <div class="each_map">
              <router-link to="/aboutme" class="each_link">{{ $t('nav.AboutMe') }}</router-link>
            </div>
            <div class="each_map last_menu">
              <router-link to="/aboutme" class="each_link">{{ $t('nav.contact') }}</router-link>
            </div>
          </div>
        </el-col>
        <el-col :span="24" class="footer_copyright">
          Copyright 2015-2020 | Xin Ning
        </el-col>
      </el-row>
    </footer>
  </div>
</template>

<script>
export default {
  name: "footerVue",
  data() {
    return {
        resumeLink:'/file/XinNing-Resume-CN.pdf',
    }
  },
  created() {
  },
  methods: {
  },
  watch: {
      '$i18n.locale'(newValue, oldValue) {
          if(newValue!=oldValue)   {
              if('zh_cn' == newValue){
                  this.resumeLink = '/file/XinNing-Resume-CN.pdf';
              }
              else{
                  this.resumeLink = '/file/XinNing-Resume-EN.pdf';
              }
          }
      }
  }
}
</script>

<style scoped lang="stylus">
.footer_wrapper
  background #cceaf2
  min-height: 100px;

  .common_footer
    width 1200px
    margin auto
    text-align center
    @media screen and (max-width: 768px)
      width 100%

    .social_wrapper
      width: 2.5rem;
      height: 100%;
      margin: 20px auto;

      .each_social
        float left
        width .5rem
        height .5rem
        margin: 0 .06rem;
        .wechat-btn
          position relative
          img
            display none;
            position: absolute;
            top: -150px;
            left: -25px;
        .wechat-btn:hover
          img
            display block
        .i_wechat
          background url("/image/footer/icon_wechat.png")

        .i_wechat:hover
          background url("/image/footer/icon_wechat_hover.png")

        .i_linkedin
          background url("/image/footer/icon_linkedin.png")

        .i_linkedin:hover
          background url("/image/footer/icon_linkedin_hover.png")

        .i_facebook
          background url("/image/footer/icon_facebook.png")

        .i_facebook:hover
          background url("/image/footer/icon_facebook_hover.png")

        .i_github
          background url("/image/footer/icon_github.png")

        .i_github:hover
          background url("/image/footer/icon_github_hover.png")

        .icon
          width .5rem
          height .5rem
          background-repeat no-repeat !important
          background-size cover !important
          background-position center !important

    .sitemap
      .sitemap_wrapper
        width 6.6rem
        margin 0 auto 20px
        @media screen and (max-width: 768px)
          width 100%
        .each_map
          float left
          width: 1.1rem;
          position relative
          padding: 0 .15rem
          font-size: .16rem
          color #666
          @media screen and (max-width: 768px)
            width 50%
            margin-bottom .1rem
        .each_map *
          color #666
        .each_map:after
          content "|"
          position absolute
          top -1px
          right 0
          color #666
          @media screen and (max-width: 768px)
            display none
        .each_map.last_menu:after
          display none
    .footer_copyright
      font-size .14rem
      color #666
      margin-bottom 20px
</style>
