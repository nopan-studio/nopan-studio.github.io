

<script lang="ts">
    let { title, description, link,image} = $props();


</script>


<div class=" border-0 border-b-1 border-gray-300 p-5"> 
    <h2 class="text-3xl font-bold text-gray-900 oswald mb-4">
          {title}
    </h2>
    <p class="text-gray-700 mb-4">
        {description}
    </p>
    <a href="{link}" class="text-orange-600 hover:underline inconsolata">View Project</a>
</div>