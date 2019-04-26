<template>
    <div class="uk-position-relative uk-visible-toggle uk-light" tabindex="-1" uk-slider="sets: true">

    <ul class="uk-slider-items uk-child-width-1-1@s uk-child-width-1-3@m uk-child-width-1-4@l">
        <li v-for="(item, index) in categorias" :key="index">
            <img :src="item.image" alt="">
            <div class="uk-position-center uk-panel"><h1>1</h1></div>
        </li>
    </ul>

    <a class="uk-position-center-left uk-position-small uk-hidden-hover" href="#" uk-slidenav-previous uk-slider-item="previous"></a>
    <a class="uk-position-center-right uk-position-small uk-hidden-hover" href="#" uk-slidenav-next uk-slider-item="next"></a>

</div>
</template>
<script>
export default {
    props:['categorias']
}
</script>