<template>
	<h1>{{foo}}</h1>
</template>

<script>
	import axios from 'axios'
	
	export default {
		 asyncData () {
			var instance = axios.create({
  				baseURL: 'http://127.0.0.1:8023/api',
  				timeout: 1000,
			});
			instance.post('/signup',{
                name: 'wangggongpu',
                password: '12345678',
                email: '1sds@qq.com'
            }).then(function (response) {
				
                console.log(response)
            }).catch(function (error) {
               
				console.log(error)
            })
    		return { foo: 'success' }
  		}
		
	}

</script>