<div style="display:flex;width:100%;align-items:center;justify-content: space-around;">
<a class="course" href="#assets/course-1">
  <img src="assets/qiskit.svg" />
  <div style="width:100%;text-align:center;">Course 1</div>
</a>
<a class="course" href="#assets/course-2">
  <img src="assets/qiskit.svg" />
  <img src="assets/qiskit.svg" />
  <div style="width:100%;text-align:center;">Course 2</div>
</a>
</div>

<style>
img{
  height: 100px;
  width: 100px;
}
.course {
  display: block;
  background-color: transparent;
  border: 1px solid var(--theme-color);
  border-radius: 10px;
  padding: 10px;
  margin: 10px;

  width: 250px;
  aspect-ratio: 1.2;

  cursor: pointer;
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  justify-content: center;
  transition: all 0.1s ease-in-out;
}

.course:hover{
  background-color: var(--theme-color);
  color: white;
}
</style>