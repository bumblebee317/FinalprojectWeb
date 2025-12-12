<template>
    <div>
<div v-if="item.published" class="TBox">
<p>
 Item ID: {{ item.id }}   
</p>
<p>
Title: {{ item.title }}
</p>
<p>
Status: {{ item.published }}
</p>
</div>
<div v-else class="FBox">
<p>
Item ID: {{ item.id }}   
</p>
<p>
Title: {{ item.title }}
</p>
<p>
Status: {{ item.published }}
</p>
</div>
</div>
</template>

<script>
    export default{
        props:["item"]
    }
</script>