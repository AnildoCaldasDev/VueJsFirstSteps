<template>
  <div>
    <b-col>
      <b-card
        :title="title"
        :img-src="image"
        img-alt="Image"
        img-top
        border-variant="primary"
        tag="article"
        style="max-width: 20rem;"
        class="mb-4 ml-3"
      >
        <b-card-text>
          Some quick example text to build on the card title and make up the
          bulk of the card's content.
        </b-card-text>
        <b-button variant="primary">Comprar</b-button>
      </b-card>
    </b-col>
  </div>
</template>
<script>
export default {
  props: {
    title: {
      type: String,
      required: true,
    },
    image: {
      type: String,
      required: true,
    },
  },
};
</script>
