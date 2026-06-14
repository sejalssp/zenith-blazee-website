<template>
  <!-- ==============================
       PAGE HERO
       ============================== -->
  <section class="page-hero" aria-label="Services">
    <HeroFinanceBg />
    <div class="hero-overlay" aria-hidden="true"></div>
    <div class="container page-hero-content">
      <span class="section-label">Our Services</span>
      <h1 class="page-hero-heading">Mutual Funds &amp; Insurance Advisory</h1>
      <p class="page-hero-sub">
        Two pillars of a complete financial plan — personalised, goal-driven, and built around your life.
      </p>
    </div>
  </section>

  <!-- ==============================
       MUTUAL FUNDS — WHAT WE HELP YOU ACHIEVE
       ============================== -->
  <section class="section section--cream goals-section" id="mutual-funds" aria-labelledby="goals-heading">
    <div class="container">
      <div class="section-intro" data-aos="fade-up">
        <span class="section-label">Mutual Fund Planning</span>
        <h2 class="section-heading" id="goals-heading">
          Your goals are unique.<br />Your plan should be too.
        </h2>
        <p class="section-sub" style="color: var(--color-grey-dark)">
          Whether you're planning for retirement, your child's education, or simply building a financial cushion — we map every goal to the right strategy.
        </p>
      </div>

      <div class="goals-grid">
        <div
          v-for="(goal, i) in goals"
          :key="goal.title"
          class="goal-card"
          data-aos="fade-up"
          :data-aos-delay="i * 70"
        >
          <div class="goal-card-top">
            <div class="goal-icon" aria-hidden="true" v-html="goal.icon"></div>
            <span class="goal-number" aria-hidden="true">0{{ i + 1 }}</span>
          </div>
          <h3 class="goal-title">{{ goal.title }}</h3>
          <p class="goal-desc">{{ goal.desc }}</p>
          <div class="goal-bar" aria-hidden="true"></div>
        </div>
      </div>
    </div>
  </section>

  <!-- ==============================
       HOW IT WORKS
       ============================== -->
  <section class="section section--white steps-section" aria-labelledby="steps-heading">
    <div class="container">
      <div class="section-intro steps-intro" data-aos="fade-up">
        <span class="section-label">How It Works</span>
        <h2 class="section-heading" id="steps-heading">From conversation to confident investing</h2>
        <p class="section-sub" style="color: var(--color-grey-dark)">
          A simple, four-step process designed around you — not paperwork.
        </p>
      </div>

      <div class="steps-grid">
        <div
          v-for="(step, i) in steps"
          :key="step.title"
          class="step-card"
          data-aos="fade-up"
          :data-aos-delay="i * 90"
        >
          <div class="step-top">
            <span class="step-number" aria-hidden="true">0{{ i + 1 }}</span>
            <div class="step-icon" aria-hidden="true" v-html="step.icon"></div>
          </div>
          <h3 class="step-title">{{ step.title }}</h3>
          <p class="step-desc">{{ step.desc }}</p>
          <div class="step-connector" aria-hidden="true" v-if="i < steps.length - 1"></div>
        </div>
      </div>
    </div>
  </section>

  <!-- ==============================
       INSURANCE ADVISORY
       ============================== -->
  <section class="section section--cream insurance-section" id="insurance" aria-labelledby="insurance-heading">
    <div class="container insurance-inner">
      <div class="insurance-content" data-aos="fade-right">
        <span class="section-label">Insurance Advisory</span>
        <h2 class="section-heading" id="insurance-heading">
          Protection First.<br /><span class="gold-text">Always.</span>
        </h2>
        <p class="insurance-sub">
          Alongside mutual fund planning, we help you evaluate the right life and health insurance coverage — because a strong financial plan begins with the right protection in place.
        </p>
      </div>

      <div class="insurance-pillars" data-aos="fade-left" data-aos-delay="100">
        <div v-for="item in insurancePillars" :key="item.title" class="ins-pillar">
          <div class="ins-pillar-icon" aria-hidden="true" v-html="item.icon"></div>
          <div>
            <p class="ins-pillar-title">{{ item.title }}</p>
            <p class="ins-pillar-desc">{{ item.desc }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- ==============================
       CTA STRIP
       ============================== -->
  <section class="cta-strip section--navy" aria-labelledby="cta-heading">
    <div class="cta-strip-bg" aria-hidden="true"></div>
    <div class="cta-strip-top-line" aria-hidden="true"></div>
    <div class="container cta-strip-inner" data-aos="fade-up">
      <span class="section-label" style="display: block; text-align: center; margin-bottom: var(--space-sm)">Take the First Step</span>
      <h2 class="cta-heading" id="cta-heading" style="color: var(--color-cream)">
        Ready to start building<br />your financial future?
      </h2>
      <p class="cta-sub">We respond within 1–2 working days. No pressure, just a conversation.</p>
      <RouterLink to="/contact" class="btn btn--primary">Get in Touch Today</RouterLink>
    </div>
  </section>
</template>

<script setup>
useHead({
  title: 'Our Services — Zenith Blazee',
  meta: [
    {
      name: 'description',
      content:
        'Zenith Blazee offers goal-based mutual fund planning and insurance advisory — personalised financial services for individual investors. ARN-334080.'
    }
  ]
})

const goals = [
  {
    title: 'Financial Freedom',
    desc: 'Build sustainable, long-term wealth that gives you choices — not just savings.',
    icon: `<svg width="26" height="26" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polyline points="23 6 13.5 15.5 8.5 10.5 1 18"/><polyline points="17 6 23 6 23 12"/></svg>`
  },
  {
    title: 'Retirement Planning',
    desc: 'Start early or catch up — we help you build a retirement corpus that lasts.',
    icon: `<svg width="26" height="26" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="10"/><polyline points="12 6 12 12 16 14"/></svg>`
  },
  {
    title: "Children's Future",
    desc: "Education, marriage, or a head start in life — plan today for what matters most tomorrow.",
    icon: `<svg width="26" height="26" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M22 10v6M2 10l10-5 10 5-10 5z"/><path d="M6 12v5c3 3 9 3 12 0v-5"/></svg>`
  },
  {
    title: 'Emergency Fund',
    desc: 'Life is unpredictable. We help you build a liquid buffer so setbacks stay manageable.',
    icon: `<svg width="26" height="26" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/></svg>`
  },
  {
    title: 'Goal-Based Planning',
    desc: "Every goal gets its own strategy — the right fund, timeline, and SIP amount to match.",
    icon: `<svg width="26" height="26" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="10"/><circle cx="12" cy="12" r="6"/><circle cx="12" cy="12" r="2"/></svg>`
  }
]

const steps = [
  {
    title: 'Tell Us Your Goals',
    desc: 'We start with a genuine conversation — understanding your financial situation, priorities, timeline, and concerns.',
    icon: `<svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M21 15a2 2 0 0 1-2 2H7l-4 4V5a2 2 0 0 1 2-2h14a2 2 0 0 1 2 2z"/></svg>`
  },
  {
    title: 'We Map Your Plan',
    desc: 'Together, we build a personalised strategy — the right funds, the right allocation, the right SIP for your goals.',
    icon: `<svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="2" y="3" width="20" height="14" rx="2"/><line x1="8" y1="21" x2="16" y2="21"/><line x1="12" y1="17" x2="12" y2="21"/></svg>`
  },
  {
    title: 'You Start Investing',
    desc: "Once you're comfortable with the plan, we guide you through a smooth, paperless onboarding process.",
    icon: `<svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polyline points="23 6 13.5 15.5 8.5 10.5 1 18"/><polyline points="17 6 23 6 23 12"/></svg>`
  },
  {
    title: 'We Stay With You',
    desc: 'Your plan is reviewed regularly and updated as your life and the markets evolve. We are in it for the long run.',
    icon: `<svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M17 21v-2a4 4 0 0 0-4-4H5a4 4 0 0 0-4 4v2"/><circle cx="9" cy="7" r="4"/><path d="M23 21v-2a4 4 0 0 0-3-3.87"/><path d="M16 3.13a4 4 0 0 1 0 7.75"/></svg>`
  }
]

const insurancePillars = [
  {
    title: 'Life Insurance',
    desc: 'Ensure your family is protected no matter what happens.',
    icon: `<svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M20.84 4.61a5.5 5.5 0 0 0-7.78 0L12 5.67l-1.06-1.06a5.5 5.5 0 0 0-7.78 7.78l1.06 1.06L12 21.23l7.78-7.78 1.06-1.06a5.5 5.5 0 0 0 0-7.78z"/></svg>`
  },
  {
    title: 'Health Insurance',
    desc: 'Protect your savings from unexpected medical expenses.',
    icon: `<svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M22 12h-4l-3 9L9 3l-3 9H2"/></svg>`
  }
]
</script>

<style scoped>
/* ==============================
   PAGE HERO
   ============================== */
.page-hero {
  align-items: center;
  background: linear-gradient(135deg, #0d1b2a 0%, #1b2a4a 50%, #0d1b2a 100%);
  display: flex;
  min-height: 55vh;
  overflow: hidden;
  position: relative;
}

.hero-overlay {
  background:
    radial-gradient(ellipse at 20% 50%, rgba(201, 168, 76, 0.08) 0%, transparent 60%),
    radial-gradient(ellipse at 80% 20%, rgba(201, 168, 76, 0.06) 0%, transparent 50%);
  inset: 0;
  pointer-events: none;
  position: absolute;
}

.page-hero-content {
  padding-bottom: var(--space-xl);
  padding-top: calc(var(--header-height) + var(--space-xl));
  position: relative;
  text-align: center;
  z-index: 2;
}

.page-hero-content .section-label {
  color: var(--color-gold);
  display: block;
  margin-bottom: var(--space-sm);
}

.page-hero-heading {
  color: var(--color-cream);
  font-size: clamp(2rem, 4vw, 3.25rem);
  letter-spacing: -0.025em;
  line-height: 1.15;
  margin-bottom: var(--space-sm);
}

.page-hero-sub {
  color: rgba(250, 248, 245, 0.75);
  font-size: clamp(1rem, 2vw, 1.2rem);
  font-weight: 300;
  line-height: 1.75;
  margin: 0 auto;
  max-width: 560px;
}

/* ==============================
   GOALS
   ============================== */
.section-intro { margin-bottom: var(--space-lg); }

.goals-grid {
  display: grid;
  gap: var(--space-md);
  grid-template-columns: 1fr;
}

.goal-card {
  background-color: var(--color-white);
  border: 1px solid var(--color-grey-light);
  border-radius: var(--radius-md);
  display: flex;
  flex-direction: column;
  gap: 0.625rem;
  overflow: hidden;
  padding: var(--space-md);
  position: relative;
  transition: box-shadow var(--transition-base), transform var(--transition-base);
}

.goal-card:hover {
  box-shadow: var(--shadow-lg);
  transform: translateY(-4px);
}

.goal-card-top {
  align-items: flex-start;
  display: flex;
  justify-content: space-between;
  margin-bottom: 0.25rem;
}

.goal-icon {
  align-items: center;
  background-color: rgba(201, 168, 76, 0.1);
  border-radius: var(--radius-md);
  color: var(--color-gold);
  display: flex;
  height: 52px;
  justify-content: center;
  width: 52px;
}

.goal-number {
  color: rgba(201, 168, 76, 0.25);
  font-family: var(--font-heading);
  font-size: 2rem;
  font-weight: 700;
  line-height: 1;
}

.goal-title {
  color: var(--color-navy-deep);
  font-family: var(--font-heading);
  font-size: var(--fs-h4);
}

.goal-desc {
  color: var(--color-grey-dark);
  font-size: var(--fs-body);
  flex: 1;
  line-height: 1.65;
}

.goal-bar {
  background: linear-gradient(to right, var(--color-gold), var(--color-gold-light));
  bottom: 0;
  height: 3px;
  left: 0;
  position: absolute;
  right: 0;
  transform: scaleX(0);
  transform-origin: left;
  transition: transform 0.38s ease;
}

.goal-card:hover .goal-bar {
  transform: scaleX(1);
}

/* ==============================
   HOW IT WORKS
   ============================== */
.steps-intro { text-align: center; align-items: center; display: flex; flex-direction: column; }

.steps-grid {
  display: grid;
  gap: var(--space-md);
  grid-template-columns: 1fr;
  margin-top: var(--space-lg);
  position: relative;
}

.step-card {
  background-color: var(--color-white);
  border: 1px solid var(--color-grey-light);
  border-radius: var(--radius-md);
  padding: var(--space-lg) var(--space-md);
  position: relative;
  transition: box-shadow var(--transition-base), transform var(--transition-base), border-color var(--transition-base);
}

.step-card:hover {
  border-color: rgba(201, 168, 76, 0.35);
  box-shadow: var(--shadow-md);
  transform: translateY(-3px);
}

.step-top {
  align-items: flex-start;
  display: flex;
  justify-content: space-between;
  margin-bottom: var(--space-sm);
}

.step-number {
  color: rgba(201, 168, 76, 0.2);
  font-family: var(--font-heading);
  font-size: 2.5rem;
  font-weight: 700;
  line-height: 1;
}

.step-icon {
  align-items: center;
  background-color: rgba(201, 168, 76, 0.1);
  border-radius: var(--radius-md);
  color: var(--color-gold);
  display: flex;
  height: 52px;
  justify-content: center;
  width: 52px;
}

.step-title {
  color: var(--color-navy-deep);
  font-family: var(--font-heading);
  font-size: var(--fs-h4);
  margin-bottom: 0.5rem;
}

.step-desc {
  color: var(--color-grey-dark);
  font-size: var(--fs-body);
  line-height: 1.7;
}

.step-connector { display: none; }

/* ==============================
   INSURANCE
   ============================== */
.insurance-inner {
  align-items: start;
  display: grid;
  gap: var(--space-xl);
  grid-template-columns: 1fr;
}

.insurance-sub {
  color: var(--color-grey-dark);
  font-size: var(--fs-body-lg);
  line-height: 1.8;
  margin-top: var(--space-sm);
  max-width: 44ch;
}

.insurance-pillars {
  display: flex;
  flex-direction: column;
  gap: var(--space-md);
}

.ins-pillar {
  align-items: flex-start;
  background-color: var(--color-white);
  border: 1px solid var(--color-grey-light);
  border-radius: var(--radius-md);
  display: flex;
  gap: var(--space-sm);
  padding: var(--space-md);
  transition: box-shadow var(--transition-base), transform var(--transition-base);
}

.ins-pillar:hover {
  box-shadow: var(--shadow-md);
  transform: translateY(-2px);
}

.ins-pillar-icon {
  align-items: center;
  background-color: rgba(201, 168, 76, 0.1);
  border-radius: var(--radius-md);
  color: var(--color-gold);
  display: flex;
  flex-shrink: 0;
  height: 46px;
  justify-content: center;
  width: 46px;
}

.ins-pillar-title {
  color: var(--color-navy-deep);
  font-size: var(--fs-body);
  font-weight: 600;
  margin-bottom: 0.3rem;
}

.ins-pillar-desc {
  color: var(--color-grey-dark);
  font-size: var(--fs-small);
  line-height: 1.6;
}

/* ==============================
   CTA STRIP
   ============================== */
.cta-strip {
  overflow: hidden;
  padding-block: var(--space-2xl);
  position: relative;
  text-align: center;
}

.cta-strip-bg {
  background:
    radial-gradient(ellipse at 0% 100%, rgba(201, 168, 76, 0.12) 0%, transparent 55%),
    radial-gradient(ellipse at 100% 0%, rgba(201, 168, 76, 0.08) 0%, transparent 50%);
  inset: 0;
  pointer-events: none;
  position: absolute;
}

.cta-strip-top-line {
  background: linear-gradient(to right, transparent, var(--color-gold), transparent);
  height: 1px;
  left: 50%;
  position: absolute;
  top: 0;
  transform: translateX(-50%);
  width: 120px;
}

.cta-strip-inner {
  position: relative;
  z-index: 1;
}

.cta-heading {
  font-size: var(--fs-h2);
  margin-bottom: var(--space-sm);
}

.cta-sub {
  color: rgba(250, 248, 245, 0.7);
  font-size: var(--fs-body-lg);
  margin-bottom: var(--space-lg);
}

/* ==============================
   RESPONSIVE
   ============================== */
@media (min-width: 600px) {
  .goals-grid {
    grid-template-columns: 1fr 1fr;
  }
}

@media (min-width: 768px) {
  .insurance-inner {
    grid-template-columns: 1fr 1fr;
  }
}

@media (min-width: 900px) {
  .steps-grid {
    grid-template-columns: repeat(4, 1fr);
    gap: 0;
  }

  .step-card {
    border-radius: 0;
    border-right: none;
  }

  .step-card:first-child { border-radius: var(--radius-md) 0 0 var(--radius-md); }
  .step-card:last-child {
    border-radius: 0 var(--radius-md) var(--radius-md) 0;
    border-right: 1px solid var(--color-grey-light);
  }

  .step-connector {
    background: linear-gradient(to right, var(--color-gold), var(--color-gold-light));
    border-radius: var(--radius-full);
    display: block;
    height: 2px;
    position: absolute;
    right: -1px;
    top: 38px;
    width: 1px;
    z-index: 1;
  }
}

@media (min-width: 1024px) {
  .goals-grid {
    grid-template-columns: repeat(3, 1fr);
  }
}
</style>
