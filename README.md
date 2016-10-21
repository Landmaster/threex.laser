threex.laser
============
Small three.js extension for creating lasers

How To Use It
=============

## threex.laserbeam.js
It is a raw laser beam using dynamic textures.
To create the laser beam and add it to the scene:

```javascript
var laserBeam = new THREEx.LaserBeam(color);
scene.add(laserBeam);
```

## threex.lasercooked.js
It is a laser beam with dynamic collision. 
On impacts, to increase realism, there is sprite and point light.
It depends on ```THREEx.LaserBeam``` so first create it and add it to the scene

```javascript
var laserBeam = new THREEx.LaserBeam();
scene.add(laserBeam);
```

Then you create the laserCooked based on it. Don't forget to update it in your render loop.

```javascript
var laserCooked	= new THREEx.LaserCooked(laserBeam,texture,scene);
onRenderFcts.push(function(delta, now){
	// every time you render the scene, update laserCooked
	laserCooked.update(delta, now)
})
```
