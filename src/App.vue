<template>
  <div class="container-fluid" id="main">
    <div class="container">
        <div class="row justify-content-center">
          <div class="col-lg-10">
               <div class="row">
                <div class="col-md-5 left-pane" data-aos="fade-up" data-aos-delay="400" data-aos-duration="1000">
                  <LeftPane />
                </div>
                <div class="col-md-7 right-pane" data-aos="fade-left" data-aos-delay="400" data-aos-duration="1000">
                  <div class="container">
                       <div id="about">
                          <AboutSection />     
                          <TechStackSection />   
                        </div>

                        <div id="experience">
                            <WorkExperienceSection />
                        </div>

                        <div id="projects">
                             <Projects />
                        </div>

                        <div id="certificates">
                              <Certificates />
                        </div>
                      
                  </div>
                </div>
              </div>
          </div>
        </div>
    </div>
   
  </div>
</template>

<script>
import LeftPane from './components/LeftPane.vue'
import Projects from './components/PortfolioProjects.vue'
import Certificates from './components/PortfolioCertificates.vue'
import AboutSection from "./components/AboutMe.vue";
import TechStackSection from "./components/TechStack.vue";
import WorkExperienceSection from "./components/WorkExperience.vue";

export default {
  components: {
    LeftPane,
    Projects,
    Certificates,
    AboutSection,
    TechStackSection,
    WorkExperienceSection
  }
}

if (typeof window !== 'undefined') {
  document.addEventListener('DOMContentLoaded', () => {
    const cursor = document.createElement('div');
    cursor.classList.add('glowing-cursor');
    document.body.appendChild(cursor);

    document.addEventListener('mousemove', e => {
      cursor.style.top = `${e.clientY}px`;
      cursor.style.left = `${e.clientX}px`;
    });
  });
}
</script>

<style>
body, html {
  height: 100%;
  margin: 0;
  justify-content: center;
  align-items: center;
  overflow: hidden;
  font-size: small;
}
 


#main{
  display: flex;
  justify-content: center;
  align-items: center;
  overflow: hidden;
  background: linear-gradient(-45deg, #101010, #450260, #101010, #101010);
  background-size: 200% 200%;
  animation: breathingGradient 15s ease infinite;
}

@keyframes breathingGradient {
  0% {
    background-position: 0% 50%;
  }
  50% {
    background-position: 100% 50%;
  }
  100% {
    background-position: 0% 50%;
  }
}




.left-pane {
  height: 100vh;
  overflow: hidden;
  padding: 2rem;
  font-size: small;
}
.right-pane {
  padding: 2rem;
  height: 100vh;
  overflow-y: auto;
  color: #fff;
    /* Hide scrollbar for Webkit (Chrome, Safari) */
  scrollbar-width: none; /* Firefox */
  -ms-overflow-style: unset;  /* IE 10+ */
   scroll-behavior: smooth;

}

.right-pane::-webkit-scrollbar {
  display: none;  /* Chrome, Safari, Opera */
}


</style>
