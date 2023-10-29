# Names

## Nextme's Name Service

> Nextme will launch a domain name service at a certain point in time when the mainnet goes live, paving the way and building infrastructure services for the Portal and the Relation Protocol.

<img class='rounded-lg' src='https://cdn.nextme.one/user/37327eb3-b8b8-48d6-91a7-68fd85e1bd25/1679635345790.png' />

!> The following are some of the brand or celebrity logos we reserved during the public beta, which are still being updated dynamically before the mainnet contract is deployed. Illegal pre-registration is not recommended during the test to avoid related legal disputes.

> If some handles are recycled or preempted, please submit this form or contact our official staff, we will verify your official information and protect it in time. https://forms.gle/nYFHkqSTuMsp1Dgh7

<div class='flex justify-center items-center py-4'>
  <span class="relative flex h-5 w-5">
    <span class="animate-ping absolute inline-flex h-full w-full rounded-full bg-green-400 opacity-75"></span>
    <span class="relative inline-flex rounded-full h-5 w-5 bg-green-400"></span>
  </span>
  <span class='pl-4'>Dynamic Update in Progress</span>
</div>

<ul>
  <li 
    v-for="(row,index) in ecosystem.names" 
    :key="`names-${index}`"
    class='leading-8'
  >{{row?.path}}
  </li>
</ul>
