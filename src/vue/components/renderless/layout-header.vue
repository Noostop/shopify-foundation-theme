<script>
import {Menu, MenuButton, MenuItems, MenuItem} from '@headlessui/vue';

import {ref, toRefs} from "vue";

export default {
  components: {
    Menu, MenuButton, MenuItems, MenuItem
  },
  props: {
    links: {
      type: String,
      // required: true,
      default: ""
    }
  },
  setup(props, {slots}) {
    const active = ref(true);

    const {links} = toRefs(props)

    console.log(links.value)

    const handleClick = () => {
      active.value = !active.value;
    };

    return () =>
        slots.default({
          active: active.value,
          handleClick,
        });
  },
};
</script>
