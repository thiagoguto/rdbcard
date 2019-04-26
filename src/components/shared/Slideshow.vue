<template>
    <div class="uk-position-relative uk-visible-toggle uk-light" index="-1" uk-slideshow="min-height: 280; max-height: 700">

        <ul class="uk-slideshow-items">
            <li :key="index" v-for="(item, index) in banner.dados">
                <img :src="item.img[0].uri.url" :alt="item.titulo" uk-cover>
            </li>
        </ul>

        <a class="uk-position-center-left uk-position-small uk-hidden-hover" href="#" uk-slidenav-previous uk-slideshow-item="previous"></a>
        <a class="uk-position-center-right uk-position-small uk-hidden-hover" href="#" uk-slidenav-next uk-slideshow-item="next"></a>

    </div>
</template>
<script>
export default {

props: ['banner']

}
</script>