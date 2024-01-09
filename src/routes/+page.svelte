
<script lang="ts">   
	import { openDrawer, openDialog } from '$lib/stores';
  import { Button } from '$lib/components/ui/button';
  import * as Drawer from '$lib/components/ui/drawer'; 
  import * as Dialog from '$lib/components/ui/dialog';
</script>


<div class="h-screen bg-white">
  <div class="prose mx-auto"> 
    <h1 class="text-3xl">Drawer Issues</h1>
    <h2>Drawer via store</h2>
    <p>Issues: doesn't close on clickoutside; doesn't have fixed background</p>
    <pre> $openDrawer: {JSON.stringify($openDrawer, null, 2)}</pre>
    <Button on:click={()=>{$openDrawer = true}}>Open</Button>
  
    <Drawer.Root open={$openDrawer} onOutsideClick={()=>$openDrawer=false}> 
      <Drawer.Content>
        <div class="mx-auto w-full max-w-xl">
          <Drawer.Header>
            <Drawer.Title>Title</Drawer.Title>
            <Drawer.Description>
              Describe
            </Drawer.Description>
          </Drawer.Header>
          <div>
            Lorem ipsum dolor sit, amet consectetur adipisicing elit. Accusamus, quas culpa earum quibusdam iure, dolorum velit tempora tempore beatae sapiente eum rerum. Tenetur, recusandae animi! Est alias quas quod veritatis!
          </div>
          <Drawer.Footer> 
            <Drawer.Close asChild let:builder>
              <Button builders={[builder]} variant="link" size="sm">Cancel</Button>
            </Drawer.Close>
          </Drawer.Footer>
        </div>
      </Drawer.Content>
    </Drawer.Root> 

    <h2>Dialog via store</h2>
    <p></p>
    <pre> $openDialog: {JSON.stringify($openDialog, null, 2)}</pre>
    <Button on:click={()=>{$openDialog = true}}>Open</Button>
  
    <Dialog.Root open={$openDialog}> 
      <Dialog.Content>
        <Dialog.Header>
          <Dialog.Title>Are you sure absolutely sure?</Dialog.Title>
          <Dialog.Description>
            This action cannot be undone. This will permanently delete your account
            and remove your data from our servers.
          </Dialog.Description>
        </Dialog.Header>
      </Dialog.Content>
    </Dialog.Root>
  </div>
</div>
<div class="h-screen bg-black"></div>
<div class="h-screen bg-white"></div>
<div class="h-screen bg-black"></div>