<template>
  <div id="app">

    <rdb-navbar></rdb-navbar>
    
    <router-view 
      :banner="banner"
      :quemsomos="quemsomos"
      :beneficios="beneficios"
      :explore="explore"
      :depoimentos="depoimentos" />
    <rdb-bannerfooter></rdb-bannerfooter>
    <rdb-footer></rdb-footer>
    <rdb-mobile></rdb-mobile>
  </div>
</template>

<script>
import gql from 'graphql-tag'
import Navbar from './components/shared/Navbar'
import Mobile from './components/shared/Mobile'
import BannerFooter from './components/shared/BannerFooter'
import Footer from './components/shared/Footer'
import axios from 'axios'

import UIkit from '../node_modules/uikit'
import Icons from '../node_modules/uikit/dist/js/uikit-icons'
UIkit.use(Icons)

export default {
components:{
  'rdb-navbar': Navbar,
  'rdb-mobile': Mobile,
  'rdb-bannerfooter': BannerFooter,
  'rdb-footer': Footer
},

data(){
  return {
    banner: '',
    quemsomos: '',
    beneficios: '',
    explore: '',
    depoimentos: '',
  }
},
methods:{
  listaEmpresas(){
    
  }
},

apollo:{
  banner: gql`query{
    banner:nodeQuery(
      filter:{
        conditions:[
          {field:"type", value:"banner"}
        ]
      }
    ){
      dados:entities{
        ... on NodeBanner{
          titulo:title
          link:fieldLink{
            url:uri
          }
          img:fieldBanner{
            uri:derivative(style:BANNER){
              url
            }
          }
        }
      }
    }
  }`,
  quemsomos: gql`query{
      quemsomos:nodeById(id:"13"){
      ... on NodePage{
        titulo:title
        subtitulo:fieldSubtitulo
        foto:fieldFoto{
            url
        }
       	body{
          value
        } 
      }
    }
  }`,
  beneficios: gql`query{
      beneficios:nodeQuery(
    filter:{
      conditions:[
        {field:"type", value:"beneficios"}
      ]
    }
    ){
    dados:entities{
      ... on NodeBeneficios{
        titulo:title
        subtitulo:fieldSubtitulo
        cor:fieldCor
        img:fieldImage{
          uri:derivative(style:CARD){
            url
          }
        }
      }
    }
    }
  }`,
  depoimentos: gql`query{
    depoimentos:nodeQuery(
    filter:{
      conditions:[
        {field:"type", value:"depoimentos"}
      ]
    }
    ){
    dados:entities{
    ... on NodeDepoimentos{
      nome:title
      foto:fieldAvatar{
        uri:derivative(style:DEPOIMENTOS){
          url
        }
      }
      depoimento:body {
        value
      }
    }
    }
    }
  }`,
},

mounted(){
   axios.post('https://backend.allya.com.br/api/customers/login',{
        email: "alisson@reconsultoriaemseguros.com.br", 
        password: "vitolo1988"
      }).then(({data}) => {
        localStorage.setItem('token', data.accessToken)
    }),
    axios.get('https://backend.allya.com.br/api/categories/',{
      headers:{
        Authorization: localStorage.token
      }
    }).then(({data}) => {
      this.explore = data
        console.log('response do allya: ', data)
    })
}

}
</script>
<style lang="sass">
$global-primary-background: #5db44d !default

body
  font-family: 'Roboto', sans-serif
  line-height: 1.6rem
  font-size: 1.06rem
  letter-spacing: 0.167px
.uk-tab .uk-active a
  border-color: $global-primary-background

@import url('https://fonts.googleapis.com/css?family=Roboto:300,400,500,700')
// 2. Import default variables and available mixins.
@import "../node_modules/uikit/src/scss/variables-theme.scss"
@import "../node_modules/uikit/src/scss/mixins-theme.scss"

// 3. Your custom mixin overwrites.
@mixin hook-card() 
  color: #000

// 4. Import UIkit.
@import "../node_modules/uikit/src/scss/uikit-theme.scss"
</style>