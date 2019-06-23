<template>
        <button class="g-button" :class="{[`i-${iconPosition}`]:true}">
                <!-- <svg v-if="icon" class="icon"><use :xlink:href="`#i-${icon}`"></use></svg> -->
                <g-icon :name="icon" v-if="icon" class="icon"></g-icon>
                <div class="content">
                        <slot></slot>        
                </div>
        </button> 
</template>
<script>
export default {
        // props:['icon', 'iconPosition']
        props:{
                icon:{},
                iconPosition: {
                        type: String,
                        default: 'left',
                        validator(value) {  //传值只能二选一
                                // if(value === 'left' || value === 'right') {
                                //         return true
                                // }
                                // return false
                                return (value === 'left' || value === 'right')
                        }
                }
        }
}
</script>
<style lang="scss" scoped>
        .g-button {
            font-size: var(--font-size);
            height: var(--button-height);
            display: inline-flex;
            justify-content: center;
            align-items: center;
            vertical-align: top;
            > .icon {
                    order:1;
            }
            > .content {
                    order:2;
            }
            &.i-right {
                >.icon {
                        order:2;
                }  
                > .content {
                        order:1;
                }  
            }
        }
</style>
