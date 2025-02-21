<!DOCTYPE html>
<html>
<head>
    <title>Endocrine System Simulator</title>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
    <style>
        body { margin: 0; overflow: hidden; }
        canvas { display: block; }
    </style>
</head>
<body>
    <script>
        // Create a 3D Scene
        const scene = new THREE.Scene();
        const camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000);
        const renderer = new THREE.WebGLRenderer();
        renderer.setSize(window.innerWidth, window.innerHeight);
        document.body.appendChild(renderer.domElement);
        
        // Add a sphere (representing a gland)
        const geometry = new THREE.SphereGeometry(1, 32, 32);
        const material = new THREE.MeshBasicMaterial({ color: 0x00ff00 });
        const gland = new THREE.Mesh(geometry, material);
        scene.add(gland);
        
        camera.position.z = 5;
        
        function animate() {
            requestAnimationFrame(animate);
            gland.rotation.y += 0.01;
            renderer.render(scene, camera);
        }
        
        animate();
    </script>
</body>
</html>
