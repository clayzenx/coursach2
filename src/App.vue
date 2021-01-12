<template>
  <div class="container column">
    <app-constructor-form class="card-w30" @addComponent="addComponent"></app-constructor-form>

    <div class="card card-w70">
      <div v-if="components.length > 0">
        <component
            v-for="component in components"
            :key="component.id"
            :is="'app-' + component.type + '-component'"
            :value="component.value">
        </component>
      </div>
      <h3 v-else>Добавьте первый блок, чтобы увидеть результат</h3>
    </div>
  </div>

  <div class="container">
    <app-comments-block></app-comments-block>
  </div>
</template>

<script>
import AppConstructorForm from "./components/AppConstructorForm";
import AppTitleComponent from "./components/AppTitleComponent";
import AppAvatarComponent from "./components/AppAvatarComponent";
import AppSubTitleComponent from "./components/AppSubTitleComponent";
import AppTextComponent from "./components/AppTextComponent";
import AppCommentsBlock from "./components/AppCommentsBlock";

export default {
  data() {
    return {
      components: []
    }
  },

  methods: {
    addComponent(component) { if (component) this.components.push(component) }
  },

  components: { AppCommentsBlock, AppTextComponent, AppSubTitleComponent, AppAvatarComponent, AppTitleComponent, AppConstructorForm },
}
</script>


