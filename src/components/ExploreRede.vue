<template> 
<section class="uk-section" id="rede">
<div class="uk-container">
    <div class="title-section">
      <h2>Explore <b> a rede</b> <span class="icon icon-colab-new-tab"></span></h2>
      <p>Já são <b>20.000 endereços parceiros</b> e não paramos de crescer</p>
    </div>
    <div>
        <ul uk-tab="swiping: false" class="uk-tab">
            
            <li :class="index == 0 ? 'uk-active' : ''" v-for="(item, index) in explore" :key="index">
                <a href="#">{{ item.name }}</a>
            </li>
        </ul>
        <ul class="uk-switcher uk-margin">
            <li :class="index == 0 ? 'uk-active' : ''" v-for="(item, index) in explore" :key="index">
                <div class='uk-grid-collapse uk-child-width-1-1@s uk-child-width-expand@m  uk-background-primary uk-light' uk-grid>
                    <div class="uk-width-1-3" style="width: 200px !important;">

                        <div class='uk-padding ' >
                            <img :src="item.image" alt="">
                        </div>
                    </div>
                        <div class="uk-padding">
                            <h4>{{ item.title_offer_sample }}</h4>
                            <p>{{ item.text_offer_sample }}</p>
                        </div>

                </div>
                <div class="uk-child-width-1-2@s uk-child-width-1-4@m uk-child-width-1-5@l uk-grid-small" uk-grid>

                    <div v-for="(tg, index) in item._tags" :key="index" class=''>
                        <div class="uk-card uk-card-small uk-card-default uk-card-body">
                            <h3 class="uk-h4">{{ tg.name }}</h3>
                        </div>
                    </div>
                </div>
            </li>
        </ul>
    </div>
</div>
</section>
</template>
<script>

export default {
props:['explore'],

}
</script>
<style lang="sass">
.uk-tab
    .uk-active
        a
            border-bottom: 7px solid
            border-color: #1e87f0
</style>