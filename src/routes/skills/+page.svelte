<script lang="ts">
	interface ClinicalSkill {
		name: string;
		level: number;
	}

	const clinicalSkills: ClinicalSkill[] = [
		{name: 'Diabetic Treatment', level: 100},
		{ name: 'Patient Assessment', level: 95 },
		{ name: 'Medication Administration', level: 98 },
		{ name: 'Wound Care', level: 92 },
		{ name: 'IV Therapy', level: 90 },
		{ name: 'Patient Education', level: 94 },
		{ name: 'Emergency Response', level: 96 }
	];

	const softSkills: string[] = [
		'Communication',
		'Empathy',
		'Critical Thinking',
		'Time Management',
		'Team Collaboration',
		'Stress Management',
		'Cultural Competence',
		'Documentation'
	];

	const certifications: string[] = [
		'Registered Nurse (RN)',
		'Basic Life Support (BLS)',
		'Advanced Cardiac Life Support (ACLS)',
		'Pediatric Advanced Life Support (PALS)'
	];
</script>

<div class="skills-page">
	<section class="hero-small section">
		<div class="container">
			<h1 class="page-title">Skills & Expertise</h1>
			<p class="page-subtitle">A comprehensive overview of my clinical competencies and professional capabilities</p>
		</div>
	</section>

	<section class="section">
		<div class="container">
			<h2 class="section-title">Clinical Skills</h2>
			<div class="skills-list">
				{#each clinicalSkills as skill}
					<div class="skill-item">
						<div class="skill-header">
							<span class="skill-name">{skill.name}</span>
							<span class="skill-percentage">{skill.level}%</span>
						</div>
						<div class="skill-bar">
							<div class="skill-progress" style="width: {skill.level}%"></div>
						</div>
					</div>
				{/each}
			</div>
		</div>
	</section>

	<section class="section" style="background: var(--bg-secondary);">
		<div class="container">
			<h2 class="section-title">Soft Skills</h2>
			<div class="soft-skills-grid">
				{#each softSkills as skill}
					<div class="soft-skill-card">
						<svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
							<path d="M9 16.17L4.83 12L3.41 13.41L9 19L21 7L19.59 5.59L9 16.17Z" fill="#10b981"/>
						</svg>
						<span>{skill}</span>
					</div>
				{/each}
			</div>
		</div>
	</section>

	<section class="section">
		<div class="container">
			<h2 class="section-title">Certifications & Licenses</h2>
			<div class="certifications-grid">
				{#each certifications as cert}
					<div class="cert-card">
						<div class="cert-icon">
							<svg width="32" height="32" viewBox="0 0 32 32" fill="none" xmlns="http://www.w3.org/2000/svg">
								<path d="M16 4L20 8H28V26H4V8H12L16 4Z" stroke="#2563eb" stroke-width="2" fill="none"/>
								<path d="M16 18L18 20L22 16" stroke="#2563eb" stroke-width="2" stroke-linecap="round"/>
							</svg>
						</div>
						<h3>{cert}</h3>
					</div>
				{/each}
			</div>
		</div>
	</section>

	<section class="cta-section section">
		<div class="container">
			<div class="cta-box">
				<h2>Interested in Learning More?</h2>
				<p>Let's discuss how my skills can benefit your organization.</p>
				<a href="/contact" class="btn btn-primary btn-large">Get In Touch</a>
			</div>
		</div>
	</section>
</div>

<style>
	.skills-page {
		padding-top: 70px;
	}

	.hero-small {
		background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
		color: white;
		text-align: center;
		padding: 4rem 0;
	}

	.page-title {
		font-size: 3rem;
		font-weight: 800;
		margin-bottom: 1rem;
	}

	.page-subtitle {
		font-size: 1.25rem;
		opacity: 0.95;
	}

	.skills-list {
		display: flex;
		flex-direction: column;
		gap: 2rem;
	}

	.skill-item {
		background: white;
		padding: 1.5rem;
		border-radius: 0.75rem;
		box-shadow: var(--shadow-sm);
	}

	.skill-header {
		display: flex;
		justify-content: space-between;
		align-items: center;
		margin-bottom: 0.75rem;
	}

	.skill-name {
		font-weight: 600;
		font-size: 1.125rem;
		color: var(--text-primary);
	}

	.skill-percentage {
		font-weight: 600;
		color: var(--primary-color);
	}

	.skill-bar {
		height: 10px;
		background: var(--bg-secondary);
		border-radius: 5px;
		overflow: hidden;
	}

	.skill-progress {
		height: 100%;
		background: linear-gradient(90deg, var(--primary-color), var(--secondary-color));
		border-radius: 5px;
		transition: width 0.6s ease;
	}

	.soft-skills-grid {
		display: grid;
		grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
		gap: 1.5rem;
	}

	.soft-skill-card {
		background: white;
		padding: 1.5rem;
		border-radius: 0.75rem;
		display: flex;
		align-items: center;
		gap: 1rem;
		box-shadow: var(--shadow-sm);
		transition: transform 0.2s ease, box-shadow 0.2s ease;
	}

	.soft-skill-card:hover {
		transform: translateY(-3px);
		box-shadow: var(--shadow-md);
	}

	.soft-skill-card span {
		font-weight: 500;
		color: var(--text-primary);
	}

	.certifications-grid {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
		gap: 2rem;
	}

	.cert-card {
		background: white;
		padding: 2rem;
		border-radius: 1rem;
		box-shadow: var(--shadow-md);
		text-align: center;
		transition: transform 0.3s ease, box-shadow 0.3s ease;
	}

	.cert-card:hover {
		transform: translateY(-5px);
		box-shadow: var(--shadow-lg);
	}

	.cert-icon {
		margin-bottom: 1rem;
		display: flex;
		justify-content: center;
	}

	.cert-card h3 {
		font-size: 1.25rem;
		font-weight: 600;
		color: var(--text-primary);
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

	.btn {
		padding: 0.875rem 2rem;
		border-radius: 0.5rem;
		font-weight: 600;
		transition: all 0.3s ease;
		display: inline-block;
		font-size: 1rem;
		background: white;
		color: #667eea;
	}

	.btn:hover {
		transform: translateY(-2px);
		box-shadow: 0 10px 25px rgba(0, 0, 0, 0.2);
	}

	.btn-large {
		padding: 1.125rem 2.5rem;
		font-size: 1.125rem;
	}

	@media (max-width: 768px) {
		.page-title {
			font-size: 2.25rem;
		}

		.soft-skills-grid {
			grid-template-columns: 1fr;
		}

		.certifications-grid {
			grid-template-columns: 1fr;
		}
	}
</style>

