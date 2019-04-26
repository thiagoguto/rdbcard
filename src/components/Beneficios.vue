<template>
<section id="beneficios" class="uk-section uk-background-muted">
    <div class="uk-container">
        <h2 class="uk-text-center uk-text-uppercase uk-margin-large">{{ titulo }}</h2>
        <div class="uk-section uk-child-width-1-1@s uk-child-width-1-2@m uk-margin-top-large uk-grid" uk-grid="">
            <div v-for="(item, index) in beneficios.dados" :key="index">
                <div class="uk-card ">
                    <div class="uk-card-media-top uk-flex uk-flex-center">
                            <img class="uk-border-rounded" :src="item.img.uri.url" :alt="item.titulo">
                    </div>
                    <div class="uk-card-body uk-text-center">
                        <h3 class="uk-card-title uk-margin-remove">{{ item.titulo }}</h3>
                        <h4 class="uk-margin-remove uk-h3" :style="'color:'+ item.cor ">
                            {{ item.subtitulo }}
                        </h4>
                        <p></p>
                    </div>
                </div>
            </div>      
        </div>
    </div>
</section>

</template>
<script>
export default {
    props:['titulo', 'beneficios']
}
</script>