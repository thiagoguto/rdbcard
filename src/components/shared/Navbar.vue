<template>
    <header class="uk-box-shadow-small">
        <div class='uk-container uk-container-expand'>
            <nav class="uk-navbar uk-navbar-transparent" uk-navbar>
                <div class="uk-navbar-left">
                    <div class="uk-navbar-item">
                        <router-link to="/" >
                            <img class="uk-logo" src='@/assets/img/logo.png' alt=''/>
                        </router-link>
                    </div>
                </div>
                <div class="uk-navbar-right">
                    <ul class="uk-navbar-nav uk-visible@m">
                        <li>
                            <a uk-scroll href="#quem-somos" >Quem Somos</a>
                        </li>
                        <li>
                            <a uk-scroll href="#beneficios" >Benefícios</a>
                        </li>
                        <li>
                            <a uk-scroll href="#rede" >Rede</a>
                        </li>
                        <li>
                            <a uk-scroll href="#cartao" >Cartão</a>
                        </li>
                        <li>
                            <a uk-scroll href="#" >Contato</a>
                        </li>
                    </ul>
                    <div class="uk-navbar-item uk-visible@m">
                        <router-link uk-scroll class="uk-button uk-button-primary" to="/login">Login</router-link>
                    </div>
                    <a uk-navbar-toggle-icon="" href="#mobile" uk-toggle="" class="uk-navbar-toggle uk-hidden@m uk-navbar-toggle-icon uk-icon"></a>
                </div>
            </nav>
        </div>
    </header>
</template>
<style lang="sass" scoped>
header
    background: #fff
.uk-logo
    width: 100px
</style>