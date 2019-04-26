<template>
    <section id="depoimentos" class="uk-section uk-background-cover uk-light" style="background: #2a6158">
        <div class='uk-container uk-container-expand'>
        <div class="uk-container">
            <h2 class="uk-text-center uk-text-uppercase uk-margin-remove-bottom">{{ titulo }}</h2>
            <p class="uk-text-center uk-margin-large-bottom">Confira nossos depoimentos e faça parte você também!!</p>
            <div class="uk-section uk-child-width-1-1@s uk-child-width-1-3@m uk-margin-large-bottom uk-grid" uk-grid="">
                <div v-for="(item, index) in depoimentos.dados" :key="index">
                    <div class="uk-card ">
                        <div class="uk-card-media-top uk-flex uk-flex-center">
                            <img class="uk-border-rounded" :src="item.foto.uri.url" alt="">
                        </div>
                        <div class="uk-card-body uk-text-center">
                            <div class="uk-light" v-html="item.depoimento.value"></div>
                            <h3 class="uk-card-title uk-margin-remove">{{ item.nome }}</h3>
                            
                        </div>
                    </div>
                </div>
                    
            </div>
            </div>
        </div>
    </section>
</template>
<script>
export default {
    props:['depoimentos', 'titulo']
}
</script>