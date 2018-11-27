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
                <router-link v-on:click.native="signOut() && close()" to="/#" class="mdl-navigation__link mdl-js-ripple-effect">
                    <div class="material-icons">home</div>
                    Sign Out
                </router-link>
            </nav>
        </div>
    </div>
</template>

<script>
  import _ from 'underscore';
  import firebase from 'firebase';

  export default {
      props: [
          'currentPage'
      ],
      methods: {
        close: function() {
            document.getElementById('nav').MaterialLayout.toggleDrawer()
        },
        signOut: function() {
          firebase.auth().signOut()
            .then(_.bind(function() {
              console.log('Signed Out !')
              this.close();
            }, this));
        }
      },
      data: function() {
          return {
          }
      }
  }
</script>


