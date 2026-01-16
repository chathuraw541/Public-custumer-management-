<template>
  <q-page class="bg-dark text-white">
    <!-- Hero Section -->
    <div
      class="row items-center justify-center window-height"
      style="background: linear-gradient(135deg, #000000 0%, #1a1a1a 100%)"
    >
      <div class="col-11 col-md-10 text-center q-pa-md">
        <q-badge
          color="secondary"
          label="Scale Your Business"
          class="q-mb-md text-bold q-px-sm q-py-xs"
        />
        <h1 class="text-h2 text-weight-bolder q-mt-none q-mb-md">
          Deepen Customer <br />
          <span class="text-secondary">Relationships</span>
        </h1>
        <p
          class="text-h5 text-grey-5 q-mb-xl"
          style="max-width: 700px; margin-left: auto; margin-right: auto"
        >
          The all-in-one CRM platform designed to help you manage leads, close deals, and support
          customers efficiently.
        </p>
        <div class="row justify-center q-gutter-md">
          <q-btn
            size="lg"
            color="secondary"
            label="Get Started"
            no-caps
            class="q-px-xl rounded-borders"
          />
          <q-btn
            size="lg"
            outline
            color="white"
            label="Live Demo"
            no-caps
            class="q-px-xl rounded-borders"
          />
        </div>
      </div>
    </div>

    <!-- Stats Section -->
    <div class="bg-white text-black q-py-lg">
      <div class="row justify-evenly text-center container-width q-mx-auto">
        <div class="col-12 col-sm-3 q-py-md">
          <div class="text-h3 text-weight-bold text-secondary">10k+</div>
          <div class="text-subtitle1 text-weight-medium">Happy Customers</div>
        </div>
        <div class="col-12 col-sm-3 q-py-md">
          <div class="text-h3 text-weight-bold text-secondary">300%</div>
          <div class="text-subtitle1 text-weight-medium">ROI Increase</div>
        </div>
        <div class="col-12 col-sm-3 q-py-md">
          <div class="text-h3 text-weight-bold text-secondary">24/7</div>
          <div class="text-subtitle1 text-weight-medium">Support Available</div>
        </div>
      </div>
    </div>

    <!-- Features Section -->
    <div class="q-py-xl container-width q-mx-auto">
      <div class="text-center q-mb-xl">
        <h2 class="text-h3 text-weight-bold q-mb-sm">Why Choose CRM Pro?</h2>
        <div class="text-h6 text-grey-5">Everything you need to grow your business</div>
      </div>

      <div class="row q-col-gutter-lg">
        <div v-for="(feature, index) in features" :key="index" class="col-12 col-md-4">
          <q-card class="bg-grey-10 text-white full-height feature-card" flat bordered>
            <q-card-section class="q-pa-lg text-center">
              <q-avatar
                color="secondary"
                text-color="white"
                size="60px"
                class="q-mb-md"
                :icon="feature.icon"
              />
              <div class="text-h5 text-weight-bold q-mb-sm">{{ feature.title }}</div>
              <div class="text-grey-5">{{ feature.description }}</div>
            </q-card-section>
          </q-card>
        </div>
      </div>
    </div>

    <!-- Detailed Value Section -->
    <div class="bg-grey-10 q-py-xl">
      <div class="container-width q-mx-auto row items-center q-col-gutter-xl">
        <div class="col-12 col-md-6">
          <h3 class="text-h3 text-weight-bold q-mb-md">
            Streamline Your <span class="text-secondary">Workflow</span>
          </h3>
          <p class="text-h6 text-grey-5 q-mb-lg">
            Forget about spreadsheets and manual data entry. Our automated tools assist you in
            managing every interaction seamlessly from a single dashboard.
          </p>
          <q-list dark padding>
            <q-item v-for="benefit in benefits" :key="benefit" class="q-pl-none">
              <q-item-section avatar>
                <q-icon name="check_circle" color="secondary" />
              </q-item-section>
              <q-item-section class="text-h6">{{ benefit }}</q-item-section>
            </q-item>
          </q-list>
        </div>
        <div class="col-12 col-md-6 text-center">
          <!-- Placeholder for an image or graphic -->
          <q-icon name="query_stats" size="200px" color="grey-8" />
        </div>
      </div>
    </div>

    <!-- Call to Action -->
    <div class="bg-secondary text-white q-py-xl text-center">
      <div class="q-pa-md">
        <h2 class="text-h3 text-weight-bold q-mt-none q-mb-md">
          Ready to Transform Your Business?
        </h2>
        <p class="text-h5 q-mb-xl opacity-80">Join thousands of businesses that trust CRM Pro.</p>
        <q-btn
          color="white"
          text-color="secondary"
          size="lg"
          label="Start Your Free Trial"
          class="text-weight-bold q-px-xl rounded-borders"
        />
      </div>
    </div>
  </q-page>
</template>

<script setup>
const features = [
  {
    title: 'Contact Management',
    description:
      'Store and organize all your customer details in one secure place. never lose track of a lead again.',
    icon: 'contacts',
  },
  {
    title: 'Sales Pipeline',
    description:
      'Visualize your sales process with drag-and-drop boards. Close deals faster with automated follow-ups.',
    icon: 'waterfall_chart',
  },
  {
    title: 'Analytics & Reports',
    description:
      'Get deep insights into your team performance and sales trends with customizable dashboards.',
    icon: 'analytics',
  },
]

const benefits = [
  'Automated Lead Scoring',
  'Email Integration & Tracking',
  'Mobile App Access',
  'Customizable Dashboards',
]
</script>

<style scoped>
.container-width {
  max-width: 1200px;
  width: 100%;
}
.feature-card {
  transition:
    transform 0.3s,
    border-color 0.3s;
  border: 1px solid rgba(255, 255, 255, 0.1);
}
.feature-card:hover {
  transform: translateY(-5px);
  border-color: var(--q-secondary);
}
</style>
