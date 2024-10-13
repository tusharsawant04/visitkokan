<template>
  <nav class="navbar navbar-expand-lg navbar-light bg-light">
    <a class="navbar-brand" href="/en-in.html">
      <img src="" alt="kokan" title="kokan" class="dt-navbar-brand-icon" />
    </a>

    <button
      class="navbar-toggler"
      type="button"
      @click="toggleMobileMenu"
      aria-controls="navbarNav"
      aria-expanded="false"
      aria-label="Toggle navigation"
    >
      <span class="navbar-toggler-icon"></span>
    </button>

    <div class="collapse navbar-collapse" id="navbarNav">
      <ul class="navbar-nav">
        <li class="nav-item" v-for="(item, index) in navItems" :key="index">
          <a
            class="nav-link"
            href="#"
            @click.prevent="handleDropdown(index)"
          >
            {{ item.label }}
          </a>
          <ul v-if="item.isOpen" class="dropdown-menu d-flex gap-2 p-1 flex-wrap">
            <li v-for="(subItem, subIndex) in item.dropdownItems" :key="subIndex">
            <div class="">
           
             <a class="dropdown-item" :href="subItem.link">
           <div class="d-flex flex-column align-items-center shadow p-2 rounded flex-wrap">
             <img :src="subItem.image" alt="" class="dropdown-icon rounded mb-1" />
                <span class="text-center">{{ subItem.title }}</span>
                </div>
              </a>
 
            </div>
            </li>
          </ul>
        </li>
      </ul>

      <div class="ml-auto navbar-icons">
        <a href="/en-in/explore.html" class="nav-icon">
          <img aria-label="explore map" alt="Explore by map" src="" />
        </a>

        <span id="ta-common-favourites-header">
          <a href="/en-in/wishlist.html" class="nav-icon">
            <img src="" alt="favourite-icon" />
            <span class="badge badge-pill badge-danger my-trip-count">1</span>
          </a>
        </span>

        <a href="#" class="nav-icon">
          <img alt="Search the site" aria-label="search" src="" />
        </a>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  data() {
    return {
   navItems: [
        { 
          label: 'Be inspired', 
          isOpen: false,
          dropdownItems: [
            { title: 'Inspiration 1', image: 'https://i.ibb.co/CPsLShg/cat3.jpg', link: 'link-to-page-1.html' },
            { title: 'Inspiration 2', image: 'https://i.ibb.co/CPsLShg/cat3.jpg', link: 'link-to-page-2.html' },
          ]
        },
        { 
          label: 'Places to go', 
          isOpen: false,
          dropdownItems: [
            { title: 'Place 1', image: 'https://i.ibb.co/CPsLShg/cat3.jpg', link: 'link-to-page-3.html' },
            { title: 'Place 2', image: 'https://i.ibb.co/CPsLShg/cat3.jpg', link: 'link-to-page-4.html' },
          ]
        },
        { 
          label: 'Things to do', 
          isOpen: false,
          dropdownItems: [
            { title: 'Activity 1', image: 'link-to-image-5.jpg', link: 'link-to-page-5.html' },
            { title: 'Activity 2', image: 'link-to-image-6.jpg', link: 'link-to-page-6.html' },
          ]
        },
        { 
          label: 'Plan your trip', 
          isOpen: false,
          dropdownItems: [
            { title: 'Plan 1', image: 'link-to-image-7.jpg', link: 'link-to-page-7.html' },
            { title: 'Plan 2', image: 'link-to-image-8.jpg', link: 'link-to-page-8.html' },
          ]
        },
      ],
    };
  },
  methods: {
    toggleMobileMenu() {
      const navbarCollapse = document.getElementById('navbarNav');
      if (navbarCollapse) {
        navbarCollapse.classList.toggle('show');
      }
    },
    handleDropdown(index) {
      this.navItems.forEach((item, idx) => {
        item.isOpen = idx === index ? !item.isOpen : false; // Toggle current and close others
      });
      console.log(`Dropdown for ${this.navItems[index].label} clicked`);
    },
  },
};
</script>

<style scoped>
.navbar-icons {
  display: flex;
  align-items: center;
}
.nav-icon {
  margin-left: 15px;
}
.dropdown-menu {
  display: none; /* Hide by default */
  position: absolute; /* Positioning */
  background-color: white; /* Dropdown background */
  border: 1px solid #ccc; /* Optional: border for visibility */
  z-index: 1000; /* Ensure it appears above other elements */
}
.dropdown-menu.show {
  display: block; /* Show when active */
}
</style>
