<script>
    
    import supabase from '$lib/db';

    async function signOut() {
   	 const { error } = await supabase.auth.signOut();

   	 if (error) alert(error.message); // alert if error
    }

    // Select entries
    async function getEntries() {
   	 const { data, error } = await supabase.from('moodEntries').select();
   	 if (error) alert(error.message);

   	 return data;
    }
</script>




<!-- Sign Out -->
<section class="container px-4 py-3 text-center">
    <button class="btn btn-secondary" on:click={signOut}>Logout</button>
</section>



   
