<template>
    <div class="root-home">
        <div class="btn-container">
            <UIButton @click="onClick" 
                :xlarge="xlarge"
                :large="large"
                :xsmall="xsmall"
                :small="small"
                :tile="tile"
                :rounded="rounded"
                :circle="circle"
                :disabled="disabled">按钮</UIButton>
        </div>
        <div class="btn-group">
            <UIButton class="btn" @click="resize('xsmall')">超小</UIButton>
            <UIButton class="btn" @click="resize('small')">小</UIButton>
            <UIButton class="btn" @click="resize('normal')">正常</UIButton>
            <UIButton class="btn" @click="resize('large')">大</UIButton>
            <UIButton class="btn" @click="resize('xlarge')">超大</UIButton>
        </div>
        <div class="btn-group">
            <UIButton class="btn" @click="changeRadius('tile')">矩形</UIButton>
            <UIButton class="btn" @click="changeRadius('normal')">正常</UIButton>
            <UIButton class="btn" @click="changeRadius('rounded')">半圆</UIButton>
            <UIButton class="btn" @click="changeRadius('circle')">圆</UIButton>
        </div>
        <div class="btn-group">
            <UIButton class="btn" @click="changeDisabled">禁用</UIButton>
        </div>
    </div>
</template>


<script lang="ts">

import { Component, Vue } from 'vue-property-decorator';
import UIButton from '@/components/myUI/UIButton.vue';

// declare module 'vue/types/vue' {
//     interface Vue {
//         [key: string]: any,
//     }
// }

@Component({
    components: {
        UIButton
    }
})
export default class Home extends Vue {
    
    private xsmall = false;
    private small = false;
    private xlarge = false;
    private large = false;
    private tile = false;
    private rounded = false;
    private circle = false;
    private disabled = false;

    private changeDisabled() {
        this.disabled = !this.disabled;
    }

    private changeRadius(name: string) {
        switch (name) {
            case 'tile':
                this.tile = true;
                this.rounded = false;
                this.circle = false;
                break;
            case 'normal':
                this.tile = false;
                this.rounded = false;
                this.circle = false;
                break;
            case 'rounded':
                this.tile = false;
                this.rounded = true;
                this.circle = false;
                break;
            case 'circle':
                this.tile = false;
                this.rounded = false;
                this.circle = true;
                break;
            default:
                break;
        }
    }
    private onClick(event: MouseEvent) {
        console.log(event)
    }

    private resize(name: string) {
        switch (name) {
            case 'xsmall':
                this.xsmall = true;
                this.small = false;
                this.xlarge = false;
                this.large = false;
                break;
            case 'small':
                this.xsmall = false;
                this.small = true;
                this.xlarge = false;
                this.large = false;
                break;
            case 'normal':
                this.xsmall = false;
                this.small = false;
                this.xlarge = false;
                this.large = false;
                break;
            case 'large':
                this.xsmall = false;
                this.small = false;
                this.xlarge = false;
                this.large = true;
                break;
            case 'xlarge':
                this.xsmall = false;
                this.small = false;
                this.xlarge = true;
                this.large = false;
                break;
            default:
                break;

        }
    }


}
</script>


<style lang="stylus" scoped>
.btn-container
    width 480px
    height 160px
    // background-color red
    display flex
    justify-content center
    align-items center

.btn 
    margin 6px
</style>