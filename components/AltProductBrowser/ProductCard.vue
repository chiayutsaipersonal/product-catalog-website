<template>
  <div class="product-card-container"
       @click="$emit('clicked')">
    <div class="product-card">
      <div class="photo-container-frame">
        <div :style="styleBinding(product.photos)"
             class="photo-container"/>
      </div>
      <div class="product-information">
        <div class="product-model">
          {{ product.model }}
        </div>
        <div class="product-name">
          {{ product.name }}
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ProductCard',
  props: {
    product: {
      type: Object,
      default() {
        return {}
      },
    },
  },
  methods: {
    styleBinding(photos) {
      if (photos[0]) {
        return {
          'background-image': `url(${photos[0].thumbnailUrl})`,
        }
      } else {
        return {
          'background-image': `url(${require('~/assets/placeholder.svg')})`,
          'background-size': 'contain',
          'background-position': 'center',
          'background-repeat': 'no-repeat',
        }
      }
    },
  },
}
</script>

<style scoped>
.product-card-container {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

.product-card-container:hover .product-card {
  transform: translate(1px, 1px);
}

.product-card {
  box-sizing: border-box;
  border: 1px solid whitesmoke;
  border-radius: 5px;
  padding: 5px;
  background-color: whitesmoke;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
  min-height: 100%;
}

.photo-container-frame {
  border-radius: 5px;
  background-color: white;
  margin: 1px 1px 10px 1px;
  padding: 5px;
}

.photo-container {
  height: 256px;
  background-color: white;
  background-size: contain;
  background-position: center;
  background-repeat: no-repeat;
  margin: 0;
}

@media only screen and (max-width: 640px) {
  .photo-container {
    min-height: 200px;
  }
}

.product-information {
  margin: 5px;
  text-align: left;
  font-weight: 600;
  cursor: default;
}

.product-model {
  font-size: 75%;
  letter-spacing: 0.15em;
}

.product-name {
  font-weight: 300;
  font-size: 75%;
}
</style>
