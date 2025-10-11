<script lang="ts">
	export let variant: number = 1;

	import Cloud1 from '$lib/assets/Cloud_1.svg?raw';
	import Cloud2 from '$lib/assets/Cloud_2.svg?raw';
	import Cloud3 from '$lib/assets/Cloud_3.svg?raw';
	import Cloud4 from '$lib/assets/Cloud_4.svg?raw';

	const clouds: Record<number, string> = {
		1: Cloud1,
		2: Cloud2,
		3: Cloud3,
		4: Cloud4
	};

	const svgContent: string = clouds[variant] ?? Cloud1;
</script>

{@html svgContent}
