<template>
    <div>
        <rdb-banner :banner="banner"></rdb-banner>
        <rdb-quem-somos :quemsomos="quemsomos"></rdb-quem-somos>
        <hr class="uk-margin-remove"/>
        <rdb-beneficio titulo="Benefícios" :beneficios="beneficios"></rdb-beneficio>
        <hr class="uk-margin-remove"/>
        <rdb-explore-rede :explore="explore"></rdb-explore-rede>
        <rdb-depoimentos titulo="Depoimentos" :depoimentos="depoimentos"></rdb-depoimentos>
    </div>
</template>


<script>
import Slideshow from "@/components/shared/Slideshow";
import QuemSomos from "@/components/QuemSomos.vue";
import Beneficios from "@/components/Beneficios.vue";
import ExploreRede from "@/components/ExploreRede.vue";
import Depoimentos from "@/components/Depoimentos.vue";

export default {
props: ['banner','beneficios','quemsomos','depoimentos', 'explore'],

components:{
    'rdb-banner': Slideshow,
    'rdb-quem-somos': QuemSomos,
    'rdb-beneficio': Beneficios,
    'rdb-explore-rede': ExploreRede,
    'rdb-depoimentos': Depoimentos
},

mounted(){
    console.log(this)
}

}
</script>