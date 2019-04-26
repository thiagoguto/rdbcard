<template>
    <section class="uk-section" id="quem-somos">
        <div class='uk-container'>
        <div class="uk-card uk-grid-collapse uk-child-width-1-2@s uk-grid" uk-grid="">
            <div>
                <div class="uk-card-body">
                    <h2>{{ quemsomos.titulo }}</h2>
                    <h5>{{ quemsomos.subtitulo }}</h5>
                    <div v-if="quemsomos.body.value" v-html="quemsomos.body.value"></div>
                </div>
            </div>
            <div class="uk-card-media-right uk-cover-container">
                <img :src="quemsomos.foto.url" alt="" uk-cover="" class="uk-cover" >
            </div>
        </div>
        </div>
    </section>
</template>
<script>
export default {
props:['quemsomos'],

}
</script>