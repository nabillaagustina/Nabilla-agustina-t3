
<script>
export default {
  name: 'App',
  data() {
    return {
      products: [
        { name: 'Botol Hijau', desc: 'Botol minum ramah lingkungan.', image: 'botol.jpg' },
        { name: 'Kacamata Hitam', desc: 'Kacamata gaya Ray-Ban.', image: 'kacamata.jpg' },
        { name: 'Parfum Chanel', desc: 'Parfum elegan untuk wanita modern.', image: 'parfum.jpg' },
        { name: 'Headphone', desc: 'Headphone wireless kualitas tinggi.', image: 'headphone.jpg' }
      ]
    };
  },
  methods: {
    getImage(fileName) {
      return new URL(`./assets/${fileName}`, import.meta.url).href;
    }
  }
};
</script>

<style scoped>
body {
  padding-top: 56px;
}
.card-img-top {
  height: 300px;
  object-fit: cover;
}
</style>
