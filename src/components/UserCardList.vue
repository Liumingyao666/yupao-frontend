<template>
    <van-card style="display: block ;width: 370px; text-align: left" v-for="user in props.userList"
        :desc="`座右铭:${user.profile}`"
        :title="`姓名:${user.username}`"
        :thumb="user.avatarUrl">
      <template #tags>
        <van-tag plain type="danger" v-for="tag in user.tags" style="margin-right: 8px; margin-top: 8px">
          {{ tag }}
        </van-tag>
      </template>
      <template #footer>
        <van-button size="mini">联系我</van-button>
      </template>
    </van-card>
</template>

<script setup lang="ts">
import {UserType} from "../models/user";

interface UserCardListProps {
  loading: boolean;
  userList: UserType[];
}

const props = withDefaults(defineProps<UserCardListProps>(), {
  loading: true,
  // @ts-ignore
  userList: [] as UserType[],
});

</script>

<style scoped>

</style>
