<script>
import { ref, toRef } from "vue";

export default {
  setup(props, { slots }) {
    const flag = ref(true);

    const handleClick = () => {
      flag.value = !flag.value;
    };

    return () =>
      slots.default({
        flag: flag.value,
        handleClick,
      });
  },
};
</script>