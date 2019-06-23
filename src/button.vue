<template>
        <button class="g-button" :class="{[`i-${iconPosition}`]:true}">
                <svg v-if="icon" class="icon"><use :xlink:href="`#i-${icon}`"></use></svg>
                <div class="content">
                        <slot></slot>        
                </div>
        </button> 
</template>
<script>
export default {
        props:['icon', 'iconPosition']
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
