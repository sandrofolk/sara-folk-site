<template>
<div>
  <b-navbar toggleable="lg" type="dark" variant="vermelho-terra">
    <b-navbar-brand href="#">
      <b-img src="@/assets/img/logos/LgRGB_20.png" height="100px" alt="" />
    </b-navbar-brand>

    <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

    <b-collapse id="nav-collapse" is-nav>
      <!--<b-navbar-nav>-->
      <!--  <b-nav-item href="#">Link</b-nav-item>-->
      <!--  <b-nav-item href="#" disabled>Disabled</b-nav-item>-->
      <!--</b-navbar-nav>-->

      <!-- Right aligned nav items -->
      <b-navbar-nav class="ml-auto">
        <b-nav-item href="#">Facebook <fa-icon :icon="['fab', 'facebook']" /></b-nav-item>
        <b-nav-item href="#">Instagram <fa-icon :icon="['fab', 'instagram']" /></b-nav-item>
        <!--<b-nav-form>-->
        <!--  <b-form-input size="sm" class="mr-sm-2" placeholder="Search"></b-form-input>-->
        <!--  <b-button size="sm" class="my-2 my-sm-0" type="submit">Search</b-button>-->
        <!--</b-nav-form>-->

        <!--<b-nav-item-dropdown text="Lang" right>-->
        <!--  <b-dropdown-item href="#">EN</b-dropdown-item>-->
        <!--  <b-dropdown-item href="#">ES</b-dropdown-item>-->
        <!--  <b-dropdown-item href="#">RU</b-dropdown-item>-->
        <!--  <b-dropdown-item href="#">FA</b-dropdown-item>-->
        <!--</b-nav-item-dropdown>-->

        <!--<b-nav-item-dropdown right>-->
        <!--  &lt;!&ndash; Using 'button-content' slot &ndash;&gt;-->
        <!--  <template v-slot:button-content>-->
        <!--    <em>User</em>-->
        <!--  </template>-->
        <!--  <b-dropdown-item href="#">Profile</b-dropdown-item>-->
        <!--  <b-dropdown-item href="#">Sign Out</b-dropdown-item>-->
        <!--</b-nav-item-dropdown>-->
      </b-navbar-nav>
    </b-collapse>
  </b-navbar>
  <section class="servicos" style="min-height: 300px;">
    <div class="bg"></div>
    <b-container fluid="xl">
      <b-row>
        <b-col cols="6">
          <b-img class="rounded" src="https://picsum.photos/1024/400/?image=41" thumbnail fluid alt=""></b-img>
        </b-col>
        <b-col cols="6">
          <h1>Drenagem linfática</h1>
          <h2>cla cla cla</h2>
          <p>Aqui vai um texto</p>
        </b-col>
      </b-row>
    </b-container>
  </section>
</div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({

})
</script>
