<template>
    <div class="col-sm-6 col-md-4 col-lg-3 my-2">
        <div class="card quote">
            <div class="card-body panel-body">
                <slot></slot>
            </div>
        </div>
    </div>
</template>

<script>
    export default {}
</script>

<style>
.panel-body{
    font-family: 'Arizonia', cursive;
    font-size: 24px;
    color: #6e6e6e;
}
.quote{
    cursor: pointer;
}
.quote:hover{
    background-color: #ffe2e2;
}
</style>