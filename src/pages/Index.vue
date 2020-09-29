<template>
  <q-page class="row items-center justify-evenly">
    <q-icon name="img:icons/smart-foreman-logo.svg" size="250px"></q-icon>
    <q-icon name="img:icons/icon_SQ5_v2_optimized_xs.svg" size="400px"></q-icon>
    <example-component title="Example component" active :todos="todos" :meta="meta"></example-component>
    <div>
      <p>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed scelerisque eget sem ac viverra.
        Fusce blandit volutpat ligula. Maecenas quis erat turpis. Nulla vulputate et ante et tempus.
        Sed varius bibendum dictum. Duis vitae erat laoreet, tempus leo a, posuere odio. Phasellus massa ipsum,
        scelerisque ut mi ac, tincidunt pretium dui. Fusce malesuada in dui at viverra. Etiam ac dui volutpat,
        aliquam nulla vel, laoreet metus. Maecenas sed nisl ultricies, rutrum magna ut, volutpat massa. Integer
        eleifend semper ipsum sit amet eleifend. Pellentesque facilisis dolor ac fringilla posuere. Vivamus
        semper tempor mi a facilisis.
        Vestibulum id tincidunt urna. Fusce porta pretium metus non mattis. Nam at finibus ipsum. Quisque
        malesuada urna vitae tellus ullamcorper imperdiet. Cras viverra blandit egestas. Aenean placerat
        massa at aliquam finibus. Donec aliquet rutrum massa sit amet egestas. Nam tempor tincidunt augue
        quis pellentesque. Donec orci lorem, congue vel odio nec, facilisis ultricies magna. Pellentesque
        erat orci, aliquet eget porttitor non, porta in enim. Suspendisse tortor tortor, congue a ullamcorper
        at, venenatis in massa. Quisque volutpat tincidunt tortor id pellentesque. Sed pellentesque imperdiet auctor.
        Duis volutpat quis felis sit amet pulvinar. Proin maximus et lorem sed condimentum. Vivamus congue ante diam,
        sed gravida leo hendrerit nec. Suspendisse tincidunt odio id orci tincidunt accumsan. In tincidunt condimentum
        eleifend. Nullam sed metus arcu. In mollis varius velit, sit amet molestie ligula convallis at. Ut eleifend
        blandit leo, vitae placerat dui congue id. Fusce at commodo mi.
        Phasellus eu lacinia quam. Sed convallis dui at nunc volutpat, ut tempus tortor rhoncus. Donec congue mi eu justo
        venenatis, vel faucibus elit tempus. Integer efficitur eros in lorem tempus, ut consectetur velit sollicitudin.
        Mauris scelerisque auctor justo in lobortis. Vivamus gravida magna sed diam sagittis, quis lacinia dui venenatis.
        Cras quam nibh, semper vitae turpis eget, ullamcorper tristique metus. Curabitur in massa elit. Aenean sit amet
        nisi sed ipsum dapibus fringilla. Donec nulla elit, maximus eu diam et, ullamcorper ornare justo. Morbi euismod
        blandit placerat.
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed scelerisque eget sem ac viverra.
        Fusce blandit volutpat ligula. Maecenas quis erat turpis. Nulla vulputate et ante et tempus.
        Sed varius bibendum dictum. Duis vitae erat laoreet, tempus leo a, posuere odio. Phasellus massa ipsum,
        scelerisque ut mi ac, tincidunt pretium dui. Fusce malesuada in dui at viverra. Etiam ac dui volutpat,
        aliquam nulla vel, laoreet metus. Maecenas sed nisl ultricies, rutrum magna ut, volutpat massa. Integer
        eleifend semper ipsum sit amet eleifend. Pellentesque facilisis dolor ac fringilla posuere. Vivamus
        semper tempor mi a facilisis.
        Vestibulum id tincidunt urna. Fusce porta pretium metus non mattis. Nam at finibus ipsum. Quisque
        malesuada urna vitae tellus ullamcorper imperdiet. Cras viverra blandit egestas. Aenean placerat
        massa at aliquam finibus. Donec aliquet rutrum massa sit amet egestas. Nam tempor tincidunt augue
        quis pellentesque. Donec orci lorem, congue vel odio nec, facilisis ultricies magna. Pellentesque
        erat orci, aliquet eget porttitor non, porta in enim. Suspendisse tortor tortor, congue a ullamcorper
        at, venenatis in massa. Quisque volutpat tincidunt tortor id pellentesque. Sed pellentesque imperdiet auctor.
        Duis volutpat quis felis sit amet pulvinar. Proin maximus et lorem sed condimentum. Vivamus congue ante diam,
        sed gravida leo hendrerit nec. Suspendisse tincidunt odio id orci tincidunt accumsan. In tincidunt condimentum
        eleifend. Nullam sed metus arcu. In mollis varius velit, sit amet molestie ligula convallis at. Ut eleifend
        blandit leo, vitae placerat dui congue id. Fusce at commodo mi.
        Phasellus eu lacinia quam. Sed convallis dui at nunc volutpat, ut tempus tortor rhoncus. Donec congue mi eu justo
        venenatis, vel faucibus elit tempus. Integer efficitur eros in lorem tempus, ut consectetur velit sollicitudin.
        Mauris scelerisque auctor justo in lobortis. Vivamus gravida magna sed diam sagittis, quis lacinia dui venenatis.
        Cras quam nibh, semper vitae turpis eget, ullamcorper tristique metus. Curabitur in massa elit. Aenean sit amet
        nisi sed ipsum dapibus fringilla. Donec nulla elit, maximus eu diam et, ullamcorper ornare justo. Morbi euismod
        blandit placerat.
      </p>
    </div>
  </q-page>
</template>

<script lang="ts">
import { Todo, Meta } from 'components/models';
import ExampleComponent from 'components/CompositionComponent.vue';
import { defineComponent, ref } from '@vue/composition-api';

export default defineComponent({
  name: 'PageIndex',
  components: { ExampleComponent },
  setup() {
    const todos = ref<Todo[]>([
      {
        id: 1,
        content: 'ct1',
      },
      {
        id: 2,
        content: 'ct2',
      },
      {
        id: 3,
        content: 'ct3',
      },
      {
        id: 4,
        content: 'ct4',
      },
      {
        id: 5,
        content: 'ct5',
      },
    ]);
    const meta = ref<Meta>({
      totalCount: 1200,
    });
    return { todos, meta };
  },
});
</script>
