<template>
  <div>
    <section class="py-16 bg-theme text-gray-200">
      <div class="container">
        <div class="lg:w-7/12">
          <h2 class="text-4xl font-bold mb-5">
            VYNC est spécialisée dans la conception et le développement de
            solutions digitales sur-mesure.
          </h2>
          <h3 class="lg:w-9/12 text-2xl font-medium mb-5">
            Vous souhaitez automatiser vos tâches, améliorer l’UX de vos outils,
            injecter de l’intelligence dans vos processus métier ?
          </h3>
          <p class="lg:w-9/12 text-xl">
            Notre agence experte analyse vos besoins, pilote vos projets, et
            vous accompagne dans la conception et le développement de vos
            projets digitaux dans la durée
          </p>
        </div>
      </div>
    </section>
    <Divider direction="top right" :size="5" class="text-theme fill-current" />
    <section class="py-16">
      <div class="container">
        <div class="flex justify-center mb-10">
          <h2 class="font-bold text-4xl text-gray-800">Notre fonctionnement</h2>
        </div>

        <div
          class="section lg:w-10/12 mx-auto flex items-center justify-between"
        >
          <div class="lg:w-6/12">
            <ZigZagItem number="#1" text="Comprendre votre besoin" />
          </div>
          <div class="lg:w-6/12">
            <div
              class="bg-contain bg-cover bg-center h-64 bg-no-repeat"
              style="
                background-image: url('https://assets.landen.co/1/taking_notes_tjaf.svg');
              "
            ></div>
          </div>
        </div>

        <div
          class="section lg:w-10/12 mx-auto flex items-center justify-between"
        >
          <div class="lg:w-6/12">
            <div
              class="bg-contain bg-cover bg-center h-64 bg-no-repeat"
              style="
                background-image: url('https://assets.landen.co/1/all_the_data_h4ki.svg');
              "
            ></div>
          </div>
          <div class="lg:w-6/12 flex justify-end">
            <ZigZagItem number="#2" text="Utiliser nos outils de mesure" />
          </div>
        </div>

        <div
          class="section lg:w-10/12 mx-auto flex items-center justify-between"
        >
          <div class="lg:w-6/12">
            <ZigZagItem number="#3" text="Définir la solution appropriée" />
          </div>
          <div class="lg:w-6/12">
            <div
              class="bg-contain bg-cover bg-center h-64 bg-no-repeat"
              style="
                background-image: url('https://assets.landen.co/1/career_progress_ivdb.svg');
              "
            ></div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import ZigZagItem from './index/ZigZagItem'
export default {
  components: {
    ZigZagItem,
  },
}
</script>
