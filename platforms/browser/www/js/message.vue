<template>
  <li class="mdl-list__item mdl-list__item--three-line">
    <span class="mdl-list__item-primary-content">
      <span class="mdl-chip mdl-chip--contact">
          <span class="mdl-chip__contact mdl-color--indigo mdl-color-text--white">B</span>
          <span class="mdl-chip__text">{{username}}</span>
      </span>
      <span class="mdl-list__item-text-body">
        {{message}}
      </span>
    </span>
    <span class="actions" v-if="isAuthor()">
      <span class="mdl-list__item-secondary-content">
        <a class="mdl-list__item-secondary-action" href="#"><i class="material-icons">edit</i></a>
      </span>
      <span class="mdl-list__item-secondary-content">
        <a class="mdl-list__item-secondary-action" href="#"><i class="material-icons">delete</i></a>
      </span>
    </span>
  </li>
</template>

<script>
  import firebase from 'firebase';

  export default {
    props: [
      'username',
      'email',
      'message'
    ],
    methods: {
      isAuthor: function() {
        let currentUser = firebase.auth().currentUser;
        console.log(this.email)
        console.log(currentUser.email)
        return this.email == currentUser.email;
      }
    },
    data: () => {
      return {
      }
    }
  }
</script>
