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
    <span class="mdl-list__item-secondary-content">
      <a class="mdl-list__item-secondary-action" href="#"><i class="material-icons">star</i></a>
    </span>
  </li>
</template>

<script>
  export default {
    props: [
      'username',
      'message'
    ],
    methods: {

    },
    data: () => {
      return {
      }
    }
  }
</script>
