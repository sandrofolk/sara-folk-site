<template>
  <div>
    <b-navbar toggleable="lg" type="dark" id="menu">
      <b-navbar-brand href="#">
        <b-img src="@/assets/img/logos/logo.png" height="100px" alt=""/>
      </b-navbar-brand>

      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav>
        <!--      <b-navbar-nav class="mx-auto">-->
        <!--        <b-nav-item href="#">Dra. Sara Folk</b-nav-item>-->
        <!--        <b-nav-item href="#" disabled>Disabled</b-nav-item>-->
        <!--      </b-navbar-nav>-->

        <!-- Right aligned nav items -->
        <b-navbar-nav class="ml-auto">
<!--          <b-nav-item href="#">Dra. Sara Folk</b-nav-item>-->
          <b-nav-item-dropdown text="Tratamentos Corporais" right>
            <b-dropdown-item :key="s.title" v-for="s in tratamentos.corporais" v-scroll-to="`#${s.name}`">
              <nuxt-link :to="`/#${s.name}`">{{ s.title }}</nuxt-link>
            </b-dropdown-item>
          </b-nav-item-dropdown>

          <b-nav-item-dropdown text="Tratamentos Faciais" right>
            <b-dropdown-item :key="s.title" v-for="s in tratamentos.faciais" v-scroll-to="`#${s.name}`">
              <nuxt-link :to="`/#${s.name}`">{{ s.title }}</nuxt-link>
            </b-dropdown-item>
          </b-nav-item-dropdown>

<!--          <b-nav-item href="#">Contato</b-nav-item>-->

          <b-nav-item href="https://www.facebook.com/fisioterapiasarafolk/" target="_blank"><span class="d-inline d-lg-none">Facebook </span>
            <fa-icon :icon="['fab', 'facebook']"/>
          </b-nav-item>
          <b-nav-item href="https://www.instagram.com/fisioterapiasarafolk/" target="_blank"><span class="d-inline d-lg-none">Instagram </span>
            <fa-icon :icon="['fab', 'instagram']"/>
          </b-nav-item>
          <!--<b-nav-form>-->
          <!--  <b-form-input size="sm" class="mr-sm-2" placeholder="Search"></b-form-input>-->
          <!--  <b-button size="sm" class="my-2 my-sm-0" type="submit">Search</b-button>-->
          <!--</b-nav-form>-->

          <!--        <b-nav-item-dropdown text="Lang" right>-->
          <!--          <b-dropdown-item href="#">EN</b-dropdown-item>-->
          <!--          <b-dropdown-item href="#">ES</b-dropdown-item>-->
          <!--          <b-dropdown-item href="#">RU</b-dropdown-item>-->
          <!--          <b-dropdown-item href="#">FA</b-dropdown-item>-->
          <!--        </b-nav-item-dropdown>-->

          <!--        <b-nav-item-dropdown right>-->
          <!--          &lt;!&ndash; Using 'button-content' slot &ndash;&gt;-->
          <!--          <template v-slot:button-content>-->
          <!--            <em>User</em>-->
          <!--          </template>-->
          <!--          <b-dropdown-item href="#">Profile</b-dropdown-item>-->
          <!--          <b-dropdown-item href="#">Sign Out</b-dropdown-item>-->
          <!--        </b-nav-item-dropdown>-->
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
    <section class="servicos" style="min-height: 300px;">
      <div class="bg"></div>
      <b-container fluid="xl">
        <b-row :key="s.title" v-for="s in services" align-h="center" class="mb-5">
          <b-col cols="10" class="mb-1">
            <h1 :id="s.name" v-text="s.title"/>
          </b-col>
          <b-col cols="10" sm="6" md="4" :order="s.order">
            <b-img :src="s.img" thumbnail fluid-grow alt="" class="service"></b-img>
          </b-col>
          <b-col cols="12" sm="6" align-self="center">
            <div v-html="s.description"/>
          </b-col>
        </b-row>
      </b-container>
    </section>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  data() {
    let tratamentos = {
      corporais: [
        {
          title: 'Drenagem Linfática',
          name: 'drenagem-linfatica',
          description:
            '<p>É uma massagem terapêutica que utiliza movimentos e pressões leves, com o objetivo de diminuir ' +
            'a retenção de líquido e dores. Indicada para Gestantes, pacientes com Linfedema, Pré e Pós Operatório ' +
            'de Cirurgias Plásticas e Vasculares.</p>' +
            '<p><strong>Pode ser feito em todo o corpo e rosto!</strong></p>',
          img: require('@/assets/img/services/drenagem_linfatica.jpg')
        },
        {
          title: 'Pré e Pós Operatório',
          name: 'pre-e-pos-operatorio',
          description:
            '<p>A fisioterapia atua desde o pré operatório, avaliando as condições da pele do paciente e também ' +
            'orientando sobre os cuidados imediatos pós cirurgia, testes de alergia quanto ao uso de bandagens ' +
            'elásticas e o trabalho e execução da fisioterapia respiratória bem como exercício metabólicos para o ' +
            'paciente realizar logo após a cirurgia.</p>' +
            '<p>Iniciado a partir do 2° ao 4° dia, o Pós Operatório visa amenizar os sintomas e ajudar na recuperar ' +
            'geral do paciente, utilizando técnicas fisioterapêuticas, como cinesioterapia, exercícios terapêuticos, ' +
            'respiratórios, uso de bandagem elástica e drenagem linfática.</p>' +
            '<p><strong>Pós Operatório é reabilitação!</strong></p>',
          img: require('@/assets/img/services/pre_e_pos_operatorio.jpg'),
          order: 1
        },
        {
          title: 'Massagem Modeladora',
          name: 'massagem-modeladora',
          description:
            '<p>Com movimentos rápidos e pressão moderada, a massagem modeladora ajuda na ativação da circulação, ' +
            'aumento da temperatura corporal, melhorando a oxigenação celular, amenizando e prevenindo a ' +
            'Lipodistrofia Ginóide (celulite) e auxiliando para um melhor contorno corporal.</p>',
          img: require('@/assets/img/services/massagem_modeladora.jpg')
        },
        {
          title: 'Massagem Terapêutica',
          name: 'massagem-terapeutica',
          description:
            '<p>Massagem realizada com movimentos firmes e suaves.<br>' +
            'Excelente alternativa para dores musculares, causadas pela dia a dia decorrentes de má postura, ' +
            'movimentos repetitivos e estresse. <br>' +
            'Esses movimentos promovem liberação de hormônios relaxantes, como a ocitocina, serotonina causando ' +
            'um bem estar fisico e psicológico.</p>',
          img: require('@/assets/img/services/massagem_terapeutica.jpg'),
          order: 1
        }
      ],
      faciais: [
        {
          title: 'Limpeza de pele Profunda',
          name: 'limpeza-de-pele-profunda',
          description:
            '<p>Com a poluição do dia a dia, uso de protetores e cremes faciais, nossa pele sofre constante agressão.</p>' +
            '<p>A limpeza de pele profunda visa restaurar, reequilibrar e limpar a pele não só do rosto mas também ' +
            'do pescoço, colo e das costas. Ela consiste não só dá higienização mas também na extração de comedões ' +
            '(os famosos cravinhos), acnes não inflamadas e a revitalização da pele.<br>Também podem ser utilizados ' +
            'na limpeza de pele recursos dermatofuncionais, como peelings químicos (ácidos) e mecânicos (diamante), ' +
            'ledterapia e alta frequência.</p>' +
            '<p>Com duração em torno de 2 horas, é um tratamento completo para quem deseja manter a pele sempre limpa.</p>',
          img: require('@/assets/img/services/limpeza_de_pele.jpg')
        },
        {
          title: 'Microagulhamento',
          name: 'microagulhamento',
          description:
            '<p>É um procedimento em que agulhas muito finas perfuram delicadamente a pele em suas várias camadas. É ' +
            'realizada com aparelhos de roller ou canetas especificas para microagulhamento.<br>' +
            'Para cada camada atingida um objetivo específico.</p>' +
            '<p>Suas indicações são: <strong>estimulo do colágeno, flacidez de pele, sinais de expressão, cicatrizes de acnes, manchas, estrias e até para tratamento de alopécias</strong>.</p>',
          img: require('@/assets/img/services/microagulhamento.jpg'),
          order: 1
        },
        {
          title: 'Peeling de Diamante',
          name: 'peeling-de-diamante',
          description:
            '<p>Também conhecido como microdermoabrasão, seu principal objetivo é remover as células mortas da pele. ' +
            'Consiste em uma aparelho de sucção e uma ponteira abrasiva onde será feita uma esfoliação da pele.</p>' +
            '<p>É um tratamento indolor e pode ser aplicado não só no rosto mas também em pescoço, colo e corpo para ' +
            'tratamento de estrias. Associado a outros tratamentos, como a limpeza de pele, podendo amenizar também ' +
            'sinais de expressão e manchas.</p>',
          img: require('@/assets/img/services/peeling_de_diamante.jpg')
        }
      ]
    };
    return {
      services: tratamentos.corporais.concat(tratamentos.faciais),
      tratamentos: tratamentos
    }
  }
})
</script>
