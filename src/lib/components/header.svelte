<script>
	import logo from "$lib/assets/logo.svg";
</script>

<header>
	<div>
		<img src={logo} alt="BetterCalapan logo" width="36" height="36" />
		<h1>BetterCalapan</h1>
	</div>
</header>

<style>
	header {
		padding: 1rem;
		display: grid;
		place-items: center;

		div {
			width: 100%;
			max-width: 80rem;
			align-self: center;
			display: grid;
			grid-template-columns: 36px 1fr;
			align-items: center;
			gap: 0.75rem;

			img {
				border-radius: 0.75rem;
			}

			h1 {
				font-size: 1.25rem;
			}
		}
	}
</style>
