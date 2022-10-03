<template>
  <div class="row justify-content">
    <div class="col-md-3" v-for="field in fields" :key="field.title">
      <div class="p-2 alert shadow-sm rounded" :class="field.color">
        <h3 class="fw-semi">{{ field.title }}</h3>

        <draggable
          class="list-group kanban-col"
          :list="field.tasks"
          group="tasks"
          ghost-class="ghost-card"
        >
          <app-task-card
            v-for="task in field.tasks"
            :key="task.id"
            :values="task"
            :color="field.color"
          />
        </draggable>
      </div>
    </div>
  </div>
</template>
<script>
import draggable from "vuedraggable";
import AppTaskCard from "./TaskCard.vue";

export default {
  components: {
    draggable,
    AppTaskCard,
  },

  data() {
    return {
      fields: [
        {
          title: "To do",
          color: "alert-warning",
          tasks: [
            {
              id: 0,
              title: "Create app",
              createDate: "Oct 3",
              deadlineDate: "Oct 5",
            },
            {
              id: 1,
              title: "Fix bugs",
              createDate: "Oct 3",
              deadlineDate: "Oct 6",
            },
            {
              id: 2,
              title: "Fix styles",
              createDate: "Sep 28",
              deadlineDate: "Oct 5",
            },
          ],
        },
        {
          title: "In progress",
          color: "alert-primary",
          tasks: [
            {
              id: 3,
              title: "Design shopping cart",
              createDate: "Sep 28",
              deadlineDate: "Oct 3",
            },
            {
              id: 4,
              title: "Fix styles",
              createDate: "Sep 23",
              deadlineDate: "Oct 10",
            },
          ],
        },
        {
          title: "Done",
          color: "alert-success",
          tasks: [
            {
              id: 5,
              title: "Update packages",
              createDate: "Oct 3",
              deadlineDate: "Oct 4",
            },
          ],
        },
      ],
    };
  },
};
</script>
<style scoped lang="scss">
.kanban-col {
  min-height: 320px;
}
.ghost-card {
  opacity: 0.5;
  background: #f7fafc;
  border: 1px solid #4299e1;
}
</style>
