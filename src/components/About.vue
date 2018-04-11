<template>
    <div>
        <h2>Tentang {{ name }}</h2>
        <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Aperiam, vel cum! Numquam, quo voluptates. Quibusdam iste, aperiam expedita, hic repellendus maxime magni itaque repudiandae molestiae natus beatae fuga. Eveniet, nihil.
        </p>
    </div>
</template>

<script>
export default {
  data () {
    return {
      name: 'Batman'
    }
  },
  //  untuk memberi ijin kepada Parent (App.vue) untuk dapat mengubah data dari Child (About.vue)
  props: ['name']


}
</script>