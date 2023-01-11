<script>
    import * as THREE from "three";
    import * as SC from "svelte-cubed";

</script>

<SC.Canvas background={new THREE.Color('#007ced')}>

    <!-- LIGHTS -->
    <SC.AmbientLight
            color={new THREE.Color('white')}
            intensity={.5}
    />
    <SC.DirectionalLight
            color={new THREE.Color('white')}
            intensity={.75}
            position={[10, 10, 10]}
    />

    <!-- MESHES -->
    <SC.Mesh
            geometry={new THREE.OctahedronGeometry()}
            material={new THREE.MeshStandardMaterial({
      color: new THREE.Color('#E7F26E')
    })}
    />

    <!-- CAMERA -->
    <SC.PerspectiveCamera near={1} far={100} fov={30} />
    <SC.OrbitControls
            enabled
            enablePan
            enableZoom
            enableRotate
            enableDamping
    />

</SC.Canvas>