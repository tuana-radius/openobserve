<!-- Copyright 2023 OpenObserve Inc.

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU Affero General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU Affero General Public License for more details.

You should have received a copy of the GNU Affero General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.
-->

<template>
  <div class="scroll" style="width: 100%; height: 100%; overflow: auto">
    <div
      v-html="DOMPurify.sanitize(htmlContent)"
      data-test="html-renderer"
    ></div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import DOMPurify from "dompurify";

export default defineComponent({
  name: "HTMLRenderer",
  props: {
    htmlContent: {
      type: String,
      default: "",
    },
  },
  setup(): any {
    return {
      DOMPurify,
    };
  },
});
</script>
