<template>
    <section id='foot_guide'>
        <section @click = "gotoAddress({path: '/lhome', query: {geohash}})" class="guide_item">
            <img v-if="selectedItem!=='home'" src="../../images/party.png" class="icon_style">  
            <img v-else src="../../images/partySelected.png" class="icon_style"> 
            <span v-if="selectedItem!=='home'" :style="{color: '#707070'}">党旗飘飘</span>
            <span v-else :style="{color: '#1296db'}">党旗飘飘</span>
        </section>
        <section @click = "gotoAddress({path: '/study'})" class="guide_item">
            <img v-if="selectedItem!=='search'" src="../../images/study.png" class="icon_style">  
            <img v-else src="../../images/studySelected.png" class="icon_style"> 
            <span v-if="selectedItem!=='search'" :style="{color: '#707070'}">学习中心</span>
            <span v-else :style="{color: '#1296db'}">学习中心</span>
        </section>
        <section @click = "gotoAddress({path: '/exam'})" class="guide_item">
            <img v-if="selectedItem!=='tenement'" src="../../images/exam.png" class="icon_style">  
            <img v-else src="../../images/examSelected.png" class="icon_style"> 
            <span v-if="selectedItem!=='tenement'" :style="{color: '#707070'}">考试中心</span>
            <span v-else :style="{color: '#1296db'}">考试中心</span>
        </section>
        <section @click = "gotoAddress({path: '/lprofile'})" class="guide_item">
            <img v-if="selectedItem!=='profile'" src="../../images/self.png" class="icon_style">  
            <img v-else src="../../images/selfSelected.png" class="icon_style"> 
            <span v-if="selectedItem!=='profile'" :style="{color: '#707070'}">我的</span>
            <span v-else :style="{color: '#1296db'}">我的</span>
        </section>
    </section>
</template>

<script>
    import {mapState} from 'vuex'
    export default {
    	data(){
            return{
            }
        },
        created(){
           
        },
        mounted(){
            
        },
        computed: {
            ...mapState([
                'geohash'
            ]),
        },
        	props: ['selectedItem'],
        methods: {
        	gotoAddress(path){
        		this.$router.push(path)
        	}
        },

    }

</script>

<style lang="scss" scoped>
    @import '../../style/mixin';

    #foot_guide{
        background-color: #fff;
        position: fixed;
        z-index: 100;
        left: 0;
        right: 0;
        bottom: 0;
        @include wh(100%, 1.95rem);
        display: flex;
        box-shadow: 0 -0.026667rem 0.053333rem rgba(0,0,0,.1);
    }
    .guide_item{
    	flex: 1;
    	display: flex;
    	text-align: center;
    	flex-direction: column;
    	align-items: center;
		.icon_style{
			@include wh(.9rem, .9rem);
			margin-top: .3rem;
			fill: #ccc;
		}
		span{
            margin-top: 0.1rem;
			@include sc(.45rem, #666);
		}
    }
   
</style>
