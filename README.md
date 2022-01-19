- 👋 Hi, I’m @lihaoyu-ice
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
export default function getGlowLight() {
  const cl = 25;
  const mat = new THREE.ShaderMaterial({
    uniforms: {
      c: {
        type: "f",
        value: 0.7,
      },
      p: {
        type: "f",
        value: 15,
      },
      glowColor: {
        type: "c",
        value: new THREE.Color(0x1c2462),
      },
      viewVector: {
        type: "v3",
        value: new THREE.Vector3(0, 0, 220),
      },
    },
    vertexShader: `
      #define GLSLIFY 1
      uniform vec3 viewVector;
      uniform float c;
      uniform float p;
      varying float intensity;
      void main()
      {
          vec3 vNormal = normalize( normalMatrix * normal );
          vec3 vNormel = normalize( normalMatrix * viewVector );
          intensity = pow( c - dot(vNormal, vNormel), p );
          gl_Position = projectionMatrix * modelViewMatrix * vec4( position, 1.0 );
      }`,
    fragmentShader: `
      #define GLSLIFY 1
      uniform vec3 glowColor;
      varying float intensity;
      void main()
      {
          vec3 glow = glowColor * intensity;
          gl_FragColor = vec4( glow, 1.0 );
      }`,
    side: 1,
    blending: 2,
    transparent: !0,
  });
  const s = new THREE.Mesh(new THREE.SphereBufferGeometry(cl, 45, 45), mat);
  s.name = "GlowLight";
  s.scale.multiplyScalar(1.15);
  s.rotateX(0.03 * Math.PI);
  s.rotateY(0.03 * Math.PI);
  return s;
}

--->
