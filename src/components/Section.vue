<template>
    <section :id="data.title.replace(' ','')">

        <div class="details">
            <div class="details-heading">
                <p class="title">{{data.title}}</p>
                <figure><img src="../assets/images/icon-ellipsis.svg" alt="ellipsis" class="ellipsis"></figure>
            </div>
            <p class="current">{{data.timeframes[period].current}}hrs</p>
            <p class="previous">{{(this.period === "daily")? "Yesterday" : (this.period === "weekly")? "Last Week" : "Last Month"}} - {{data.timeframes[period].previous}}hrs</p>
        </div>
        
    </section>
</template>

<script>
export default {
    props:["data","period"]
}
</script>
