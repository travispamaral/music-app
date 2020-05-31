<template>
  <NotificationBell :class="{'has-notifications':hasNotifications}" />
</template>

<script>
import NotificationBell from '../../../public/img/icons/notificationBell.svg'

export default {
  name: 'NotificationIcon',
  components: { NotificationBell },
  props: {
    hasNotifications: {
      type: Boolean,
      default: false
    }
  }
}
</script>

<style lang="scss" scoped>
ellipse {
  fill: var(--accent);
  display: none;;
}
.has-notifications {
  ellipse { display: block; }
}
// svg {
//   position: relative;
//   width: 1rem;
//   height: 1rem;
//   &:after {
//     position: absolute;
//     top: -2px;
//     right: 0;
//     display: block;
//     width: .55rem;
//     height: .55rem;
//     background-color: var(--accent);
//     border-radius: 50%;
//     content: '';
//   }
// }
</style>
