<template>
  <b-container>
    <h2>{{ message }}</h2>
      <b-form inline>
        <b-row class="justify-content-center">

          <b-input-group prepend="Title" class="mb-2 mr-sm-2 mb-sm-0">
            <b-input
              id="inline-form-input-name"
              class="mb-2 mr-sm-2 mb-sm-0"
            ></b-input>
          </b-input-group>

          <b-input-group prepend="Network" class="mb-2 mr-sm-2 mb-sm-0">
            <b-input id="inline-form-input-username"></b-input>
          </b-input-group>

        </b-row>
        <b-row class="justify-content-center">

          <b-input-group prepend="Genres" class="mb-2 mr-sm-2 mb-sm-0">
            <b-input
              id="inline-form-input-genre"
              class="mb-2 mr-sm-2 mb-sm-0"
            ></b-input>
          </b-input-group>

          <b-input-group prepend="Number of Season" class="mb-2 mr-sm-2 mb-sm-0">
            <b-input id="inline-form-input-username"></b-input>
          </b-input-group>

        </b-row>
        <b-row class="justify-content-center">

          <b-input-group prepend="Is Current" class="mb-2 mr-sm-2 mb-sm-0">
            <b-form-checkbox class="mb-2 mr-sm-2 mb-sm-0" checked="true">Yes</b-form-checkbox>
            <b-form-checkbox class="mb-2 mr-sm-2 mb-sm-0">No</b-form-checkbox>
          </b-input-group>

          <b-button variant="primary">Save</b-button>

        </b-row>
      </b-form>
  </b-container>
</template>

<script>
export default {
  name: 'RegistroShow',
  props: {
    message: String
  }
}
</script>

<style scoped>

</style>
