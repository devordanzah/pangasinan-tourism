<template>
  <header class="header">
    <div class="header__container">

      <!-- Logo -->
      <router-link
        to="/"
        class="brand"
        aria-label="Pangasinan Heritage Home"
      >
        <div class="brand__icon">
          P
        </div>

        <div class="brand__text">
          <strong>Pangasinan</strong>
          <span>HERITAGE</span>
        </div>
      </router-link>


      <!-- Navigation -->
      <nav class="navigation">
        <router-link
          to="/"
          class="navigation__link"
        >
          Home
        </router-link>

        <a
          href="#heritage"
          class="navigation__link"
        >
          Heritage Sites
        </a>
      </nav>
      
      <div class="search">
        <span>🔍</span>

        <input
          type="search"
          placeholder="Search places..."
          aria-label="Search heritage sites"
        />
      </div>

    </div>
  </header>
</template>

<script>
export default {
  name: 'HeaderNavigation'
}
</script>

<style scoped>

.header {
  position: sticky;
  top: 0;
  z-index: 1000;

  background: rgba(255, 255, 255, 0.96);

  border-bottom: 1px solid #e5e8e6;

  backdrop-filter: blur(10px);
}


.header__container {
  width: 100%;
  max-width: 1200px;

  min-height: 72px;

  margin: 0 auto;

  padding: 10px 20px;

  display: flex;
  align-items: center;

  gap: 30px;
}


.brand {
  display: flex;
  align-items: center;

  gap: 10px;

  text-decoration: none;

  color: #1c2923;

  flex-shrink: 0;
}


.brand__icon {
  width: 40px;
  height: 40px;

  display: flex;
  align-items: center;
  justify-content: center;

  border-radius: 12px;

  background: #176b4d;

  color: white;

  font-weight: 800;
}


.brand__text {
  display: flex;
  flex-direction: column;

  line-height: 1.1;
}


.brand__text strong {
  font-size: 15px;
}


.brand__text span {
  margin-top: 4px;

  color: #176b4d;

  font-size: 9px;

  font-weight: 800;

  letter-spacing: 2px;
}


/* NAVIGATION */

.navigation {
  display: flex;
  align-items: center;

  gap: 5px;
}


.navigation__link {
  padding: 9px 13px;

  border-radius: 9px;

  color: #1c2923;

  text-decoration: none;

  font-size: 14px;

  font-weight: 600;

  transition: 0.2s;
}


.navigation__link:hover {
  background: #e7f3ed;

  color: #176b4d;
}


/* SEARCH */

.search {
  margin-left: auto;

  width: 200px;
  height: 40px;

  display: flex;
  align-items: center;

  gap: 8px;

  padding: 0 12px;

  border: 1px solid #dfe4e1;

  border-radius: 10px;

  background: #f8faf9;
}


.search span {
  font-size: 13px;
}


.search input {
  width: 100%;

  border: none;

  outline: none;

  background: transparent;

  color: #1c2923;

  font-size: 13px;
}


@media (max-width: 700px) {

  .header__container {
    gap: 15px;
  }

  .navigation {
    display: none;
  }

}


@media (max-width: 500px) {

  .brand__text {
    display: none;
  }

  .search {
    width: 160px;
  }

}

</style>