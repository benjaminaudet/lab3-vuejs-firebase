<template>
    <div class="mdl-layout mdl-js-layout mdl-layout--fixed-header" id="nav">
        <header class="mdl-layout__header">
            <div class="mdl-layout__header-row">
                <span class="mdl-layout-title">{{currentPage}}</span>
                <div class="mdl-layout-spacer"></div>
                <nav class="mdl-navigation"></nav>
            </div>
        </header>
        <div class="mdl-layout__drawer">
            <span class="mdl-layout-title">Pages</span>
            <nav class="mdl-navigation">
                <div v-on:click="close" v-for="nav of navigation">
                    <router-link :to="nav.url" class="mdl-navigation__link mdl-js-ripple-effect">
                        <div class="material-icons">{{nav.icon}}</div>
                        {{nav.label}}
                    </router-link>
                </div>
            </nav>
        </div>
    </div>
</template>

<script>
    import firebase from 'firebase';
    import navigation from './navigationElements.js';

    export default {
        props: [
            'currentPage'
        ],
        methods: {
            close: function() {
                document.getElementById('nav').MaterialLayout.toggleDrawer()
            }
        },
        data: function() {
            return {
                navigation: navigation
            }
        }
    }
</script>


