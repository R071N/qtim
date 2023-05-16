<template>
  <header id="masthead" class="site-header">
    <div class="site-branding">
      <h1 class="site-title">
        <NuxtLink to="/" rel="home">Moschino</NuxtLink>
      </h1>
      <h2 class="site-description">Minimalist Portfolio HTML Template</h2>
    </div>
    <nav id="site-navigation" class="main-navigation">
      <button class="menu-toggle">Menu</button>
      <a class="skip-link screen-reader-text" href="#content">Skip to content</a>
      <div class="menu-menu-1-container">
        <ul id="menu-menu-1" class="menu">
          <li>
            <NuxtLink to="/">Home</NuxtLink>
          </li>
          <li>
            <NuxtLink to="/">About</NuxtLink>
          </li>
          <li>
            <NuxtLink to="/">Shop</NuxtLink>
          </li>
          <li>
            <NuxtLink to="/">Blog</NuxtLink>
          </li>
          <li>
            <NuxtLink to="/">Elements</NuxtLink>
          </li>
          <li>
            <NuxtLink to="/">Pages</NuxtLink>
            <ul class="sub-menu">
              <li>
                <NuxtLink to="/">Portfolio Item</NuxtLink>
              </li>
              <li>
                <NuxtLink to="/">Blog Article</NuxtLink>
              </li>
              <li>
                <NuxtLink to="/">Shop Item</NuxtLink>
              </li>
              <li>
                <NuxtLink to="/">Portfolio Category</NuxtLink>
              </li>
            </ul>
          </li>
          <li>
            <NuxtLink to="/">Contact</NuxtLink>
          </li>
        </ul>
      </div>
    </nav>
  </header>
</template>
