<template>
  <ModalTemplate
    :show="show"
    @close="close"
  >
    <div class="modal-header">
      <h3>New Post</h3>
    </div>
    <div class="modal-body">
      <label class="form-label">
        Title
        <input
          v-model="title"
          class="form-control"
        >
      </label>
      <label class="form-label">
        Body
        <textarea
          v-model="body"
          rows="5"
          class="form-control"
        />
      </label>
    </div>
    <div class="modal-footer text-right">
      <button
        class="modal-default-button"
        @click="savePost()"
      >
        Save
      </button>
    </div>
  </ModalTemplate>
</template>

<script>
import ModalTemplate from '@/components/ModalTemplate'

export default {
  components: {
    ModalTemplate
  },
  props: ['show'],
  data: function () {
    return {
      title: '',
      body: ''
    }
  },
  methods: {
    close: function () {
      this.$emit('close')
      this.title = ''
      this.body = ''
    },
    savePost: function () {
      // Some save logic goes here...

      this.close()
    }
  },
  template: '#new-post-modal-template'
}
</script>

<style>

</style>
