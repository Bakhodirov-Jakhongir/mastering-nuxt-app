<template>
    <div>
        <div style="display:flex;">
            <img v-for="image in home.images" :key="image" :src="image" alt="image" width="200" height="150"/>
        </div>
        <div>{{home.title}}</div>
        <img src="/images/marker.svg" alt="marker.svg" width="20" height="20"> {{home.location.address}} {{home.location.city}} {{home.location.state}} {{home.location.country}}<br>
        <img src="/images/star.svg" alt="star.svg" width="20" height="20"> {{home.reviewValue}}
    </div>
</template>

<script>
import homes from '~/data/homes';
export default {
    data() {
        return {
            home: {}
        }   
    },
    created() {
        const home = homes.find((home) => home.objectID === this.$route.params._id);
        this.home = home;
    },
}
</script>