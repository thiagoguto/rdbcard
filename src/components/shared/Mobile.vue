<template>
<div id="mobile" uk-offcanvas="mode: push">
    <div class="uk-offcanvas-bar uk-flex uk-flex-column uk-offcanvas-bar-animation uk-offcanvas-slide">
        <button class="uk-offcanvas-close" type="button" uk-close></button>
        <ul class="uk-nav uk-nav-primary uk-nav-center uk-margin-auto-vertical">
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
        <div class="uk-navbar-item">
            <router-link class="uk-button uk-button-default " to="/login">Login</router-link>
        </div>
    </div>
</div>
</template>