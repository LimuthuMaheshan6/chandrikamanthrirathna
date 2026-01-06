<script lang="ts">
	interface Project {
		title: string;
		description: string;
		technologies: string[];
		results: string[];
	}

	const projects: Project[] = [
		{
			title: 'Patient Care Initiative',
			description: 'Led a comprehensive patient care program that improved patient satisfaction scores by 40% and reduced readmission rates.',
			technologies: ['Patient Care', 'Quality Improvement', 'Team Leadership'],
			results: ['40% increase in satisfaction', 'Reduced readmissions', 'Improved outcomes']
		},
		{
			title: 'Healthcare Education Program',
			description: 'Developed and implemented an educational program for patients with chronic conditions, resulting in better self-management and adherence.',
			technologies: ['Patient Education', 'Program Development', 'Health Promotion'],
			results: ['Improved adherence rates', 'Better patient outcomes', 'Enhanced self-care']
		},
		{
			title: 'Clinical Documentation System',
			description: 'Collaborated on improving clinical documentation processes, leading to more accurate records and better continuity of care.',
			technologies: ['Documentation', 'Process Improvement', 'Quality Assurance'],
			results: ['Improved accuracy', 'Better continuity', 'Enhanced efficiency']
		},
		{
			title: 'Community Health Outreach',
			description: 'Organized and participated in community health screenings and educational events, reaching over 500 community members.',
			technologies: ['Community Health', 'Public Health', 'Health Promotion'],
			results: ['500+ participants', 'Increased awareness', 'Community engagement']
		}
	];
</script>

<div class="projects-page">
	<section class="hero-small section">
		<div class="container">
			<h1 class="page-title">Projects & Achievements</h1>
			<p class="page-subtitle">Highlighting key projects and initiatives that demonstrate my commitment to excellence in healthcare</p>
		</div>
	</section>

	<section class="section">
		<div class="container">
			<div class="projects-grid">
				{#each projects as project}
					<div class="project-card">
						<div class="project-header">
							<h2 class="project-title">{project.title}</h2>
						</div>
						<p class="project-description">{project.description}</p>
						<div class="project-technologies">
							{#each project.technologies as tech}
								<span class="tech-tag">{tech}</span>
							{/each}
						</div>
						<div class="project-results">
							<h4>Key Results:</h4>
							<ul>
								{#each project.results as result}
									<li>
										<svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
											<path d="M13.3333 4L6 11.3333L2.66667 8" stroke="#10b981" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
										</svg>
										{result}
									</li>
								{/each}
							</ul>
						</div>
					</div>
				{/each}
			</div>
		</div>
	</section>

	<section class="cta-section section">
		<div class="container">
			<div class="cta-box">
				<h2>Have a Project in Mind?</h2>
				<p>I'm always interested in new opportunities to make a positive impact in healthcare.</p>
				<a href="/contact" class="btn btn-primary btn-large">Let's Collaborate</a>
			</div>
		</div>
	</section>
</div>

<style>
	.projects-page {
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

	.projects-grid {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
		gap: 2.5rem;
	}

	.project-card {
		background: white;
		padding: 2.5rem;
		border-radius: 1rem;
		box-shadow: var(--shadow-md);
		transition: transform 0.3s ease, box-shadow 0.3s ease;
		display: flex;
		flex-direction: column;
	}

	.project-card:hover {
		transform: translateY(-5px);
		box-shadow: var(--shadow-lg);
	}

	.project-title {
		font-size: 1.75rem;
		font-weight: 700;
		margin-bottom: 1rem;
		color: var(--text-primary);
	}

	.project-description {
		color: var(--text-secondary);
		line-height: 1.7;
		margin-bottom: 1.5rem;
		flex-grow: 1;
	}

	.project-technologies {
		display: flex;
		flex-wrap: wrap;
		gap: 0.75rem;
		margin-bottom: 1.5rem;
	}

	.tech-tag {
		background: var(--bg-secondary);
		color: var(--primary-color);
		padding: 0.5rem 1rem;
		border-radius: 0.5rem;
		font-size: 0.875rem;
		font-weight: 500;
	}

	.project-results {
		border-top: 1px solid var(--border-color);
		padding-top: 1.5rem;
	}

	.project-results h4 {
		font-size: 1rem;
		font-weight: 600;
		margin-bottom: 0.75rem;
		color: var(--text-primary);
	}

	.project-results ul {
		list-style: none;
		display: flex;
		flex-direction: column;
		gap: 0.5rem;
	}

	.project-results li {
		display: flex;
		align-items: center;
		gap: 0.5rem;
		color: var(--text-secondary);
		font-size: 0.9375rem;
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

		.projects-grid {
			grid-template-columns: 1fr;
		}
	}
</style>

