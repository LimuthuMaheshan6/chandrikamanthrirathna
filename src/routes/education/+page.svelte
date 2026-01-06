<script lang="ts">
	interface Education {
		degree: string;
		school: string;
		year: string;
		description: string;
		highlights: string[];
	}

	const education: Education[] = [
		{
			degree: 'Bachelor of Science in Nursing (BSN)',
			school: 'University Name',
			year: '2015 - 2019',
			description: 'Comprehensive nursing program covering clinical practice, patient care, healthcare systems, and evidence-based practice.',
			highlights: ['Dean\'s List', 'Clinical Excellence Award', 'Student Leadership']
		},
		{
			degree: 'Associate Degree in Nursing (ADN)',
			school: 'Community College',
			year: '2013 - 2015',
			description: 'Foundation in nursing principles, clinical skills, and patient care fundamentals.',
			highlights: ['Honors Graduate', 'Clinical Rotations']
		},
		{
			degree: 'Associate Degree in Nursing (ADN)',
			school: 'Community College',
			year: '2013 - 2015',
			description: 'Foundation in nursing principles, clinical skills, and patient care fundamentals.',
			highlights: ['Honors Graduate', 'Clinical Rotations']
		}
	];

	const continuingEducation: string[] = [
		'Advanced Cardiac Life Support (ACLS) - Current',
		'Pediatric Advanced Life Support (PALS) - Current',
		'Trauma Nursing Core Course (TNCC)',
		'Emergency Nursing Pediatric Course (ENPC)',
		'Wound Care Certification',
		'IV Therapy Certification'
	];
</script>

<div class="education-page">
	<section class="hero-small section">
		<div class="container">
			<h1 class="page-title">Education & Training</h1>
			<p class="page-subtitle">A commitment to lifelong learning and professional development</p>
		</div>
	</section>

	<section class="section">
		<div class="container">
			<h2 class="section-title">Formal Education</h2>
			<div class="education-timeline">
				{#each education as edu, index}
					<div class="timeline-item">
						<div class="timeline-marker"></div>
						<div class="timeline-content">
							<div class="education-card">
								<div class="education-header">
									<h3 class="degree">{edu.degree}</h3>
									<span class="year">{edu.year}</span>
								</div>
								<p class="school">{edu.school}</p>
								<p class="description">{edu.description}</p>
								<div class="highlights">
									<h4>Achievements:</h4>
									<ul>
										{#each edu.highlights as highlight}
											<li>
												<svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
													<path d="M13.3333 4L6 11.3333L2.66667 8" stroke="#2563eb" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
												</svg>
												{highlight}
											</li>
										{/each}
									</ul>
								</div>
							</div>
						</div>
					</div>
				{/each}
			</div>
		</div>
	</section>

	<section class="section" style="background: var(--bg-secondary);">
		<div class="container">
			<h2 class="section-title">Continuing Education & Certifications</h2>
			<div class="continuing-ed-grid">
				{#each continuingEducation as course}
					<div class="course-card">
						<div class="course-icon">
							<svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
								<path d="M12 2L2 7L12 12L22 7L12 2Z" stroke="#2563eb" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
								<path d="M2 17L12 22L22 17" stroke="#2563eb" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
								<path d="M2 12L12 17L22 12" stroke="#2563eb" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
							</svg>
						</div>
						<span>{course}</span>
					</div>
				{/each}
			</div>
		</div>
	</section>

	<section class="section">
		<div class="container">
			<div class="commitment-box">
				<h2>Commitment to Learning</h2>
				<p>
					I believe in the importance of continuous learning and staying current with the latest 
					developments in healthcare. I regularly participate in professional development opportunities, 
					attend conferences, and pursue additional certifications to enhance my skills and knowledge.
				</p>
			</div>
		</div>
	</section>

	<section class="cta-section section">
		<div class="container">
			<div class="cta-box">
				<h2>Ready to Connect?</h2>
				<p>Let's discuss how my education and experience can benefit your organization.</p>
				<a href="/contact" class="btn btn-primary btn-large">Get In Touch</a>
			</div>
		</div>
	</section>
</div>

<style>
	.education-page {
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

	.section-title {
		font-size: 2.5rem;
		font-weight: 700;
		margin-bottom: 2.5rem;
		color: var(--text-primary);
	}

	.education-timeline {
		position: relative;
		padding-left: 2rem;
	}

	.education-timeline::before {
		content: '';
		position: absolute;
		left: 0;
		top: 0;
		bottom: 0;
		width: 2px;
		background: var(--border-color);
	}

	.timeline-item {
		position: relative;
		margin-bottom: 3rem;
	}

	.timeline-marker {
		position: absolute;
		left: -2.5rem;
		top: 0.5rem;
		width: 16px;
		height: 16px;
		border-radius: 50%;
		background: var(--primary-color);
		border: 3px solid white;
		box-shadow: 0 0 0 3px var(--primary-color);
	}

	.timeline-content {
		margin-left: 0;
	}

	.education-card {
		background: white;
		padding: 2.5rem;
		border-radius: 1rem;
		box-shadow: var(--shadow-md);
	}

	.education-header {
		display: flex;
		justify-content: space-between;
		align-items: flex-start;
		margin-bottom: 0.75rem;
		flex-wrap: wrap;
		gap: 1rem;
	}

	.degree {
		font-size: 1.5rem;
		font-weight: 700;
		color: var(--text-primary);
	}

	.year {
		background: var(--primary-color);
		color: white;
		padding: 0.5rem 1rem;
		border-radius: 0.5rem;
		font-weight: 600;
		font-size: 0.875rem;
	}

	.school {
		font-size: 1.125rem;
		color: var(--primary-color);
		font-weight: 600;
		margin-bottom: 1rem;
	}

	.description {
		color: var(--text-secondary);
		line-height: 1.7;
		margin-bottom: 1.5rem;
	}

	.highlights {
		border-top: 1px solid var(--border-color);
		padding-top: 1.5rem;
	}

	.highlights h4 {
		font-size: 1rem;
		font-weight: 600;
		margin-bottom: 0.75rem;
		color: var(--text-primary);
	}

	.highlights ul {
		list-style: none;
		display: flex;
		flex-direction: column;
		gap: 0.5rem;
	}

	.highlights li {
		display: flex;
		align-items: center;
		gap: 0.5rem;
		color: var(--text-secondary);
	}

	.continuing-ed-grid {
		display: grid;
		grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
		gap: 1.5rem;
	}

	.course-card {
		background: white;
		padding: 1.5rem;
		border-radius: 0.75rem;
		display: flex;
		align-items: center;
		gap: 1rem;
		box-shadow: var(--shadow-sm);
		transition: transform 0.2s ease, box-shadow 0.2s ease;
	}

	.course-card:hover {
		transform: translateY(-3px);
		box-shadow: var(--shadow-md);
	}

	.course-card span {
		font-weight: 500;
		color: var(--text-primary);
	}

	.commitment-box {
		background: white;
		padding: 3rem;
		border-radius: 1rem;
		box-shadow: var(--shadow-md);
		text-align: center;
		max-width: 800px;
		margin: 0 auto;
	}

	.commitment-box h2 {
		font-size: 2rem;
		font-weight: 700;
		margin-bottom: 1.5rem;
		color: var(--text-primary);
	}

	.commitment-box p {
		color: var(--text-secondary);
		line-height: 1.8;
		font-size: 1.125rem;
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

		.education-timeline {
			padding-left: 1.5rem;
		}

		.timeline-marker {
			left: -1.75rem;
		}

		.education-header {
			flex-direction: column;
		}

		.continuing-ed-grid {
			grid-template-columns: 1fr;
		}
	}
</style>

