## n3d-threejs

This packages the [Three.js](https://github.com/mrdoob/three.js) library as a [node.js module](http://nodejs.org/api/modules.html).

### Installation

``` js
npm install n3d-threejs
```

OR

``` js
cd <app-folder>/node_modules
git clone git@github.com:joates/n3d-threejs.git
```

### Example

``` js
var THREE = require('n3d-threejs')

var width = window.innerWidth
var height = window.innerHeight
var scene, camera, renderer, cube

function init(){
  scene = new THREE.Scene()
  camera = new THREE.PerspectiveCamera(45, width/height, 0.1, 10000)

  renderer = new THREE.WebGLRenderer()
  renderer.setSize(window.width, height)
  document.body.appendChild(renderer.domElement)

  var geometry = new THREE.BoxGeometry(1, 1, 1)
  var material = new THREE.MeshBasicMaterial({color: 0x00ff00})
  cube = new THREE.Mesh(geometry, material)
  scene.add(cube)

  camera.position.z = 5
}

function animate(){
  requestAnimationFrame(animate)
  update()
  render()
}

function update(){
  cube.rotation.x += 0.1
  cube.rotation.y += 0.1
}

function render(){
  renderer.render(scene, camera)
}

init()
animate()
```


## License

The MIT License

Copyright &copy; 2010-2014 three.js authors

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
