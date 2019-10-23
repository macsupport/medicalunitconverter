<script>
	export let segment;
</script>




<nav class="w-full px-1">
  <div class="container mx-auto rounded-t shadow bg-cover bg-center m-2" style="background-image: url(https://www.vetcalculators.com/img/emergencyBW.jpg)">
 	<!-- Text shadow utilities will be cool -->
    <div class="flex justify-between p-4 items-center mb-10">
      <a href="#" class=" text-black  text-sm md:text-4xl">Medical Unit Converter</a>
      <ul class="list-reset flex">
	   <li><a href="." class='bg-gray-700 hover:bg-blue-700  text-white font-bold py-2 px-4 rounded-l {segment === "home" ? "bg-blue-700" : ""}'>Home</a></li>
        <li><a href="about" class='bg-gray-700 hover:bg-blue-700  text-white font-bold py-2 px-4  {segment === "about" ? "bg-blue-700" : ""}'>About</a></li>
        <li><a href="legal" class='bg-gray-700 hover:bg-blue-700  text-white font-bold py-2 px-4  {segment === "legal" ? "bg-blue-700" : ""}'>Legal</a></li>
        <li><a href="contact" class='bg-gray-700 hover:bg-blue-700  text-white font-bold py-2 px-4 rounded-r {segment === "contact" ? "bg-blue-700" : ""}'>Contact</a></li>
      </ul>
    </div>
    
    <div class="text-center text-black md:text-3xl pb-10">
      <h1 class="font-sans"> US Units  SI Units Conversion</h1>
    
      <h2 class=" text-sm tracking-wide mt-2 mb-4">Common Lab Values</h2>
  
    </div>
   
  </div>
  
</nav>