<script lang="ts">
	import { onMount } from 'svelte';
	
	let mounted = false;
	onMount(() => {
		mounted = true;
	});
</script>

<div class="home">
	<section class="hero">
		<div class="container">
			<div class="hero-content" class:fade-in={mounted}>
				<h1 class="hero-title">
					Compassionate Care,<br />
					<span class="highlight">Professional Excellence</span>
				</h1>
				<p class="hero-subtitle">
					Dedicated registered nurse with a passion for patient care and a commitment to making a positive impact in healthcare.
				</p>
				<div class="hero-cta">
					<a href="/contact" class="btn btn-primary">Get In Touch</a>
					<a href="/projects" class="btn btn-secondary">View My Work</a>
				</div>
			</div>
		</div>
	</section>

	<section class="about section">
		<div class="container">
			<div class="about-grid">
				<div class="about-content">
					<h2 class="section-title">About Me</h2>
					<p class="section-text">
						With years of experience in healthcare, I bring a unique combination of clinical expertise, 
						compassion, and dedication to every patient interaction. My approach to nursing is centered 
						on providing holistic, patient-centered care that addresses both physical and emotional needs.
					</p>
					<p class="section-text">
						I am committed to continuous learning and staying current with the latest evidence-based 
						practices in nursing. My goal is to make a meaningful difference in the lives of patients 
						and their families while contributing to the advancement of healthcare.
					</p>
					<a href="/skills" class="btn btn-outline">Learn More About My Skills</a>
				</div>
				<div class="about-image">
					<div class="image-placeholder">
						<img src="src/public/nanda.webp" width="100%"   alt="nurse-pic">
					</div>
				</div>
			</div>
		</div>
	</section>

	<section class="features section" style="background: var(--bg-secondary);">
		<div class="container">
			<h2 class="section-title text-center">Why Choose Me</h2>
			<div class="features-grid">
				<div class="feature-card">
					<div class="feature-icon">
						<svg width="40" height="40" viewBox="0 0 40 40" fill="none" xmlns="http://www.w3.org/2000/svg">
							<path d="M20 5L25 15H35L27 22L30 32L20 26L10 32L13 22L5 15H15L20 5Z" fill="#2563eb"/>
						</svg>
					</div>
					<h3>Expert Care</h3>
					<p>Years of experience in diverse healthcare settings with a focus on patient safety and quality outcomes.</p>
				</div>
				<div class="feature-card">
					<div class="feature-icon">
						<svg width="40" height="40" viewBox="0 0 40 40" fill="none" xmlns="http://www.w3.org/2000/svg">
							<path d="M20 8C13.3726 8 8 13.3726 8 20C8 26.6274 13.3726 32 20 32C26.6274 32 32 26.6274 32 20C32 13.3726 26.6274 8 20 8ZM20 28C15.5817 28 12 24.4183 12 20C12 15.5817 15.5817 12 20 12C24.4183 12 28 15.5817 28 20C28 24.4183 24.4183 28 20 28Z" fill="#10b981"/>
							<path d="M20 14V20L24 22" stroke="#10b981" stroke-width="2" stroke-linecap="round"/>
						</svg>
					</div>
					<h3>Always Available</h3>
					<p>Committed to being responsive and available when you need professional nursing expertise.</p>
				</div>
				<div class="feature-card">
					<div class="feature-icon">
						<svg width="40" height="40" viewBox="0 0 40 40" fill="none" xmlns="http://www.w3.org/2000/svg">
							<path d="M20 10C14.4772 10 10 14.4772 10 20C10 25.5228 14.4772 30 20 30C25.5228 30 30 25.5228 30 20C30 14.4772 25.5228 10 20 10ZM18 24L14 20L15.41 18.59L18 21.17L24.59 14.58L26 16L18 24Z" fill="#2563eb"/>
						</svg>
					</div>
					<h3>Certified Professional</h3>
					<p>Maintaining current certifications and staying updated with the latest healthcare practices and protocols.</p>
				</div>
			</div>
		</div>
	</section>

	<section class="cta-section section">
		<div class="container">
			<div class="cta-box">
				<h2>Ready to Work Together?</h2>
				<p>Let's discuss how I can contribute to your healthcare team or project.</p>
				<a href="/contact" class="btn btn-primary btn-large">Contact Me Today</a>
			</div>
		</div>
	</section>
</div>

<style>
	.home {
		padding-top: 70px;
	}

	.hero {
		background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
		color: white;
		padding: 6rem 0;
		min-height: 80vh;
		display: flex;
		align-items: center;
	}

	.hero-content {
		max-width: 800px;
		opacity: 0;
		transform: translateY(20px);
		transition: opacity 0.6s ease, transform 0.6s ease;
	}

	.hero-content.fade-in {
		opacity: 1;
		transform: translateY(0);
	}

	.hero-title {
		font-size: 3.5rem;
		font-weight: 800;
		line-height: 1.2;
		margin-bottom: 1.5rem;
	}

	.highlight {
		color: #fbbf24;
	}

	.hero-subtitle {
		font-size: 1.25rem;
		margin-bottom: 2.5rem;
		opacity: 0.95;
		line-height: 1.7;
	}

	.hero-cta {
		display: flex;
		gap: 1rem;
		flex-wrap: wrap;
	}

	.btn {
		padding: 0.875rem 2rem;
		border-radius: 0.5rem;
		font-weight: 600;
		transition: all 0.3s ease;
		display: inline-block;
		font-size: 1rem;
	}

	.btn-primary {
		background: white;
		color: #667eea;
	}

	.btn-primary:hover {
		transform: translateY(-2px);
		box-shadow: 0 10px 25px rgba(0, 0, 0, 0.2);
	}

	.btn-secondary {
		background: transparent;
		color: white;
		border: 2px solid white;
	}

	.btn-secondary:hover {
		background: white;
		color: #667eea;
	}

	.btn-outline {
		border: 2px solid var(--primary-color);
		color: var(--primary-color);
	}

	.btn-outline:hover {
		background: var(--primary-color);
		color: white;
	}

	.btn-large {
		padding: 1.125rem 2.5rem;
		font-size: 1.125rem;
	}

	.about-grid {
		display: grid;
		grid-template-columns: 1fr 1fr;
		gap: 4rem;
		align-items: center;
	}

	.section-title {
		font-size: 2.5rem;
		font-weight: 700;
		margin-bottom: 1.5rem;
		color: var(--text-primary);
	}

	.section-text {
		font-size: 1.125rem;
		color: var(--text-secondary);
		margin-bottom: 1.5rem;
		line-height: 1.8;
	}

	.text-center {
		text-align: center;
	}

	.about-image {
		display: flex;
		justify-content: center;
		align-items: center;
	}

	.image-placeholder {
		width: 100%;
		max-width: 400px;
		aspect-ratio: 1;
		background: var(--bg-secondary);
		border-radius: 1rem;
		display: flex;
		align-items: center;
		justify-content: center;
	}

	.features-grid {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
		gap: 2.5rem;
		margin-top: 3rem;
	}

	.feature-card {
		background: white;
		padding: 2.5rem;
		border-radius: 1rem;
		box-shadow: var(--shadow-md);
		transition: transform 0.3s ease, box-shadow 0.3s ease;
	}

	.feature-card:hover {
		transform: translateY(-5px);
		box-shadow: var(--shadow-lg);
	}

	.feature-icon {
		margin-bottom: 1.5rem;
	}

	.feature-card h3 {
		font-size: 1.5rem;
		font-weight: 600;
		margin-bottom: 1rem;
		color: var(--text-primary);
	}

	.feature-card p {
		color: var(--text-secondary);
		line-height: 1.7;
	}

	.cta-section {
		background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
		color: white;
	}

	.cta-box {
		text-align: center;
		max-width: 700px;
		margin: 0 auto;
	}

	.cta-box h2 {
		font-size: 2.5rem;
		font-weight: 700;
		margin-bottom: 1rem;
	}

	.cta-box p {
		font-size: 1.25rem;
		margin-bottom: 2rem;
		opacity: 0.95;
	}

	@media (max-width: 768px) {
		.hero {
			padding: 4rem 0;
			min-height: 70vh;
		}

		.hero-title {
			font-size: 2.5rem;
		}

		.hero-subtitle {
			font-size: 1.125rem;
		}

		.about-grid {
			grid-template-columns: 1fr;
			gap: 2rem;
		}

		.section-title {
			font-size: 2rem;
		}

		.features-grid {
			grid-template-columns: 1fr;
		}

		.cta-box h2 {
			font-size: 2rem;
		}
	}
</style>

