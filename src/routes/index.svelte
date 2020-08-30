<svelte:head>
  <title>medicalunitconverter.com</title>
  <meta name="description" content="Medical unit conversion calculator, medicalunitconverter.com. Convert US units to International (SI) units easily with this onlne calculator. Easily search for a specific lab test, enter any value and convert the units. For both Human and Veterinary values.">
  

<!-- Global site tag (gtag.js) - Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=UA-255701-18"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'UA-255701-18');
</script>
</svelte:head>




<script>
  import { fade, fly } from 'svelte/transition';
  import Fa from 'svelte-fa';
import { faFlagUsa, faGlobe, faArrowsAltH, faVial, faCalculator } from '@fortawesome/pro-duotone-svg-icons';

 //import j$ from 'jquery';
//import { onMount } from 'svelte';

//onMount(() => {
//    j$('.test').click(() => {
//        console.log('test');
 //   });
//});

import units from "../components/unitsH.js";



let name = '';

 
  

 	let prefix = '';
	let i = 0;
  let current = 'human';
  
  function setBothFromSI(value, i) {
    const {factor, siValue} = units[i];
    units[i].siValue = +value;
    units[i].usValue = +(value / factor).toFixed(2);
  }
  function setBothFromUS(value, i) {
    const {factor, usValue} = units[i];
    units[i].usValue = +value;
    units[i].siValue = +(value * factor).toFixed(2);;
  }

	$: filteredUnits = prefix
		? units.filter(unit => {
			const names = `${unit.name}`;
			return names.toLowerCase().startsWith(prefix.toLowerCase());
      
		})
		: units;
$: selected = filteredUnits[i];

</script>









  <div class="container mx-auto  px-1">

  


 <div class="md:w-1/4 mb-3 sm:w-1/3 text-black p-1">Search Units <input placeholder="Units" class="mt-1 block w-full  text-gray-700 border border-gray-300 rounded-lg py-2 px-2 leading-tight bg-white  focus:outline-none focus:bg-white focus:border-gray-500" type="search" bind:value={prefix}></div>


  {#each filteredUnits as unit, i}
 <div class="border border-gray-300 rounded mb-2">


 <div class="flex flex-wrap md:flex-no-wrap lg:flex-no-wrap px-1  mb-1">
 <div class="w-full md:w-2/5" >
            
              <div class="font-bold text-black ">{unit.name}</div>
             <div class="text-gray-700 text-md"><Fa class="inline"  secondaryColor="red"  icon={faVial}/>  Specimen: {unit.specimen} </div>
         <div class="text-gray-700 text-sm"><Fa class="inline"  icon={faCalculator}/>  Conversion Factor: {unit.factor} </div>
            
  </div>
  <div class="md:w-1/3 w-1/2   h-14 pr-1 pl-1">
  <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-1" for="grid-first-name">
       <Fa class="inline" size="lg" primaryColor="blue" secondaryColor="red" icon={faFlagUsa}/> US
      </label>
               <input class="appearance-none mt-1 block w-full bg-blue-100 text-gray-700 border border-blue-200 rounded py-2 px-2 leading-tight focus:outline-none focus:bg-white focus:border-gray-500" value={unit.usValue} on:input="{e => setBothFromUS(e.target.value, i)}"  type=number placeholder=" US">
<div class="text-gray-700 text-sm">US Range:{unit.conventionalRange} {unit.conventionalUnit}</div>
             </div>

 <div class="md:w-1/3 w-1/2   h-14 pr-1 pl-1">
 <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-1" for="grid-first-name">
        <Fa class="inline" size="lg" primaryColor="green" secondaryColor="lightblue" icon={faGlobe}/> International
      </label>
               <input class="appearance-none mt-1 block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-2 px-2 leading-tight focus:outline-none focus:bg-white focus:border-gray-500" value={unit.siValue} on:input="{e => setBothFromSI(e.target.value, i)}" type=number placeholder="SI">
<div class="text-gray-700 text-sm">SI Range: {unit.siRange} {unit.siUnit} </div>
             </div>

 
 
 
 </div> 
</div>
{/each}
  
   
   
   

    

  
   </div>
<footer class='w-full text-center border-t border-grey p-4 pin-b'>
            www.medicalunitconverter.com
        </footer>