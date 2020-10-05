/* eslint-disable prettier/prettier */
<template>
  <div>
    <div class="container flex flex-wrap lg:flex-no-wrap my-16">
      <div class="lg:w-4/12 w-full order-last">
        <div class="box bg-gray-200 rounded text-center text-xl py-8 lg:mr-10">
          <div>Contactez-nous</div>
          <div class="font-bold">+33 6 78 34 94 12</div>
          <div class="font-bold mb-3">contat@vync.fr</div>
          <div>Rencontrez-nous</div>
          <div class="font-bold mb-3">229 rue Emile Zola</div>
          <div>Suivez-nous</div>
          <ul class="flex icon-list justify-center">
            <li>
              <IconLinkedin />
            </li>
            <li>
              <IconTwitter />
            </li>
            <li>
              <IconFacebook />
            </li>
          </ul>
        </div>
        <!-- <div class="h-20 bg-blue-500 mr-10">Map</div> -->
      </div>
      <div class="flex-grow mb-10">
        <div class="box">
          <h2 class="text-4xl font-bold text-theme mb-6">
            Vous avez un projet? Dites nous en plus
          </h2>
          <p class="text-xl mb-6">
            Nous vous accueillons dans notre agence, au cœur de Paris pour
            parler de votre projet. Notre équipe se fera un plaisir de vous
            écouter autour d’un café!
          </p>

          <form @submit.prevent="send">
            <NizForm label="Prénom" :required="true" />
            <NizForm label="Nom" :required="true" />
            <NizForm label="Email" :required="true" />
            <NizForm label="Téléphone" :required="true" />
            <NizForm label="Société" :required="true" />
            <NizForm label="Message" :required="true" :textarea="true" />
            <div class="text-center">
              <input
                type="submit"
                class="bg-theme text-white py-2 px-5 rounded"
                value="Envoyer"
              />
            </div>
          </form>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import NizForm from './components/NizForm'
export default {
  components: {
    NizForm,
  },
  methods: {
    send() {
      console.log('send')
    },
  },
}
</script>
<style scoped lang="scss">
.icon-list {
  svg {
    @apply h-6 w-6 fill-current text-gray-700;
  }
  li {
    &:not(:last-child) {
      @apply mr-2;
    }
  }
}
</style>
