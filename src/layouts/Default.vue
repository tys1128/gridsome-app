<template>
  <div class="layout">
    <header class="header fixed w-full z-10">
      <strong class="mr-auto">
        <g-link to="/" class="flex items-center">
          <img src="/assets/logo.svg" alt="logo NWA" class="h-6 px-1" />
          <!-- {{ $static.metadata.siteName }} -->
        </g-link>
      </strong>
      <nav class="nav font-semibold">
        <g-link class="nav__link mx-4" to="/journal/">Journal</g-link>
        <g-link class="nav__link mx-4" to="/contact/">contact</g-link>
      </nav>
    </header>
    <slot />
    <span class="block text-sm my-24">Copyright © 2021</span>
  </div>
</template>

<static-query>
query {
  metadata {
    siteName
  }
}
</static-query>

<style>
body {
  font-family: -apple-system, system-ui, BlinkMacSystemFont, "Segoe UI", Roboto,
    "Helvetica Neue", Arial, sans-serif;
  margin: 0;
  padding: 0;
  line-height: 1.5;
}

.layout {
  max-width: 760px;
  margin: 0 auto;
  padding-left: 20px;
  padding-right: 20px;
}

.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  max-width: 760px;
  margin-bottom: 20px;
  height: 80px;
}

.nav__link {
  margin-left: 20px;
}
</style>
