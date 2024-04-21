<script>
	let name = 'yo yo';
	let lastName='honey singh'
	let color = 'Brown';
	let products = [
	{
		name: 'Iphone',
		price: '$1000',
		id : 1
	},
	{
		name: 'Samsung',
		price: '$500',
		id : 2
	},
	{
		name: 'Oneplus',
		price: '$800'
	}
];


	// $ element which is used to display the dynamic events just like useState in React

	$:fullname = `${name} ${lastName}`;

	const handlebtn = () =>{
		if(color=='white'){
			color = 'Balck';
		}
		else{
			color='white';
		}
	};

	// const handleinput =(e)=>{
	// 	color = e.target.value;
	// }

	const handledelete = (id) =>{
		products = products.filter((i)=>i.id!=id);
	}
</script>

<main>
	<h1> {fullname}</h1>
	{#each products as i}
	<div>
		<p>
		<h1>{i.name}</h1>
		<p>{i.price}</p>
		<button on:click= {() => handledelete(i.id)} >Delete</button>
		</div>
	{/each}
	
	<h1 >Skin colour</h1>
	<h1 style="color: {color};">{color}</h1>
<button on:click =  {handlebtn}>
		Update color
	</button>
	<!-- <input type="text" on:change={handleinput} value={color}> -->
	<!-- similarly -->

	<input type="text" bind:value={name}>
	<input type="text" bind:value={lastName}>
	<input type="text" bind:value={color}>
</main>

<style>
	h1{
		color:red;
	}
	button{
		padding:10px;
		background-color:blue;
		font-weight:bold;
		color:black;		
	}
	.white{
		color:burlywood;
	}
	.black{
		color:black;
	}
</style>

