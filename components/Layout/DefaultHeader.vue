<template>
  <VAppBar>
    <template #prepend>
      <VAppBarTitle>Application Bar</VAppBarTitle>
    </template>
    <template #default>
      <div class="mr-2">
        <NuxtLink v-for="{ label, to } in links" :key="label" :to="to">
          <VBtn>{{ label }}</VBtn>
        </NuxtLink>
        <VMenu transition="slide-y-transition">
          <template #activator="{ props }">
            <VAvatar class="avatar" icon="$vuetify" size="58" v-bind="props"></VAvatar>
          </template>
          <v-list>
            <v-list-item v-for="(item, i) in links" :key="i">
              <NuxtLink to="/">
                <v-list-item-title>{{ item.label }}</v-list-item-title>
              </NuxtLink>
            </v-list-item>
          </v-list>
        </VMenu>
      </div>
      <VMenu />
    </template>
  </VAppBar>
</template>

<script lang="ts" setup>
const links = [
  {
    label: 'hallo',
    to: '/'
  },
  {
    label: 'hall2',
    to: '/'
  }
]
</script>

<style scoped>
.avatar {
  cursor: pointer;
}
</style>
