<template>
<div>
        <rdb-banner :banner="banner"></rdb-banner>
    <div class='uk-section' style="border-top: 7px solid #5db44d">

        <div class="uk-container uk-container-small">
            <div class='uk-grid-small uk-flex uk-flex-center uk-text-center' uk-grid>
                <div class='uk-width-1-1@s uk-width-2-3@m uk-width-1-3@l'>
                    <h1>Seja bem vindo!</h1>
                    <p>Insira seu e-mail e sua senha de usuario RDB.</p>
                    <div class='uk-card uk-card-body uk-card-default'>
                        <form>
    <fieldset class="uk-fieldset">

        <legend class="uk-legend">Login</legend>

        <div class="uk-margin-large">
            <input class="uk-input" type="text" placeholder="E-mail">
        </div>

        <div class="uk-margin-large">
            <input class="uk-input" type="password" placeholder="Senha">
        </div>

        <div class="uk-margin-large">
            <button  class="uk-button uk-button-primary uk-width-1-1">Entrar</button>
        </div>

    </fieldset>
</form>
                    </div>
                </div>
            </div>
        </div>
    </div>
</div>
</template>
<script>
import Slideshow from '@/components/shared/Slideshow.vue'
export default {
    props:['banner'],
    components:{
        'rdb-banner': Slideshow
    }
}
</script>