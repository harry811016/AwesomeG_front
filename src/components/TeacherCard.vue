<template>
  <div class="row overflow-auto" style="height: 600px" v-viewer>
    <div
      v-for="teacher in fiteredTeachers"
      :key="teacher.id"
      class="col-md-6 col-lg-4"
    >
      <div
        class="card mb-3 text-center align-items-center"
        style="background-color: #fffbf0"
      >
        <img
          v-if="teacher.avatar"
          class="rounded-circle mt-3"
          :src="teacher.avatar"
          alt="Card image cap"
          width="100px"
          height="100px"
          style="cursor: zoom-in"
        />
        <img
          v-else
          class="rounded-circle mt-3"
          src="https://images.pexels.com/photos/771742/pexels-photo-771742.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=750&w=1260"
          alt="Card image cap"
          width="100px"
          height="100px"
        />
        <div class="card-body">
          <h5 class="card-text title-wrap" style="color: black">
            {{ teacher.name }}
          </h5>
          <span
            class="badge badge-pill m-1"
            :class="{
              'badge-info': teacher.expertise === 'Math',
              'badge-success': teacher.expertise === 'Physical',
              'badge-secondary': teacher.expertise === 'Chemical',
            }"
            style="cursor: default"
            >{{ teacher.expertise }}</span
          >
        </div>
        <div class="card-footer w-75" style="background-color: #fffbf0">
          <!-- <button type="button" class="btn btn-danger like mr-2">Unlike</button>
          <button type="button" class="btn btn-primary like mr-2">Like</button>-->
          <span
            class="badge badge-info"
            style="cursor: default; background-color: #c03546"
          >
            <h5>Solved: {{ teacher.AnswersCount }}</h5>
          </span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    fiteredTeachers: {
      type: Array,
      required: true,
    },
  },
};
</script>