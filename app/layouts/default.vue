<template>
  <div>
    <NuxtLayout name="page">
      <template #header>
      <SHeader
        :links="links"
        :socials="socials"
        hide-panel
        links-variant="elegant"
        title="s94.dev"
        sticky
      />
      </template>
      <SMain centered>
        <slot />
      </SMain>
    </NuxtLayout>
    <SFooter
      :separator-avatar="{ src: 'https://avatars.githubusercontent.com/u/13056429?v=4', size: 'lg' }"
      :links="linksGroup"
      :socials="socials"
    >
      <template #legal>
        <div>
          © 1994-{{ new Date().getFullYear() }}, Grown up by
          <NuxtLink class="underline underline-offset-2" target="_blank" to="https://github.com/sandros94">
            <span>Sandros94</span>
          </NuxtLink>
          & parents
        </div>
      </template>
    </SFooter>
  </div>
</template>

<script setup lang="ts">
import type { Links, LinksGroup } from '#s94-ui/types'

const links = useState<Links | undefined>('nav-links')
const socials = useState<Links | undefined>('social-links')
const linksGroup = useState<LinksGroup[] | undefined>('footer-linksGroup')
</script>
