<!DOCTYPE html>

<html>
	<head>
		<title>Кристални нашественици</title>
		<meta charset="utf-8">
		
		<meta name="viewport" content="width=device-width, user-scalable=no, minimum-scale=1.0, maximum-scale=1.0">
		
		<script src="three.min.js"></script>
		<script src="WebGL.js"></script>
		<script src="vax.js"></script>
	</head>
	
	<body>
		<script>
			vaxInit();
			
			camera.fov = 30;
			onWindowResize();

			scene.background = new THREE.CubeTextureLoader().load( [
				'Buddha/posx.jpg', 'Buddha/negx.jpg',
				'Buddha/posy.jpg', 'Buddha/negy.jpg',
				'Buddha/posz.jpg', 'Buddha/negz.jpg' ] );
				

			var geometry = new THREE.SphereBufferGeometry( 20, 16,16 ),
				material = new THREE.MeshPhongMaterial( ),
				sphere = new THREE.Mesh( geometry, material );
				
				material.envMap = scene.background;
				material.reflectivity = 1;
			scene.add( sphere );
			
			
			function animate()
			{
				controls.update();
			}
			
		</script>
		
	</body>
</html>


