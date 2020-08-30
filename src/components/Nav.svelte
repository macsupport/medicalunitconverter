<script>
  export let segment;
  
  import Fa from 'svelte-fa';
import { faFlagUsa, faGlobe, faArrowsAltH, faBalanceScale, faInfoCircle, faPaperPlane, faCalculator, faPencilRuler, faDog, faUserMd, faVial} from '@fortawesome/pro-duotone-svg-icons';
  let current = 'human';
  
</script>



<nav class="w-full">
  <div class="w-full mx-auto rounded-t shadow bg-cover bg-center h-48" style="height:300px;background-image: url(static/bg3.jpg)">
 	<!-- Text shadow utilities will be cool -->
   <div class="container mx-auto px-1">
      <div class="flex items-center justify-between py-1">
        <div class="text-xl flex flex-wrap">
         
        </div>

        

        <div class="sm:flex sm:items-center">
       <ul class="list-reset flex p-4">
        <li><a href="about" class='shadow bg-blue-500 hover:bg-blue-700 text-sm text-white py-2 px-2 rounded inline-flex items-center mr-1 {segment === "about" ? "bg-blue-700" : ""}'><Fa class="inline-flex  text-white pr-1" size="lg" icon={faInfoCircle}/> About</a></li>
        <li><a href="legal" class='shadow bg-blue-500 hover:bg-blue-700 text-sm  text-white py-2 px-2 inline-flex items-center mr-1 rounded {segment === "legal" ? "bg-blue-700" : ""}'><Fa class="inline  text-white pr-1" size="lg" icon={faBalanceScale}/> Legal</a></li>
        <li><a href="mailto:info@vetcalculators.com" class='shadow bg-blue-500 text-sm hover:bg-blue-700  text-white py-2 px-2 inline-flex items-center rounded {segment === "contact" ? "bg-blue-700" : ""}'><Fa class="inline text-white pr-1" size="lg" icon={faPaperPlane}/> Contact</a></li>
        <li><a href="privacy" class='shadow bg-blue-500 hover:bg-blue-700 text-sm text-white py-2 px-2 rounded inline-flex items-center mr-1 {segment === "privacy" ? "bg-blue-700" : ""}'><Fa class="inline-flex  text-white pr-1" size="lg" icon={faInfoCircle}/> Privacy</a></li>
      </ul>
        </div>

        
      </div>
      
    
      </div>
    
    <div class="text-center text-white pb-1">
    <h1 class="font-sans  md:text-2xl textShadow"><Fa class="inline text-gray-600 "  primaryColor="blue" secondaryColor="white"  size="lg" icon={faCalculator}/>  Medical Unit Converter</h1>
      <h2 class="font-sans  text-2xl textShadow"> <Fa class="inline textShadow" size="lg" secondaryColor="red"  icon={faVial}/> US Units  <Fa class="inline text-gray-700" size="lg" icon={faArrowsAltH}/> SI Units <Fa class="inline" size="lg"  secondaryColor="red"  icon={faVial}/></h2>
    <h3 class="tracking-wide mt-2 mb-4 textShadow">Easily Convert Medical and Metric Values</h3>
      
  
    </div>
   
  </div>
  
</nav>
<ul class="flex w-2/3 mx-auto">
  <li class="flex-1 mr-1 ml-1">
    <a class='shadow text-lg text-center block border border-white rounded bg-gray-600 hover:bg-blue-700   py-2 px-1 text-white' class:bg-blue-700="{current === 'human'}"	on:click="{() => current = 'human'}" href="."><Fa class="inline-flex  text-white pr-1" size="2x" icon={faUserMd}/>  Human Units</a>
  </li>
  <li class="flex-1 mr-1">
    <a class='shadow text-lg text-center block border border-white rounded bg-gray-600 hover:bg-blue-700  py-2 px-1  text-white' class:bg-blue-700="{current === 'Veterinary'}"	on:click="{() => current = 'Veterinary'}" href="vet"><Fa class="inline-flex  text-white pr-1" size="2x" icon={faDog}/>  Veterinary Units</a>
  </li>
  <li class="flex-1 mr-1">
    <a class='shadow text-lg text-center block border border-white rounded bg-gray-600 hover:bg-blue-700  py-2 px-1  text-white' class:bg-blue-700="{current === 'Metric Units'}"	on:click="{() => current = 'Metric Units'}" href="metric"><Fa class="inline-flex  text-white pr-1" size="2x" icon={faPencilRuler}/>  Metric Units</a>
  </li>
</ul>



