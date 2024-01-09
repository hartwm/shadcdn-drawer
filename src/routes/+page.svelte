
<script lang="ts"> 
	import { open } from '$lib/stores';
  import { Button } from '$lib/components/ui/button';
  import * as Drawer from '$lib/components/ui/drawer'; 
  import * as Dialog from '$lib/components/ui/dialog';
</script>


<div class="h-screen bg-white">
  <h1 class="text-3xl">Drawer Issues</h1>
  <div class="prose mx-auto"> <pre> {JSON.stringify($open, null, 2)}</pre></div>
  <Button on:click={()=>{$open = true}}>Open</Button>
 
  <Drawer.Root open={$open}>
    <!-- <Drawer.Trigger>Open</Drawer.Trigger> -->
    <Drawer.Content>
      <div class="mx-auto w-full max-w-xl">
        <Drawer.Header>
          <Drawer.Title>Title</Drawer.Title>
          <Drawer.Description>
            Describe
          </Drawer.Description>
        </Drawer.Header>
        <div>
          lorem
        </div>
        <Drawer.Footer> 
          <Drawer.Close asChild let:builder>
            <Button builders={[builder]} variant="link" size="sm">Cancel</Button>
          </Drawer.Close>
        </Drawer.Footer>
      </div>
    </Drawer.Content>
  </Drawer.Root>
  



</div>
<div class="h-screen bg-black"></div>
<div class="h-screen bg-white"></div>
<div class="h-screen bg-black"></div>