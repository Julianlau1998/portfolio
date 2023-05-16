<template>
  <div class="section primary is-flex is-flex-direction-column is-justify-content-center is-align-items-center">
    <div class="columns">
      <div class="column">
        <h1 class="header is-size-1 mb-5">
          Contact
        </h1>
      </div>
    </div>
    <div class="columns">
      <div class="column">
        <p>
          Thank You for visiting!<br>
          In case You have any questions, feel free to contact me via the following Email-Address or use the form below <br>
          <a href= "mailto:jlauapps@gmail.com">jlauapps@gmail.com</a>
        </p>
        <hr class="mt-6">
      </div>
    </div>
    <div class="columns is-contact-form">
      <form action="https://formsubmit.co/jlauapps@gmail.com" method="POST">
        <input type="hidden" name="_captcha" value="false">
        <input type="hidden" name="_next" value="https://jlapps.netlify.app/">
        <input
            type="email"
            name="email"
            id="mail-adress"
            class="hidden contact"
            placeholder="Your Email-adress"
            required
        >
        <br>
        <textarea
            placeholder="Your message"
            name="Email Text"
            class="hidden contact"
            id="mail"
            cols="30"
            rows="10"
            required
        ></textarea>
        <br>
        <button type="submit" id="submit" class="button is-primary mt-negative-2">
          Submit
        </button>
      </form>
    </div>
  </div>
</template>

<script>

export default {
  name: "contact_component",
}
</script>
