<template lang="pug">
.container-fluid
  .row
    .index_page
      section.banner.col-md-12
        .row
          Banner
      section.product 
      section.development
      
      section.idea.col-md-12
        h1 CASE STUDIES
        //- br
        .row
          .col-sm-4.case(v-for="case in caseAry | limitBy 3")
            h2 {{case.title}}
            img.img-responsive(v-bind:src="case.url")
        .row
          .col-sm-4.case(v-for="case in caseAry | limitBy 3 3")
            h2 {{case.title}}
            img.img-responsive(v-bind:src="case.url")
        a.btn_learnMore Learn More

      section.start_today.col-md-12
        h1 OUR PARTNER & CUSTOMER
        p Lorem ipsum dolor sit amet, consectetur adipisicing elit. Odit sint ex dolore dolorum doloremque culpa sed aspernatur obcaecati, neque ipsum amet velit quia expedita ut facilis, reprehenderit quis veritatis autem eligendi delectus necessitatibus quo maxime inventore. Corporis cupiditate officiis id possimus minus, quaerat magni. Eligendi perferendis ipsam aut itaque blanditiis?
        .partner
          a(v-for="link in partnerAry | limitBy 5", v-bind:href="link.url") 
            img(v-bind:src="link.Picurl", alt="")
          a(v-for="link in partnerAry | limitBy 5", v-bind:href="link.url") 
            img(v-bind:src="link.Picurl", alt="")
      footer.col-md-12
        h3 About Gemsense 
        ul.social
          li(v-for="icon in iconAry| limitBy 6",v-bind:style="{ 'background-color': icon.icon_bg}")
            i(class="fa"+" "+"{{icon.icon_name}}",aria-hidden="true")
        ul.contact  
          li.mail 
            a(href='mailto:Gemsense@gmail.com') Gemsense@gmail.com
          li.website 
            a(href='http://Gemsense.com') http://Gemsense.com
        ul.copyright
          li Hosting Sponsored by Wendy - managed by Gemsense
          li Copyright @2017 -Gemsense - All rights reserved - Gemsense is released under the MIT license
</template>

<script>
import Banner from '../pages/Banner.vue'
export default {
  components: {
    'banner': Banner
  },
  data () {
    return {
      testArray: 'hshs',
      caseAry: [
        {
          title: 'Healthcare',
          url: require('../assets/index/case1.jpg')
        },
        {
          title: 'Immersive VR Experie',
          url: require('../assets/index/case2.jpg')
        },
        {
          title: 'Industrial Tracking',
          url: require('../assets/index/case3.jpg')
        },
        {
          title: 'Remote Monitoring',
          url: require('../assets/index/case4.jpg')
        },
        {
          title: 'Smart Office',
          url: require('../assets/index/case5.jpg')
        },
        {
          title: 'Activities Tracking',
          url: require('../assets/index/case6.jpg')
        }
      ],
      partnerAry: [
        {
          url: 'http://cn.vuejs.org/v2/guide/',
          Picurl: require('../assets/index/partner1.png')
        },
        {
          url: 'https://www.facebook.com/',
          Picurl: require('../assets/index/partner2.png')
        },
        {
          url: 'https://www.facebook.com/',
          Picurl: require('../assets/index/partner3.png')
        },
        {
          url: 'https://www.facebook.com/',
          Picurl: require('../assets/index/partner4.png')
        },
        {
          url: 'https://www.facebook.com/',
          Picurl: require('../assets/index/partner5.png')
        }
      ],
      iconAry: [
        {
          icon_name: 'fa-twitter',
          icon_bg: '#30a6cf'
        },
        {
          icon_name: 'fa-pinterest-p',
          icon_bg: '#c62632'
        },
        {
          icon_name: 'fa-linkedin',
          icon_bg: '#1977a6'
        },
        {
          icon_name: 'fa-instagram',
          icon_bg: '#427399'
        },
        {
          icon_name: 'fa-google-plus',
          icon_bg: '#db4d3f'
        },
        {
          icon_name: 'fa-facebook',
          icon_bg: '#3d5b96'
        }
      ]
    }
  },
  computed: {
    testhahah () {
      return this.testArray + 'after computed'
    }
  },
  methods: {
    alarm () {
      window.alert('hsh')
    }
  }, // close methods
  ready () {
  },
  watch: {
    testArray (newValue, oldValue) {
      console.log(newValue)
      console.log(oldValue)
    }
  }
}
</script>

<style lang="scss" scoped>
@import '../scss/_variables.scss';
@import '../scss/_mixin.scss';

.idea{
  background-color: #f4f8fa;
  padding: 55px 0;
  h1{
    @include index_h1;
    margin-bottom: 55px;
  }
  .row{padding: 0 6%;
    &:nth-child(3){
      margin-top: 70px;
    }
  }
  
  .case{
    h2{
      font-family: $main_font_Light;
      font-size: 25px;
      letter-spacing: 1.6px;
      margin-bottom: 10px;
    }
  }

  .btn_learnMore{
    margin-top: 50px;
  }
}

.start_today{
  padding-top: 50px;
  h1{
    @include index_h1;
    margin-bottom: 20px;
  }
  p{
    @include center;
    width: percentage(1180px/$wrap_w);
    font-family: $main_font_Light;
    font-size: 22px;
    line-height: 30px;
  }
  .partner{
    @include center;
    width: 95%;
    margin-top: 60px;
    margin-bottom: 80px;
    a{
      display: inline-block;
      width: 20%;
    }
  } 
}

footer{
  background-color: #1e323d;
  color: #fff;
  font-family: $main_font_r;
  text-align: left;
  padding-top: 50px;
  padding-bottom: 50px;
  padding-left: percentage(90px/$wrap_w);
  h3{
    font-size: 24px;
    letter-spacing: 1px;
  }
  .social{
    margin-top: 20px;
    margin-bottom: 20px;
    >li{
      display: inline-block;
      font-size: 26px;
      width: 45px;
      height: 45px;
      border-radius: 50%;
      line-height: 45px;
      text-align: center;
      margin-right: 30px;
    }
  }
  .contact,.copyright{
    >li{
      line-height: 35px;
    }
  }
  .contact{
    margin-bottom: 10px;
  }

}



</style>
