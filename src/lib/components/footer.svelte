<script lang="ts">
	import Facebook from "$lib/icons/facebook.svelte";
	import GitHub from "$lib/icons/github.svelte";

	const apps = [
		{
			name: "Portal",
			url: "https://bettercalapan.org"
		},
		{
			name: "Roadmap",
			url: "https://roadmap.bettercalapan.org"
		}
	];
	const bettergov = [
		{
			name: "Transparency Portal",
			url: "https://transparency.bettergov.ph"
		},
		{
			name: "Open Data Portal",
			url: "https://data.bettergov.ph"
		},
		{
			name: "Budget Tracker",
			url: "https://budget.bettergov.ph"
		},
		{
			name: "SALN Tracker",
			url: "https://saln.bettergov.ph"
		},
		{
			name: "Juris",
			url: "https://juris.ph"
		}
	];
</script>

<footer>
	<div class="wrapper">
		<div class="info">
			<h1>BetterCalapan</h1>
			<p class="description">
				An open-source initiative providing transparent access to municipal services, local
				legislation, and public data for the people of Calapan.
			</p>
			<div class="socials">
				<a
					class="social"
					href="https://facebook.com/bettercalapan.org"
					target="_blank"
					rel="external noopener noreferrer"
					aria-label="Go to Facebook page"
				>
					<Facebook />
				</a>
				<a
					class="social"
					href="https://github.com/BetterCalapan/bettercalapan"
					target="_blank"
					rel="external noopener noreferrer"
					aria-label="Go to GitHub repository"
				>
					<GitHub />
				</a>
			</div>
		</div>
		<div class="footer-sections">
			<div class="footer-section">
				<h1>Apps</h1>
				<ul class="footer-section-list">
					{#each apps as app (app.name)}
						<li class="app">
							<a href={app.url} target="_blank" rel="external noopener noreferrer" class="link"
								>{app.name}</a
							>
						</li>
					{/each}
				</ul>
			</div>
			<div class="footer-section">
				<h1>BetterGov</h1>
				<ul class="footer-section-list">
					{#each bettergov as proj (proj.name)}
						<li class="bettergov-proj">
							<a href={proj.url} target="_blank" rel="external noopener noreferrer" class="link"
								>{proj.name}</a
							>
						</li>
					{/each}
				</ul>
			</div>
		</div>
	</div>
</footer>

<style>
	h1 {
		font-size: 1.125rem;
		color: var(--bg);
		font-weight: 500;
	}
	footer {
		padding: 4rem 1rem;
		display: grid;
		place-items: center;
		gap: 3rem;
		background: var(--fg);
		color: var(--neutral-dark);

		.wrapper {
			width: 100%;
			max-width: 80rem;
			display: flex;
			flex-direction: column;
			gap: 2rem;

			.info {
				display: flex;
				flex-direction: column;
				gap: 1rem;

				.description {
					max-width: 28rem;
				}
				.socials {
					margin-top: 1rem;
					display: flex;
					flex: 1;
					gap: 1rem;

					.social {
						width: 20px;
						height: 20px;
						align-self: end;
						color: var(--neutral-dark);
					}
				}
			}
			.footer-sections {
				margin-top: 1.75rem;
				display: flex;
				flex-direction: column;
				gap: 2rem;

				.footer-section {
					display: flex;
					flex-direction: column;
					gap: 1rem;
					color: var(--fg);

					.footer-section-list {
						display: flex;
						flex-direction: column;
						gap: 0.5rem;

						li {
							.link {
								color: var(--neutral-dark);
								text-decoration: none;

								&:hover {
									text-decoration: underline;
								}
							}
						}
					}
				}
			}
		}
	}

	@media (min-width: 600px) {
		footer {
			.wrapper {
				.footer-sections {
					display: grid;
					grid-template-columns: repeat(2, 12rem);
				}
			}
		}
	}

	@media (min-width: 1100px) {
		footer {
			.wrapper {
				display: grid;
				grid-template-columns: 1fr 24rem;
				gap: 20rem;

				.footer-sections {
					margin: 0;
					display: grid;
					grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
				}
			}
		}
	}
</style>
