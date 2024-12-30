<template>
  <v-app>
    <v-container>
      <!-- Header -->
        <v-container class="text-center py-4">
            <img src="@/assets/logo.svg" alt="discuss it logo" style="height: 50px;" />
        </v-container>
        <hr />
        
      <!-- Main Content -->
      <v-main>
        <v-container class="py-8">
          <v-card class="mx-auto" max-width="600" elevation="2">
            <v-card-title class="justify-center">
              <h1 class="text-h5 font-weight-bold">Expert Profile</h1>
            </v-card-title>
            <v-divider></v-divider>

            <!-- Stepper -->
            <v-row class="justify-between align-center my-6">
              <template v-for="(step, index) in steps" :key="index">
                <v-col cols="auto">
                  <v-chip
                    :color="currentStep >= step.id ? 'blue' : 'grey lighten-2'"
                    text-color="white"
                    pill
                    class="px-4"
                  >
                    {{ step.id }}
                  </v-chip>
                  <v-tooltip bottom>
                    <template #activator="{ on, attrs }">
                      <span v-bind="attrs" v-on="on" class="ml-2">
                        {{ step.name }}
                      </span>
                    </template>
                  </v-tooltip>
                </v-col>
                <v-col v-if="index < steps.length - 1" cols="auto">
                  <v-divider vertical></v-divider>
                </v-col>
              </template>
            </v-row>

            <!-- Email & OTP Section -->
            <v-card-text>
              <v-row class="justify-center">
                <v-col cols="12" md="6" class="text-center">
                  <v-icon color="blue" size="64">mdi-at</v-icon>
                  <p class="text-center mt-2">
                    Please check your email
                    <br />
                    We've sent a code to
                    <br />
                    <strong>john.doe@gmail.com</strong>
                  </p>
                  <v-row class="justify-center mt-4">
                    <v-col cols="auto" v-for="n in 4" :key="n">
                      <v-text-field
                        v-model="otp[n - 1]"
                        outlined
                        maxlength="1"
                        class="otp-box"
                        type="text"
                        solo
                      ></v-text-field>
                    </v-col>
                  </v-row>
                  <v-btn color="primary" class="mt-4" @click="verifyOtp">
                    Verify
                  </v-btn>
                  <p class="text-sm text-gray-500 mt-2">
                    Didn't get the code? <a href="#" class="text-blue">Resend OTP</a>
                  </p>
                </v-col>
                <v-col cols="12" md="6" class="text-center">
                  <v-icon color="grey" size="64">mdi-check-circle</v-icon>
                  <p>Phone number verified</p>
                </v-col>
              </v-row>
            </v-card-text>

            <v-divider></v-divider>

            <!-- Continue Button -->
            <v-card-actions class="justify-center">
              <v-btn color="primary" block class="py-3" @click="continueToNextStep">
                Continue
              </v-btn>
            </v-card-actions>

            <v-card-subtitle class="text-center text-body-2 mt-4">
              By continuing, you agree to the
              <v-btn text class="text-blue">Terms of use</v-btn>
              and
              <v-btn text class="text-blue">Privacy Policy</v-btn>
              of discuss it
            </v-card-subtitle>
          </v-card>
        </v-container>
      </v-main>

      <!-- Footer -->
      <v-footer color="grey darken-4" padless>
        <v-container class="text-center">
          <v-img
            src="https://placehold.co/150x50?text=discuss+it"
            alt="discuss it logo"
            contain
            width="150"
          ></v-img>
          <p class="text-white">Copyright © 2024 discuss it</p>
        </v-container>
      </v-footer>
    </v-container>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      currentStep: 1,
      steps: [
        { id: 1, name: "Verify Email & Cell Phone" },
        { id: 2, name: "Contact Information" },
        { id: 3, name: "Expertise" },
        { id: 4, name: "Payment Information" },
        { id: 5, name: "Calendar Availability" },
      ],
      otp: ["", "", "", ""],
    };
  },
  methods: {
    verifyOtp() {
      alert(`Entered OTP: ${this.otp.join("")}`);
    },
    continueToNextStep() {
      if (this.currentStep < this.steps.length) {
        this.currentStep++;
      }
    },
  },
};
</script>

<style>
.otp-box {
  text-align: center;
  font-size: 1.5rem;
  width: 3rem;
}
</style>
