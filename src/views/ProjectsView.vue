<script setup>
import ButtonBox from '../components/ButtonBox.vue'
import ProjectShow from '@/components/ProjectShow'
</script>

<template>
  <div class="content">
    <div class="grid">
      <div class="box box-width-4">
        <div class="box-content about-me">
          <div class="my-memoji">
            <img class="my-memoji-image" :src="require('@/assets/images/me-dev.png')" alt="Mon moi">
          </div>
          <div class="my-presentation">
            <div class="title">
              C'est toujours moi... <img src="@/assets/images/emojis/waving-hand.png" alt="Hey" class="waving-hand">
            </div>
            <div class="description">Mais en train de développer</div>
            <span>
            Mes projets peuvent vous donner un aperçu de mon travail
            <img src="@/assets/images/emojis/eyes.png" alt="Hey" class="eyes">
          </span>
          </div>
        </div>
      </div>

      <ButtonBox class="box-width-3-height-2"
                 data-project="cosplay"
                 :background-url="require('@/assets/images/projects/cosplay/cosplay.png')"
                 @click="openProjectView">
        <template #button>Découvrir</template>
      </ButtonBox>

      <ButtonBox class="box-width-2"
                 data-project="merit"
                 :background-url="require('@/assets/images/projects/merit/merit.png')"
                 @click="openProjectView">
        <template #button>Y jeter un coup d'oeil</template>
      </ButtonBox>

      <ButtonBox class="box-width-2"
                 data-project="habbox"
                 :background-url="require('@/assets/images/projects/habbox/habbox.png')"
                 @click="openProjectView">
        <template #button>Explorer</template>
      </ButtonBox>
    </div>
    <ProjectShow id="cosplay">
      <template #icon>
        <img :src="require('@/assets/images/projects/cosplay/cosplay-logo.png')" alt="Cosplay" class="logo">
      </template>
      <template #title>Une application mobile</template>
      <template #small-description>Il s'agit d'un projet scolaire réalisé en groupe lors de mon Mastère 1 Développement Web &
        Mobile.
      </template>
      <template #big-description>
        <p>
          Pour ce projet qui a été développé en équipe, nous devions réalisé un réseau social sous la forme d'une
          application mobile.
          <span class="mt-1 d-block">
            Projet réalisé sous <b>React Native</b> pour le côté Front-End et sous <b>NodeJS (API GraphQL)</b> pour le côté Back-End.
          </span>
        </p>
      </template>
      <template #default>
        <div :style="{backgroundImage: 'url(' + require('@/assets/images/projects/cosplay/1.png') + ')'}" class="two-col-two-rows"></div>
        <div :style="{backgroundImage: 'url(' + require('@/assets/images/projects/cosplay/2.png') + ')'}" class="two-col-two-rows"></div>
        <div :style="{backgroundImage: 'url(' + require('@/assets/images/projects/cosplay/3.png') + ')'}" class="two-col-two-rows"></div>
      </template>
    </ProjectShow>
    <ProjectShow id="merit">
      <template #icon>
        <img :src="require('@/assets/images/projects/merit/merit-logo.svg')" alt="MERIT" class="logo merit">
      </template>
      <template #title>Un outil pour les ressources humaines</template>
      <template #small-description>Il s'agit d'un projet professionnel que j'ai effectué lors de mon alternance.
      </template>
      <template #big-description>
        <p>
          Cet outil a pour but de simplifier les campagnes salariales internes de l'entreprise. Avant l'arrivée de ce
          projet, toutes les propositions de mesures salariales se faisaient par l'intermédiaire d'un fichier Excel
          partagé.
          <span class="mt-1 d-block">
            Projet réalisé sous <b>Symfony 5</b> et <b>Bootstrap</b>.
          </span>
        </p>
      </template>
      <template #default>
        <div :style="{backgroundImage: 'url(' + require('@/assets/images/projects/merit/1.png') + ')'}" class="two-rows-two-col"></div>
        <div :style="{backgroundImage: 'url(' + require('@/assets/images/projects/merit/2.png') + ')'}"></div>
        <div :style="{backgroundImage: 'url(' + require('@/assets/images/projects/merit/4.png') + ')'}"></div>
        <div :style="{backgroundImage: 'url(' + require('@/assets/images/projects/merit/3.png') + ')'}" class="four-col"></div>
      </template>
    </ProjectShow>
    <ProjectShow id="habbox">
      <template #icon>
        <img :src="require('@/assets/images/projects/habbox/habbox-logo.gif')" alt="Habbox" class="logo">
      </template>
      <template #title>Le site web d'un jeu vidéo</template>
      <template #small-description>Il s'agit d'un projet personnel qui m'a permis de m'améliorer en UI/UX.</template>
      <template #big-description>
        <p>
          Ce jeu vidéo a ouvert ses portes en 2016 et accueille chaque jour plusieurs joueurs passionnés par la
          construction d'appartements.
          <span class="mt-1 d-block">
            C'est en 2021 que l'on m'a contacté dans le but de refondre totalement le design du site qui commençait à se
            faire vieux et pour y rajouter quelques fonctionnalités.
          </span>
        </p>
      </template>
      <template #default>
        <div :style="{backgroundImage: 'url(' + require('@/assets/images/projects/habbox/1.png') + ')'}" class="four-col"></div>
        <div :style="{backgroundImage: 'url(' + require('@/assets/images/projects/habbox/2.png') + ')'}" class="two-rows-two-col"></div>
        <div :style="{backgroundImage: 'url(' + require('@/assets/images/projects/habbox/4.png') + ')'}"></div>
        <div :style="{backgroundImage: 'url(' + require('@/assets/images/projects/habbox/3.png') + ')'}"></div>
      </template>
    </ProjectShow>
  </div>
</template>

<script>
export default {
  methods: {
    openProjectView: function (event) {
      const view = document.getElementById(event.target.closest('.box').getAttribute('data-project'))
      view.classList.remove('d-none')
      document.body.style.overflow = 'hidden'
    }
  }
}
</script>
