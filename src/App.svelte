<script>
	// import Button from "@smui/button";
	// import LayoutGrid, { Cell } from "@smui/layout-grid";
	// import TopAppBar, { Row, Section, Title } from "@smui/top-app-bar";
	export let name;

	import Line from "svelte-chartjs/src/Line.svelte";
	import { MaterialApp, Button, Alert, AppBar } from "svelte-materialify";
	import BodyContent from "./components/BodyContent.svelte";

	let dataLine = {
		labels: [
			"January",
			"February",
			"March",
			"April",
			"May",
			"June",
			"July",
		],
		datasets: [
			{
				label: "My First dataset",
				fill: true,
				lineTension: 0.3,
				backgroundColor: "rgba(225, 204,230, .3)",
				borderColor: "rgb(205, 130, 158)",
				borderCapStyle: "butt",
				borderDash: [],
				borderDashOffset: 0.0,
				borderJoinStyle: "miter",
				pointBorderColor: "rgb(205, 130,1 58)",
				pointBackgroundColor: "rgb(255, 255, 255)",
				pointBorderWidth: 10,
				pointHoverRadius: 5,
				pointHoverBackgroundColor: "rgb(0, 0, 0)",
				pointHoverBorderColor: "rgba(220, 220, 220,1)",
				pointHoverBorderWidth: 2,
				pointRadius: 1,
				pointHitRadius: 10,
				data: [65, 59, 80, 81, 56, 55, 40],
			},
			{
				label: "My Second dataset",
				fill: true,
				lineTension: 0.3,
				backgroundColor: "rgba(184, 185, 210, .3)",
				borderColor: "rgb(35, 26, 136)",
				borderCapStyle: "butt",
				borderDash: [],
				borderDashOffset: 0.0,
				borderJoinStyle: "miter",
				pointBorderColor: "rgb(35, 26, 136)",
				pointBackgroundColor: "rgb(255, 255, 255)",
				pointBorderWidth: 10,
				pointHoverRadius: 5,
				pointHoverBackgroundColor: "rgb(0, 0, 0)",
				pointHoverBorderColor: "rgba(220, 220, 220, 1)",
				pointHoverBorderWidth: 2,
				pointRadius: 1,
				pointHitRadius: 10,
				data: [28, 48, 40, 19, 86, 27, 90],
			},
		],
	};
</script>

{@debug name}
<MaterialApp theme="light">
	<AppBar>
		Hello {name}! Visit the
	</AppBar>
	<BodyContent>
		<svelte:fragment slot="footer">
			<p>All rights reserved.</p>
			<p>Copyright (c) 2019 Svelte Industries</p>
		</svelte:fragment>
	</BodyContent>
	<Button class="red">hello</Button>
	<Alert class="success-color">
		<a href="https://svelte.dev/tutorial">Svelte tutorial</a>
		to learn how to build Svelte apps.
	</Alert>

	<Line
		data={dataLine}
		options={{
			responsive: true,
			plugins: {
				legend: {
					position: "top",
				},
				title: {
					display: true,
					text: "測試圖表",
				},
			},
		}}
	/>
</MaterialApp>
