<template>
  <div>
    <!-- Footer -->
    <footer class="text-center text-lg-start bg-light text-muted mt-3">
      <!-- Section: Social media -->
      <section
        class="d-flex justify-content-center justify-content-lg-between p-4 border-top"
      >
        <!-- Left -->
        <div class="me-5 d-none d-lg-block">
          <span>Get connected with us on social networks:</span>
        </div>
        <!-- Left -->

        <!-- Right -->
        <div>
          <a
            target="_blank"
            href="https://www.facebook.com/Taman-Dayu-Golf-Club-and-Resort-1010222312373686/"
            class="me-4 text-reset"
          >
            <i class="fab fa-facebook-f"></i>
          </a>
          <a
            target="_blank"
            href="https://twitter.com/tamandayuresort/"
            class="me-4 text-reset"
          >
            <i class="fab fa-twitter"></i>
          </a>

          <a
            target="_blank"
            href="https://www.instagram.com/tamandayugolfresort/"
            class="me-4 text-reset"
          >
            <i class="fab fa-instagram"></i>
          </a>
        </div>
        <!-- Right -->
      </section>
      <!-- Section: Social media -->

      <!-- Section: Links  -->
      <section class="">
        <div class="container text-center text-md-start mt-5">
          <!-- Grid row -->
          <div class="row mt-3">
            <!-- Grid column -->
            <div class="col-md-3 col-lg-4 col-xl-3 mx-auto mb-4">
              <!-- Content -->
              <h6 class="text-uppercase fw-bold mb-4">
                <i class="fas fa-gem me-3"></i> {{ companyName }}
              </h6>
            </div>
            <!-- Grid column -->

            <!-- Grid column -->
            <div class="col-md-2 col-lg-2 col-xl-2 mx-auto mb-4">
              <!-- Links -->
              <h6 class="text-uppercase fw-bold mb-4">The Resorts</h6>
              <p>
                <a href="#!" class="text-reset">Villas</a>
              </p>
              <p>
                <a href="#!" class="text-reset">Bungalows</a>
              </p>
              <p>
                <a href="#!" class="text-reset">Hotel</a>
              </p>
            </div>
            <!-- Grid column -->

            <!-- Grid column -->
            <div class="col-md-3 col-lg-2 col-xl-2 mx-auto mb-4">
              <!-- Links -->
              <h6 class="text-uppercase fw-bold mb-4">Useful links</h6>
              <p>
                <a href="#!" class="text-reset">About Us</a>
              </p>
              <p>
                <a href="#!" class="text-reset">Amenities</a>
              </p>
              <p>
                <a href="#!" class="text-reset">Promotions</a>
              </p>
              <p>
                <a href="#!" class="text-reset">News & Events</a>
              </p>
            </div>
            <!-- Grid column -->

            <!-- Grid column -->
            <div class="col-md-5 col-lg-4 col-xl-4 mx-auto mb-md-0 mb-4">
              <!-- Links -->
              <h6 class="text-uppercase fw-bold mb-4">Contact</h6>
              <p>
                <i class="fas fa-home me-3"></i> Jl. Raya Surabaya-Malang Km.48
                Pandaan 67156 Pasuruan, East Java - Indonesia
              </p>
              <p>
                <i class="fas fa-envelope me-3"></i>
                info@tamandayu.com
              </p>
              <p><i class="fas fa-phone me-3"></i> +62 343 674 1234</p>
              <p><i class="fas fa-phone me-3"></i> +62 811 34 88 234</p>
              <p><i class="fas fa-print me-3"></i> +62 343 674 1280</p>
            </div>
            <!-- Grid column -->
          </div>
          <!-- Grid row -->
        </div>
      </section>
      <!-- Section: Links  -->

      <!-- Copyright -->
      <div
        class="text-center p-4"
        style="background-color: rgba(0, 0, 0, 0.05)"
      >
        © 2023 Copyright: {{ companyName }}
      </div>
      <!-- Copyright -->
    </footer>
    <!-- Footer -->
  </div>
</template>

<script>
export default {
  data() {
    return {
      companyName: 'Taman Dayu Golf Club & Resort',
    }
  },
}
</script>
