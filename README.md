# vue-social-links

![](screenshot/1.png)
![](screenshot/2.png)

```
npm install vue-social-links
```
## Used

```

<template>
  <div class="home">
    <vueSocialLinks
      :social="{
          youtube: 'test',
          instagram: 'test',
          github: 'test',
          twitter: 'test',
          linkedin: 'test',
          facebook: 'test',
      }"
    />
  </div>
</template>

<script>
import vueSocialLinks from 'vue-social-links';

export default {
  components: {
    vueSocialLinks,
  },
};
</script>


```
