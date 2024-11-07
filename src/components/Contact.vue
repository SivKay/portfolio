<script setup>
import { ref } from "vue";
import emailjs from "@emailjs/browser";

const form = ref(null);
const isOpenSnackBar = ref(false);
const snackBar = ref({
  color: "",
  text: "",
});
const name = ref("");
const nameRules = ref([(value) => !!value || "Please enter a name."]);

const email = ref("");
const emailRules = ref([
  (value) => {
    if (!value) return "Please enter an email.";

    if (!/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(value)) {
      return "Please enter a valid email.";
    }
    return true;
  },
]);

const subject = ref("");
const subjectRules = ref([(value) => !!value || "Please enter a subject."]);

const message = ref("");
const messageRules = ref([(value) => !!value || "Please enter a message."]);

async function onSubmit(event) {
  const value = await form.value.validate();

  if (value.valid) {
    const templateParams = {
      message: message.value,
      from_name: name.value,
      email: email.value,
      subject: subject.value,
    };

    emailjs
      .send(
        import.meta.env.VITE_EMAIL_SERVICE_ID,
        import.meta.env.VITE_EMAIL_TEMPLATE_ID,
        templateParams,
        {
          publicKey: import.meta.env.VITE_EMAIL_PUBLIC_ID,
        }
      )
      .then(
        (response) => {
          isOpenSnackBar.value = true;
          snackBar.value = {
            color: "success",
            text: "Email is sent successfully!",
          };
        },
        (err) => {
          isOpenSnackBar.value = true;
          snackBar.value = {
            color: "success",
            text: "Failed to send email!",
          };
        }
      );
  }
}
</script>

<template>
  <section id="contact">
    <div class="header position-relative text-center mb-8">
      <h1 class="title-shadow">Contact</h1>
      <h2>Contact</h2>
    </div>

    <div class="content-container">
      <div class="d-flex flex-column ga-8">
        <div class="contact-item">
          <div class="icon d-flex align-center justify-center">
            <v-icon
              color="var(--vt-c-yellow)"
              icon="mdi-map-marker"
              size="x-large"
            ></v-icon>
          </div>
          <div>
            <h3>Address</h3>
            <p>198 West 21th Street, Suite 721 New York NY 10016</p>
          </div>
        </div>
        <div class="contact-item">
          <div class="icon d-flex align-center justify-center">
            <v-icon
              color="var(--vt-c-yellow)"
              icon="mdi-phone"
              size="x-large"
            ></v-icon>
          </div>
          <div>
            <h3>Contact Number</h3>
            <a href="tel:+85595356363">+85595356363</a>
          </div>
        </div>
        <div class="contact-item">
          <div class="icon d-flex align-center justify-center">
            <v-icon
              color="var(--vt-c-yellow)"
              icon="mdi-email"
              size="x-large"
            ></v-icon>
          </div>
          <div>
            <h3>Email Address</h3>
            <a href="mailto:11jsivkay@gmail.com">11jsivkay@gmail.com</a>
          </div>
        </div>
      </div>
      <div>
        <v-sheet class="w-full pa-6 pa-md-16" color="#f8f9fa">
          <v-form ref="form" @submit.prevent="onSubmit">
            <v-text-field
              v-model="name"
              :rules="nameRules"
              label="Your Name"
            ></v-text-field>
            <v-text-field
              v-model="email"
              :rules="emailRules"
              label="Your Email"
            ></v-text-field>
            <v-text-field
              v-model="subject"
              :rules="subjectRules"
              label="Subject"
            ></v-text-field>
            <v-textarea
              v-model="message"
              :rules="messageRules"
              label="Message"
              no-resize
            ></v-textarea>
            <v-btn
              class="mt-4"
              color="var(--vt-c-yellow)"
              rounded="xl"
              type="submit"
              size="x-large"
              >Send Message</v-btn
            >
          </v-form>
        </v-sheet>
      </div>
    </div>
  </section>

  <v-snackbar
    v-model="isOpenSnackBar"
    :color="snackBar.color"
    location="top right"
  >
    {{ snackBar.text }}
  </v-snackbar>
</template>

<style scoped>
section {
  padding-top: 7rem;
}

.header h2 {
  font-size: 3.125rem;
  font-weight: 700;
  margin-bottom: 1.5rem;
}

.content-container {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 1rem;
}

.contact-item {
  display: flex;
  align-items: center;
  gap: 3rem;
}

.contact-item h3 {
  text-transform: uppercase;
  margin-bottom: 1.5rem;
}

.contact-item a {
  color: var(--vt-c-white);
  text-decoration: none;
}

.icon {
  width: 100px;
  min-width: 100px;
  height: 100px;
  min-height: 100px;
  background: rgba(255, 255, 255, 0.1);
  border-radius: 50%;
}

.title-shadow {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  font-size: min(7vw, 6rem);
  color: rgba(255, 255, 255, 0.1);
  z-index: -1;
  font-weight: 900;
}

@media (max-width: 768px) {
  .content-container {
    grid-template-columns: auto;
    gap: 2rem;
  }

  .contact-item {
    gap: 1rem;
  }
}
</style>
