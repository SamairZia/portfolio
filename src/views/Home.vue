<template>
  <div>
    <section id="home" class="site-wrapper">
      <div class="site-title">
        <h1
          class="display-3 orbitron-font text-uppercase site-heading"
        >Samair Zia</h1>
        <h1 class="display-2 orbitron-font">Front-end Developer</h1>
      </div>
    </section>
    <section id="about" class="about-section">
<!-- <span>I don’t like to define myself by the work I’ve done. I define myself by the work I want to do.</span>   -->
      <!-- USING BOOTSTRAP-VUE GRID SYSTEM -->
      <!-- Who am i row start-->
      <b-container>
        <b-row>
          <b-col class="heading-row">
            <h1 class="primary-color roboto-font display-2 mb-3">Who I am.</h1>
          </b-col>
        </b-row>
        <b-row>
          <b-col class="ml-3" sm="6">
            <p
              class="subheading"
            > I am Front-end Developer that specializes in developing Single page Applications / E-Commerce portals using HTML5, CSS3, Javascript, JQuery, Bootstrap etc. Recently I have started exploring Vue.js along with its component framework/library including Vuetify, Element UI.</p>
          </b-col>
          <b-col offset-sm="1" sm="4">
            <div class="mt-3 d-inline-block w-100">
              <p class="float-left primary-color text-uppercase alternates-font">Location:</p>
              <p class="float-right">Karachi, Pakistan</p>
            </div>
            <div class="d-inline-block w-100">
              <p class="float-left primary-color text-uppercase alternates-font">Email:</p>
              <p class="float-right">samairzia1995@gmail.com</p>
            </div>
            <div class="d-inline-block w-100">
              <p class="float-left primary-color text-uppercase alternates-font">Phone:</p>
              <p class="float-right">+92 (312) 8606539</p>
            </div>
          </b-col>
          <!-- <b-col sm="2"></b-col> -->
        </b-row>
      </b-container>
      <!-- Who am i row end-->
      <br>
      <br>

      <!-- What can i do starts -->
      <b-container>
        <b-row>
          <b-col class="heading-row">
            <h1 class="primary-color roboto-font display-2 mb-3">What can I do for you</h1>
            <p class="f-16">A front-end developer's role is to combine design and business logic to achieve a user-facing product. To do this successfully, a wide skill set is necessary to produce a quality user experience that leads to meeting business goals.</p>
          </b-col>
        </b-row>
        <b-row>
          <b-col class="ml-3" sm="11">
            <v-expansion-panel popout dark>
              <v-expansion-panel-content v-for="cando in candolist" :key="cando.heading">
                <template v-slot:header>
                  <div class="f-18">{{ cando.heading }}</div>
                </template>
                <v-card>
                  <v-card-text class="f-16">{{ cando.description }}</v-card-text>
                </v-card>
              </v-expansion-panel-content>
            </v-expansion-panel>
          </b-col>
        </b-row>
      </b-container>
      <!-- What can i do ends -->
    </section>

    <section id="experience" class="experience-section">
      <b-container>
        <b-row>
          <b-col class="heading-row">
            <h1 class="primary-color roboto-font display-2 mb-3">Where I've been</h1>
          </b-col>
        </b-row>
        <b-row>
          <b-col class="ml-3" sm="11">
            <v-timeline>
              <v-timeline-item
                v-for="wherelistcontent in wherelist"
                :key="wherelistcontent.name"
                color="primary-background"
                fill-dot
                small
              >
                <template v-slot:opposite>
                  <span>{{ wherelistcontent.duration }}</span>
                </template>
                <v-card class="elevation-2 white black--text">
                  <v-card-title class="headline">{{ wherelistcontent.name }}</v-card-title>
                  <v-card-text>{{ wherelistcontent.role }} <br v-if="wherelistcontent.role2">
                    {{ wherelistcontent.role2 }} <br v-if="wherelistcontent.role2">
                    {{ wherelistcontent.role3 }} <br v-if="wherelistcontent.role2">
                    {{ wherelistcontent.role4 }}
                  </v-card-text>
                </v-card>
              </v-timeline-item>
            </v-timeline>
          </b-col>
        </b-row>
      </b-container>
    </section>

    <section id="skills" class="skill-education">
      <b-container>
        <b-row>
          <b-col class="heading-row">
            <h1 class="primary-color roboto-font display-2 mb-3">What I Know</h1>
          </b-col>
        </b-row>
        <b-row>
          <b-col class="ml-3" sm="6">
            <br>
            <div class="education-div">
              <h3 class="primary-color font-weight-bold">My Education</h3>
              <div class="education-info" v-for="education in educationlist" :key="education.name">
                <label>{{ education.name }}</label>
                <br>
                <label class="primary-color f-18">{{ education.degree }}</label>
                <br>
                <label>{{ education.majors }}</label>
                <br>
                <label>{{ education.year }}</label>
              </div>
            </div>
          </b-col>
          <b-col sm="5">
            <br>
            <div class="education-div">
              <h3 class="primary-color font-weight-bold">My Skills</h3>
              <div class="skill-info" v-for="skills in skillslist" :key="skills.name">
                <label>{{ skills.name }}</label>
                <span class="ml-2 float-right">
                  <v-icon v-for="i in skills.ratingYes" :key="i">fiber_manual_record</v-icon>
                  <v-icon class="nottt" v-for="j in skills.ratingNo" :key="j">fiber_manual_record</v-icon>
                </span>
              </div>
            </div>
          </b-col>
        </b-row>
      </b-container>
    </section>

    <section id="portfolio" class="portfolio" >
      <b-container>
        <b-row>
          <b-col class="heading-row">
            <h1 class="primary-color roboto-font display-2 mb-3">Some of My Core Projects</h1>
          </b-col>
        </b-row>
        <b-row>
          <b-col offset-sm="1" sm="10">
            <v-carousel hide-controls height="auto" dark class="mt-3 shadow-none">
              <v-carousel-item v-for="portfolio in portfoliolist" :key="portfolio.name">
                <div class="pb-5">
                  <h3 class="primary-color text-sm-center">{{ portfolio.name }}</h3>
                  <p class="text-sm-center">{{ portfolio.project }}</p>
                  <div class="px-5 pt-5 w-80">
                    <p class="primary-color">Project Details</p>
                    <p>{{ portfolio.details }}</p>
                  </div>
                  <div class="px-5 pb-5">
                    <p class="primary-color mt-4">Project Info</p>
                    <v-icon class="f-18 primary-color">settings</v-icon>
                    <label class="ml-3">Tools used:</label>
                    <label class="ml-4">{{ portfolio.tools }}</label>
                    <br>
                    <v-icon class="f-18 primary-color">done_all</v-icon>
                    <label class="ml-3">Project done:</label>
                    <label class="ml-4">{{ portfolio.as }}</label>
                  </div>
                </div>
              </v-carousel-item>
            </v-carousel>
          </b-col>
        </b-row>
      </b-container>
    </section>

    <section id="contact" class="talk">
      <b-container>
        <b-row>
          <b-col class="heading-row">
            <h1 class="primary-color roboto-font display-2 mb-3">Let's talk</h1>
          </b-col>
        </b-row>
        <b-row>
          <b-col class="ml-3" sm="6">
            <h3> Let's create something great! </h3>
            <p class="w-75">If you like my work and have some cool projects to work on or want to hire me, just send me an Email or contact me through social channels.</p>
          </b-col>
          <b-col sm="5">
            <h5 class="primary-color">SOCIAL CONTACTS</h5>
            <a href="https://www.linkedin.com/in/samairzia" target="_blank"><i class='fab fa-linkedin social-icons'></i></a>
            <a href="https://www.facebook.com/SamairZia95" target="_blank"><i class='fab fa-facebook social-icons'></i></a>
            <div class="mt-3">
            <v-icon class="primary-color">
              email
            </v-icon>
              <a class="email-link" href="mailto:samairzia1995@gmail.com"> samairzia1995@gmail.com</a>
              <br><br>
            <v-icon class="primary-color">
              phone
            </v-icon>
              <a class="email-link" href="tel:+923128606539"> +923128606539</a>
            </div>
            
            <div class="to-top" @click="$vuetify.goTo('#home', { offset: -1 })"><i class="fa fa-long-arrow-alt-up"></i> Top</div>
          </b-col>
        </b-row>
      </b-container>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      candolist: [
        {
          heading: "Web Development",
          description: "Either it is Business website, Personal Blog, Single Page Application or E-commerce Store for your brand. I try to develop websites that follow best practices of speed optimization and are built with mobile first approach, With my experience I can Create responsive websites that work on a wide range of devices generating more leads and decreasing your current bounce rate. This is what matters, doesn’t it?"
        },
        { heading: "CMS", description: " I can develop CMS using WordPress, Magento and from the scratch also. " },
        { heading: "SEO", description: " SEO is basically the practice of increasing the quantity and quality of traffic to your website through organic search engine results. I will do SEO of your Business/Blog/E-commerce website to generate more traffic and rank better on Search engines. It will include On page , Off page SEO on multiple Keywords." },
        {
          heading: "Social Media Marketing",
          description: "Social media marketing is a powerful way for businesses of all sizes to reach prospects and customers. Your customers are already interacting with brands through social media, and if you're not speaking directly to your audience through social platforms like Facebook, Twitter, Instagram, and Pinterest, you're missing out! Great marketing on social media can bring remarkable success to your business and can boost your sales."
        }
      ],

      wherelist: [
        {
          name: "Freelance",
          role: "Front-end Development",
          role2: "SEO Services",
          role3: "E-commerce development",
          role4: "Digital Marketing",
          duration: "2017 till date"
        },
        {
          name: "Dataminds",
          role: "Front-end / Wordpress Developer",
          duration: "December 2018 till date"
        },
        {
          name: "Incisivesoft",
          role: "Front-end Developer",
          duration: "November 2018"
        },
        {
          name: "YRM Solution",
          role: "Front-end Developer",
          duration: "June 2018 to October 2018"
        }
      ],

      educationlist: [
        {
          name: "Sir Syed University of Engineering & Technology",
          degree: "Bachelors in Software Engineering",
          majors: "Computer Sciences",
          year: "2014 - 2017"
        },
        {
          name: "DJ Sindh govt. Science College",
          degree: "Intermediate in Pre-Engineering",
          majors: "Physics, Chemistry, Maths",
          year: "2011 - 2013"
        },
        {
          name: "Metropolitan Academy",
          degree: "Matriculation",
          majors: "Biology",
          year: "2010"
        }
      ],

      skillslist: [
        { name: "Javascript", ratingYes: 4, ratingNo: 1 },
        { name: "HTML5", ratingYes: 5, ratingNo: 0 },
        { name: "CSS3", ratingYes: 4, ratingNo: 1 },
        { name: "Bootstrap", ratingYes: 5, ratingNo: 0 },
        { name: "JQuery", ratingYes: 3, ratingNo: 2 },
        { name: "Responsive Design", ratingYes: 5, ratingNo: 0 },
        { name: "Vue.js", ratingYes: 3, ratingNo: 2 },
        { name: "WordPress", ratingYes: 3, ratingNo: 2 },
        { name: "Opencart", ratingYes: 4, ratingNo: 1 },
        { name: "C# .NET", ratingYes: 2, ratingNo: 3 },
        { name: "Android", ratingYes: 2, ratingNo: 3 }
      ],

      portfoliolist: [
        {
          name: "Ambassador - The Custom Shop",
          project: "E-commerce Portal",
          details:
            "E-commerce portal for a Custom-Tailored Suit Franchise – Built a Customized E-commerce portal with admin panel from the scratch on top of Node.js using Handlebars templating engine where Users can create account, place orders, track orders, view products, search products and Admin can add/update products, update order statuses, manage users etc",
          tools:
            "HTML5, CSS3, Javascript, JQuery, Handlebars.js (Templating Engine)",
          as: "As a Freelancer"
        },
        {
          name: "Beautyglance - K-beauty Online Shopping in Pakistan",
          project: "E-commerce Portal",
          details:
            "E-commerce portal for online cosmetic store - Built an e-commerce portal using opencart that can carry out all the standard e-commerce features with admin panel and additional plugins (eg. Facebook messenger, Facebook shop integration, Instagram feed integration etc) and customized almost 70% of its UI afterwards.",
          tools: "Opencart",
          as: "Under the Umbrella of Dataminds"
        },
        {
          name: "Mehran Foods - Premium Pakistani Foods",
          project: "E-commerce Portal",
          details:
            "E-commerce portal for Delivery of Premium Halal and hygienic food in Korea- Built an e-commerce portal using WordPress/Woocommerce that can carry out all the standard e-commerce features with admin panel and additional plugins (eg. Facebook messenger, Whatsapp Chat, Facebook shop integration, Instagram feed integration etc).",
          tools: "WordPress / WooCommerce",
          as: "Under the Umbrella of Dataminds"
        },
        {
          name: "Small scale ERP",
          project: "Desktop Application",
          details:
            "Built a customized small-scale ERP solution for a chemical company, Rose Enterprises. It manages the sales, purchasing, inventory, accounts and generate invoices and reports.",
          tools: "C# (WinForms), SQL Server",
          as: "As a Freelancer"
        }
      ]
    };
  }
};
</script>

<style>
.site-wrapper {
  background: url("../../public/assets/img/bg.jpg");
  height: 100vh;
  background-repeat: no-repeat;
  background-size: cover;
  position: relative;
}
</style>
