< html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>LITLEVELS 3D Clothing</title>

  <!-- CSS styles -->
  <style>
    body {
      margin: 0;
      overflow: hidden;
    }

    #3d-container {
      position: absolute;
      top: 0;
      left: 0;
    }
  </style>
</head>
<body>

  <!-- Three.js library -->
  <script src="https://threejs.org/build/three.js"></script>

  <!-- HTML content -->
  <div id="3d-container"></div>

  <!-- JavaScript code -->
  <script>
    // Set up the scene
    var scene = new THREE.Scene();
    var camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000);
    var renderer = new THREE.WebGLRenderer();
    renderer.setSize(window.innerWidth, window.innerHeight);
    document.getElementById('3d-container').appendChild(renderer.domElement);

    // Create a simple cube as a placeholder for the clothing model
    var geometry = new THREE.BoxGeometry();
    var material = new THREE.MeshBasicMaterial({ color: 0x00ff00 });
    var cube = new THREE.Mesh(geometry, material);
    scene.add(cube);

    // Position the camera
    camera.position.z = 5;

    // Animation loop
    var animate = function () {
      requestAnimationFrame(animate);

      // Rotate the cube
      cube.rotation.x += 0.01;
      cube.rotation.y += 0.01;

      renderer.render(scene, camera);
    };

    animate();
  </script>

</body>
</html>
