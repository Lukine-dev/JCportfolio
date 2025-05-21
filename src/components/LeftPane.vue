<template>
  <div class="left">
    <div class="mt-5">
      <h1><strong>{{ info.name }}</strong></h1>
      <p><strong>Email:</strong> {{ info.email }}</p>
      <p><strong>Role:</strong> {{ info.role }}</p>
      <p><strong>About:</strong> {{ info.about }}</p>
    </div>
      <div>
          <nav class="mt-5">
                  <ul class="list-unstyled">
                  <li ><a href="#about" class="nav-link">ABOUT</a></li>
                  <li ><a href="#about" class="nav-link" >TECHNOLOGIES</a></li>
                  <li ><a href="#experience" class="nav-link">EXPERIENCE</a></li>
                  <li ><a href="#projects" class="nav-link">PROJECTS</a></li>
                  <li ><a href="#certificates" class="nav-link">CERTIFICATES</a></li>
                  </ul>
          </nav>

          <div class="mt-auto socials">
              <!-- Social Icons -->
                  <a class="mx-2" href="https://linkedin.com/in/justine-carl-mantua-778346222"><i class="bi bi-linkedin text-white mx-1"></i></a>
                  <a class="mx-2" href="https://github.com/Lukine-dev"><i class="bi bi-github text-white mx-1"></i></a>
                  <a class="mx-2" href="https://www.facebook.com/justiine.mantua"><i class="bi bi-facebook text-white mx-1"></i></a>
          </div>
      </div>
    </div>
</template>

<script>
export default {
  data() {
    return {
      info: {
        name: 'Justine Carl P. Mantua',
        email: 'justinecarlmantua.dev@gmail.com',
        role: 'Full Stack Developer',
        about: 'Web developer experienced in different tech stacks and languages.'
      }
    }
  }
}
</script>

<style>
.left{
  color: #fff;
}
.nav-link {
  text-decoration: none;
  display: block;
  margin: 8px 0;
  font-weight: 500;
  transition: all 1s ease-in-out;
  color: #fff;
}
.nav-link:hover {
  transform: scale(1.05);
  color: blueviolet;
  transform: translateX(1%);
  
}
.socials{
  position: fixed;
  bottom: 10%;
  font-size: medium;
}
</style>