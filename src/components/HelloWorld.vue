<template>
  <div>
    <renderer :size="{ w: 600, h: 400 }">
      <scene>
        <orbit-controls
          :position="{
            x: 9,
            y: 26,
            z: 20,
          }"
          :rotation="{ x: 2, y: 0, z: 3 }"
        >
          <camera :position="{ z: 15 }"></camera>
        </orbit-controls>
        <light
          :hex="0xffffff"
          :intensity="2"
          :position="{ x: 0, y: 200, z: 0 }"
        ></light>
        <light
          :hex="0xff0000"
          :intensity="2"
          :position="{ x: -50, y: -50, z: -50 }"
        ></light>
        <light
          :hex="0xefefff"
          :intensity="2"
          :position="{ x: 50, y: 50, z: 50 }"
        ></light>
        <mesh name="Cube">
          <geometry type="Box" :args="[boxLength, boxLength, boxLength]" />
          <material type="MeshLambert" :color="0x4424ff"></material>
        </mesh>
      </scene>
    </renderer>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  data: () => ({
    boxLength: 10,
  }),
  mounted() {
    console.log(this.global);
  },
};
</script>

<style scoped>
</style>
