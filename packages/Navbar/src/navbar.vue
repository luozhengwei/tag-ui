<template>
    <nav class="navbar navbar-default">
        <div :class="classBuilderContainer">
            <!-- Brand and toggle get grouped for better mobile display -->
            <div class="navbar-header">
                <button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#bs-example-navbar-collapse-1" aria-expanded="false">
                    <span class="sr-only">Toggle navigation</span>
                    <span class="icon-bar"></span>
                    <span class="icon-bar"></span>
                    <span class="icon-bar"></span>
                </button>
                <a class="navbar-brand" href="#" v-text="brand"></a>
            </div>
            <!-- Collect the nav links, forms, and other content for toggling -->
            <div class="collapse navbar-collapse">
                <slot></slot>
            </div>
            <!-- /.navbar-collapse -->
        </div>
        <!-- /.container-fluid -->
    </nav>
</template>
<script>
export default {
    name: 'TagNavbar',
    props: {
        brand: {
            type: String,
            default: 'Brand',
        },
        fluid: {
            type: Boolean,
            default: true,
        },
    },
    computed: {
        classBuilderContainer() {
            var classes = [];
            if (this.fluid) classes.push('container-fluid');
            else classes.push('container');
            return classes;
        }
    }
}
</script>
