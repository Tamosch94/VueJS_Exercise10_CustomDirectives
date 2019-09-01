<template>
    <div class="container">
        <div class="row">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <h1 v-custom-on:click="myTestFunction">Directives Exercise</h1>
                <!-- Exercise -->
                <!-- Build a Custom Directive which works like v-on (Listen for Events) -->

            </div>
        </div>
    </div>
</template>

<script>
    export default {
		directives: {
			'custom-on': {
				bind(el, binding, vnode) {
					if (binding.arg == 'click') {
						console.log('test');
						el.addEventListener('click', function(event) {
							binding.value();
						});

					}
				}

			}
		},
		methods: {
			myTestFunction() {
				alert('You clicked on your custom directive!')
			}
		}
	}
</script>

<style>
</style>
